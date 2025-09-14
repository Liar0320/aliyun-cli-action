# aliyun-cli-action

This GitHub Action allows you to easily install and configure the Aliyun Command Line Interface (CLI) in your workflows. The Aliyun CLI is a powerful tool for interacting with Alibaba Cloud services.


## Usage
```
    steps:
    - name: Install and Configure Aliyun CLI
      uses: Liar0320/aliyun-cli-action@v1.0.2
      with:
        version: '3.0.181'
        access-key-id: ${{ secrets.ALIYUN_ACCESS_KEY_ID }}
        access-key-secret: ${{ secrets.ALIYUN_ACCESS_KEY_SECRET }}
        region: ${{ vars.ALIYUN_REGION }}

    - name: List objects in Aliyun OSS bucket
      run: aliyun oss ls ${{ vars.BUCKET_DESTINATION }}

    - name: Upload file to Aliyun OSS bucket
      run: |
        aliyun oss cp sample.html ${{ vars.BUCKET_DESTINATION }}
        echo "File uploaded successfully"
      working-directory: ${{ vars.WORKING_DIRECTORY }}

    - name: Upload folder to Aliyun OSS bucket
      run: |
        aliyun oss cp dist/ ${{ vars.BUCKET_DESTINATION }} -r
        echo "Folder uploaded successfully"
      working-directory: ${{ vars.WORKING_DIRECTORY }}
```

## Getting more details

To get more details, follow the step by step guide through my medium
- [Publish Your First GitHub Action to Automate Alibaba Cloud OSS Operations](https://medium.com/@wadexu007/3337aa5e5d60?source=friends_link&sk=0c86e6344745b34eeb551e601af3bbc7)

## Environment Setup

### Local Testing with act

1. **Install act**:
   ```bash
   brew install act
   ```

2. **Pull Docker image**:
   ```bash
   docker pull catthehacker/ubuntu:act-latest --platform linux/amd64
   ```

3. **Run local test**:
   ```bash
   act --container-architecture linux/amd64 --input trigger=manually --secret-file my.secrets --var-file my.variables -W .github/workflows/test_with_local_actions.yaml
   ```

## Related Projects

- [auto-push-oss](https://github.com/OSpoon/auto-push-oss/tree/main) - A Node.js version GitHub Action for uploading files to Aliyun OSS
- [nektos/act](https://github.com/nektos/act) - Run your GitHub Actions locally
- [Alibaba Cloud OSS CLI Commands](https://www.alibabacloud.com/help/en/oss/developer-reference/common-commands) - Official OSS command reference

## License
This GitHub Action is licensed under the MIT License.
