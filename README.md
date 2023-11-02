# Minio

## Usage

```sh
require (
  github.com/minio/minio v0.0.1
)

replace github.com/minio/minio v0.0.1 => github.com/Laisky/minio laisky
```

## New Features

### Verify AWS SigV4 Signature

```go
import minioCmd "github.com/minio/minio/cmd"

if err := minioCmd.ReqSignatureV4Verify(req,
    region, minioCmd.ServiceType("kms-xks-proxy"),
    minioCmd.SignatureV4VerifyCredential(cred.AccessKeyID, cred.SecretAccessKey),
); err != nil {
    return errors.Wrap(err, "verify aws v4 signature")
}
```
