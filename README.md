# 浙江道路实时视频 

数据来源：https://ddzlcx.zjt.gov.cn/wx/home.html#/main/camera  

## 视频流获取方式(Python)
```python
import requests
url='https://ddzlcx.jtyst.zj.gov.cn/zlcx2/hikvisionVideo/getVideoUrlByCameraCode'
data = {
    "cameraCode":videoId,#设备ID
    "type":2
}
headers={
    'authorization': 'xxxxxx xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx'#授权密钥
}
response = requests.get(url=url,params=data,headers=headers,verify=False)
getjson = response.text

#响应内容：
{
  "code": 100000,
  "msg": "成功",
  "data": "https://splkplay.jtyst.zj.gov.cn/ctm01epcp/fdaedf16-0c2f-4891-a51e-325dcad59096_sub.m3u8?auth_key=1688736298-0-0-ee8beb817e1290515e8863f99fba2f8c"
}
#视频参数：H264/352x288/25
```
## 查看示例：B站  

## 视频流有时效性，可在需要使用时再请求视频流
