# How to use model from local path or git server or S3 storage

## Pre-requirement

Run command `aws configure` to set `Access key` and `Secrete key` for S3 storage.

## Configure model with custom storage

Enable `endpoint_url` in model.yaml file to point to custom S3 storage endpoint URL.

```
# from AWS S3
    s3_mirror_config: 
      # bucket_uri: s3://gpt2/facemodel/  # Must include hash file with commit id in the repo

# from custom S3 storage such as minio
    s3_mirror_config:
      endpoint_url: http://3.107.108.170:9000 # for custom S3 storage endpoint url 
      bucket_uri: s3://gpt2/facemodel/  # Must include hash file with commit id in the repo

# from local path
    s3_mirror_config:
      bucket_uri: /Users/hub/models/gpt2/ # Local path of model with hash file

# from git server
    s3_mirror_config:
      git_uri: https://portal.opencsg.com/models/AIWizards/gpt2.git # git address for git clone
```

To use the local path of the model, set `bucket_uri` to the local path. For example: `bucket_uri: /Users/home/models/gpt2/`.

To download the model using `git clone`, set `git_uri` to the model address.
