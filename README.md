# วิธีใช้งาน Docker registry ของ Github ขั้นเริ่มต้น

## สร้าง Access Token สำหรับนักพัฒนา
1. ไปที่ `Profile > Settings > Developer Settings > Personal access tokens`
2. ทำการสร้าง Token `Generate new token`
3. ให้ทำการเก็บ Token ดังกล่าวไว้

## สร้าง Token ไว้ในเครื่องของเรา
```sh
export GH_TOKEN=[YOUR_TOKEN]
```

## Docker Login
```sh
echo $GH_TOKEN | docker login ghcr.io -u USERNAME --password-stdin
# Output > Login Succeeded
```

## Pushing container images
```sh
docker push ghcr.io/[OWNER]/[IMAGE_NAME]:[Version: ex. latest or 1.0]
# Ex.
docker push ghcr.io/testowner/helloworld:latest
```

## Pulling container images
```sh
docker inspect ghcr.io/OWNER/IMAGE_NAME
# Ex.
docker pull ghcr.io/OWNER/IMAGE_NAME@sha256:82jf9a84u29hiasldj289498uhois8498hjs29hkuhs
```

## Tagging container images
```sh
docker tag 38f737a91f39 ghcr.io/OWNER/NEW_IMAGE_NAME:latest
```
