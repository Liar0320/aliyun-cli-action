# aliyun-cli-action

This GitHub Action allows you to easily install and configure the Aliyun Command Line Interface (CLI) in your workflows. The Aliyun CLI is a powerful tool for interacting with Alibaba Cloud services.


## Usage
```
    steps:
    - name: Install and Configure Aliyun CLI
      uses: wadexu007/aliyun-cli-action@v1.0.0
      with:
        aliyun-cli-version: '3.0.181'
        access-key-id: ${{ secrets.ALIYUN_ACCESS_KEY_ID }}
        access-key-secret: ${{ secrets.ALIYUN_ACCESS_KEY_SECRET }}
        region: ${{ vars.ALIYUN_REGION }}

    - name: List objects in Aliyun OSS bucket
      run: aliyun oss ls oss://xxx
```

## Getting more details

To get more details, follow the step by step guide through my medium 
- [Publish Your First GitHub Action to Automate Alibaba Cloud OSS Operations](https://medium.com/@wadexu007/3337aa5e5d60?source=friends_link&sk=0c86e6344745b34eeb551e601af3bbc7)

## License
This GitHub Action is licensed under the MIT License.
