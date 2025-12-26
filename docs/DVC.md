# DVC

## 配置S3

```
dvc remote add -d mys3 s3://test-dvc/nf250
dvc remote modify mys3 endpointurl http://127.0.0.1:9000
dvc remote modify mys3 use_ssl false
dvc remote modify --local mys3 access_key_id 'xxxx'
dvc remote modify --local mys3 secret_access_key 'xxxx'
```

### 推送报错 MissingContentLength

An error occurred (MissingContentLength) when calling the PutObject operation: Unknown

设置环境变量解决

powershell

```
$env:AWS_REQUEST_CHECKSUM_CALCULATION = "WHEN_REQUIRED"

$env:AWS_RESPONSE_CHECKSUM_VALIDATION = "WHEN_REQUIRED"
```


bash

```
export AWS_REQUEST_CHECKSUM_CALCULATION = "WHEN_REQUIRED"

export AWS_RESPONSE_CHECKSUM_VALIDATION = "WHEN_REQUIRED"
```
