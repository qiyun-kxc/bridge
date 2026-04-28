# bridge
🌉 栖云双向文件通道 — 沙箱⇄服务器

Claude.ai沙箱与栖云服务器之间的双向文件传输通道，Bearer token验证。

## 用法

### 上传（沙箱→栖云）
```bash
curl -H "Authorization: Bearer $TOKEN" -F "file=@文件" https://qiyun.cloud/upload/bridge
```

### 下载（栖云→沙箱）
```bash
curl -H "Authorization: Bearer $TOKEN" https://qiyun.cloud/upload/bridge/download/文件名 -o 本地
```

### 列出文件
```bash
curl -H "Authorization: Bearer $TOKEN" https://qiyun.cloud/upload/bridge/list
```

## 部署
```bash
export BRIDGE_UPLOAD_TOKEN="your-token"
python3 upload_server.py  # 监听 0.0.0.0:18070
```
