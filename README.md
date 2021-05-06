# AWS S3 Github Action

Upload, download, or list files/folders through Github Actions.

Based on keithweaver/aws-s3-github-action, with bugfixes.

```
- uses: gsaraf/aws-s3-github-action@master
  with:
    command: cp
    source: ./local_file.txt
    destination: s3://yourbucket/folder/local_file.txt
    aws_access_key_id: ${{ secrets.AWS_ACCESS_KEY_ID }}
    aws_secret_access_key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
    aws_region: eu-central-1
```

**Inputs**

| Variable name      | Required/Optional  | Default  | Description                |
| ------------------ | ------------------ | -------- | -------------------------- |
| `command`          | Optional           | `cp`     | This is the command that is being performed. When using the AWS CLI, it's the portion following the service. `aws s3 cp ...` <- `cp`, `aws s3 ls` <- `ls` |
| `source`           | Required           | N/A      | Depending on the command, this could be the directory you are requesting list, or the source file. |
| `destination`      | Required for `cp`, `mv` and `sync` | N/A      | The location where you want the file to arrive. |
| `aws_region` | Required   | N/A | This is the aws region for the S3 bucket. [More info](https://docs.aws.amazon.com/cli/latest/reference/configure/) |
| `aws_access_key_id` | Optional   | N/A | This is the credentials from an IAM role for getting access to a bucket. [More info](https://docs.aws.amazon.com/cli/latest/reference/configure/) |
| `aws_secret_access_key` | Optional   | N/A | This is the credentials from an IAM role for getting access to a bucket. [More info](https://docs.aws.amazon.com/cli/latest/reference/configure/) |
| `aws_session_token` | Optional   | N/A | This is the credentials from an IAM role for getting access to a bucket. [More info](https://docs.aws.amazon.com/cli/latest/reference/configure/) |
| `metadata_service_timeout` | Optional   | N/A | The number of seconds to wait until the metadata service request times out. [More info](https://docs.aws.amazon.com/cli/latest/reference/configure/) |
