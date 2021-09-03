# AWS S3 PUBLIC ACCESS
![1) Public Accesss](https://user-images.githubusercontent.com/47303106/132001867-9dd10ae1-dfac-45a1-bca2-4f45ebc0d98c.png)
2. *Bucket policy*:
```{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::serialtown-storage/*"
        }
    ]
}
```
3. CORS:
```
[
    {
        "AllowedHeaders": [
            "Authorization",
            "Content-Type",
            "Origin",
            "X-Requested-With"
        ],
        "AllowedMethods": [
            "GET",
            "POST"
        ],
        "AllowedOrigins": [
            "*"
        ],
        "ExposeHeaders": [
            "ETag"
        ],
        "MaxAgeSeconds": 3000
    }
 ]
```
