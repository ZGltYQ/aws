# AWS S3 PUBLIC ACCESS
1. Open the Amazon S3 console at https://console.aws.amazon.com/s3/.
2. Choose the name of the bucket that you have configured as a static website.
3. Choose Permissions.
4. Under Block public access (bucket settings), choose Edit.
5. Clear Block all public access, and choose Save changes.

![1) Public Accesss](https://user-images.githubusercontent.com/47303106/132001867-9dd10ae1-dfac-45a1-bca2-4f45ebc0d98c.png)

6. Under Buckets, choose the name of your bucket.
7. Choose Permissions.
8. Under Bucket Policy, choose Edit.
9. To grant public read access for your website, copy the following bucket policy, and paste it in the Bucket policy editor.

```{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::Bucket-Name/*"
        }
    ]
}
```
10. Update the Resource to your bucket name. In the preceding example bucket policy, Bucket-Name is a placeholder for the bucket name. To use this bucket policy with your own bucket, you must update this name to match your bucket name.

11. Choose Save changes. A message appears indicating that the bucket policy has been successfully added. If you see an error that says Policy has invalid resource, confirm that the bucket name in the bucket policy matches your bucket name. For information about adding a bucket policy, see How do I add an S3 bucket policy?
If you get an error message and cannot save the bucket policy, check your account and bucket Block Public Access settings to confirm that you allow public access to the bucket.

## CORS

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

# Object access control lists

![Screenshot_2021-09-03_15-34-58](https://user-images.githubusercontent.com/47303106/132006202-f445479c-cbd5-4056-823c-5a3073d21b95.png)
