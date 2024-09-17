# Install mkcert

```
brew install mkcert
```

# Generate certificate and install new local certificate authority

```
mkcert -install
mkcert zoop-release-sdk-ios-prd.s3.sa-east-1.amazonaws.com 127.0.0.1 ::1
```

# Move certificate files to ssl folder
```
mv zoop-release-sdk-ios-prd.s3.sa-east-1.amazonaws.com+2-key.pem ssl/cert-key.pem
mv zoop-release-sdk-ios-prd.s3.sa-east-1.amazonaws.com+2.pem ssl/cert.pem 
```

# Start docker-composer
```
docker-compose -f docker-compose.local.yml up
```

# Test SSL - Open Browser

(https://zoop-release-sdk-ios-prd.s3.sa-east-1.amazonaws.com/)

# Test Download File

(https://zoop-release-sdk-ios-prd.s3.sa-east-1.amazonaws.com/EMVConnect/iOS/2.1.9/EMVConnectiOSPrd.zip)

# Test Download File With Curl

```
CURL_SSL_BACKEND=secure-transport curl -v -k -O https://zoop-release-sdk-ios-prd.s3.sa-east-1.amazonaws.com/EMVConnect/iOS/2.1.9/EMVConnectiOSPrd.zip
```