# aliyun-cli-action

This GitHub Action allows you to easily install and configure the Aliyun Command Line Interface (CLI) in your workflows. The Aliyun CLI is a powerful tool for interacting with Alibaba Cloud services.


## Usage
```
    steps:
    - name: Install and Configure Aliyun CLI
      uses: Liar0320/aliyun-cli-action@v1.0.0
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

## License
This GitHub Action is licensed under the MIT License.
