# fastapi vercel demo

vercel部署fastapi示例仓库

## 配置说明

- Node.js Version：20.x

需要编写几个配置文件：

vercel_build.sh

内容如下

```shel
pip install -r requirements.txt
```

vercel.json

内容如下

```json
{
  "devCommand": "uvicorn main:app --host 0.0.0.0 --port 3000",
  "builds": [
    {
      "src": "main.py",
      "use": "@vercel/python"
    }
  ],
  "routes": [
    {
      "src": "/",
      "dest": "main.py"
    },
    {
      "src": "/docs",
      "dest": "main.py"
    },
    {
      "src": "/openapi.json",
      "dest": "main.py"
    }
  ]
}
```
