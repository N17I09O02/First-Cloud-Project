---
title : "Connect S3 vào dự án"
date: "2025-06-14"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---

1. Cài S3 vào dự án của bạn.
  ```
    dotnet add package AWSSDK.S3
  ```

2. Cấu hình trong appsettings.json
  ```
    "AWS": {
      "Region": "us-east-1",
      "BucketName": "quanlydonhang-images"
    }
  ```

3. Viết service xử lý.
  ```
    using Amazon.S3;
    using Amazon.S3.Transfer;
    using Microsoft.Extensions.Configuration;

    public class S3Service
    {
        private readonly IAmazonS3 _s3Client;
        private readonly string _bucketName;

        public S3Service(IAmazonS3 s3Client, IConfiguration config)
        {
            _s3Client = s3Client;
            _bucketName = config["AWS:BucketName"];
        }

        public async Task<string> UploadFileAsync(IFormFile file)
        {
            var key = Guid.NewGuid().ToString() + Path.GetExtension(file.FileName);

            using var stream = file.OpenReadStream();
            var uploadRequest = new TransferUtilityUploadRequest
            {
                InputStream = stream,
                Key = key,
                BucketName = _bucketName,
                ContentType = file.ContentType
            };

            var transferUtility = new TransferUtility(_s3Client);
            await transferUtility.UploadAsync(uploadRequest);

            return key;
        }

        public string GetFileUrl(string key)
        {
            return $"https://{_bucketName}.s3.amazonaws.com/{key}";
        }
    }
  ```

4. Đăng ký S3Service vào Program.cs
  ```
    builder.Services.AddAWSService<IAmazonS3>();
    builder.Services.AddScoped<S3Service>();
  ```

5. Code mẫu xử lý việc upload ảnh
  ```
  [HttpPost("upload")]
  public async Task<IActionResult> UploadImage(IFormFile file, [FromServices] S3Service s3Service)
  {
      var key = await s3Service.UploadFileAsync(file);
      var url = s3Service.GetFileUrl(key);
      return Ok(new { Url = url });
  }
  ```