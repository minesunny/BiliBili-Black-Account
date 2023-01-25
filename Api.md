获取个人黑名单列表
接口 https://api.bilibili.com/x/relation/blacks
方法：GET
参数类型：URLParam

| 参数名        | 类型     | 内容                               | 必要性 | 备注                            |
|------------|--------|----------------------------------|-----|-------------------------------|
| csrf       | str    | 5ebd55ca8627064b9c77a66f128b1fe0 | 必要  | cookie中bili_jct字段             |
| jsonp      | str    | jsonp                            | 必要  | 序列化类型                         |
| pn         | number | 1                                | 必要  | pageNumber start index with 0 |
| ps         | number | 20                               | 必要  | pageSize                      |
| re_version | number | 0                                | 必要  | 不知                            |

请求例子
## 黑名单列表请求
```shell
curl "https://api.bilibili.com/x/relation/blacks?csrf=5ebd55ca8627064b9c77a66f128b1fe0&jsonp=jsonp&pn=1&ps=20&re_version=0" \
-H 'cookie: buvid3=A196E54B-BD49-61DC-CA79-8C5474A0E00F91642infoc; i-wanna-go-back=-1; buvid_fp=A196E54B-BD49-61DC-CA79-8C5474A0E00F91642infoc; buvid_fp_plain=undefined; hit-dyn-v2=1; CURRENT_BLACKGAP=0; LIVE_BUVID=AUTO2416550166022866; blackside_state=0; nostalgia_conf=-1; is-2022-channel=1; buvid4=null; hit-new-style-dyn=0; rpdid=|(YYl~JRJkk0J\'uYY)YYk)R|; DedeUserID=421177496; DedeUserID__ckMd5=ba9894aa5da6f16e; b_ut=5; dy_spec_agreed=1; CURRENT_FNVAL=4048; fingerprint=1a351ff4afeedd4fba4c55aec5fa476e; CURRENT_QUALITY=80; SESSDATA=5ea40568,1690169086,9bfa3*12; bili_jct=5ebd55ca8627064b9c77a66f128b1fe0; bp_video_offset_421177496=754547594301014100; sid=6a6xi0b9; innersign=1; b_lsid=32B1765B_185E8FCA1B3; b_nut=1674651148' \
-H 'Accept-Encoding: gzip, zlib, deflate, zstd, br'
```

HTTPie
```shell
http GET 'https://api.bilibili.com/x/relation/blacks?csrf=5ebd55ca8627064b9c77a66f128b1fe0&jsonp=jsonp&pn=1&ps&re_version=0' \
    'cookie':'buvid3=A196E54B-BD49-61DC-CA79-8C5474A0E00F91642infoc; i-wanna-go-back=-1; buvid_fp=A196E54B-BD49-61DC-CA79-8C5474A0E00F91642infoc; buvid_fp_plain=undefined; hit-dyn-v2=1; CURRENT_BLACKGAP=0; LIVE_BUVID=AUTO2416550166022866; blackside_state=0; nostalgia_conf=-1; is-2022-channel=1; buvid4=null; hit-new-style-dyn=0; rpdid=|(YYl~JRJkk0J'uYY)YYk)R|; DedeUserID=421177496; DedeUserID__ckMd5=ba9894aa5da6f16e; b_ut=5; dy_spec_agreed=1; CURRENT_FNVAL=4048; fingerprint=1a351ff4afeedd4fba4c55aec5fa476e; CURRENT_QUALITY=80; SESSDATA=5ea40568,1690169086,9bfa3*12; bili_jct=5ebd55ca8627064b9c77a66f128b1fe0; bp_video_offset_421177496=754547594301014100; sid=6a6xi0b9; innersign=1; b_lsid=32B1765B_185E8FCA1B3; b_nut=1674651148' \
    'Accept-Encoding':'gzip, zlib, deflate, zstd, br'

```

响应例子
```json
{
    "code": 0,
    "data": {
        "list": [
            {
                "attribute": 128,
                "face": "https:\/\/i0.hdslb.com\/bfs\/face\/member\/noface.jpg",
                "face_nft": 0,
                "mid": 693101261,
                "mtime": 1674102855,
                "nft_icon": "",
                "official_verify": {
                    "desc": "",
                    "type": 0
                },
                "rec_reason": "",
                "sign": "",
                "special": 0,
                "tag": null,
                "track_id": "",
                "uname": "\u65e0\u8bed\u7684\u80a5\u5b85",
                "vip": {
                    "accessStatus": 0,
                    "avatar_subscript": 0,
                    "avatar_subscript_url": "",
                    "dueRemark": "",
                    "label": {
                        "bg_color": "",
                        "bg_style": 0,
                        "border_color": "",
                        "label_theme": "",
                        "path": "",
                        "text": "",
                        "text_color": ""
                    },
                    "nickname_color": "",
                    "themeType": 0,
                    "vipDueDate": 0,
                    "vipStatus": 0,
                    "vipStatusWarn": "",
                    "vipType": 0
                }
            }
        ],
        "re_version": 0,
        "total": 114
    },
    "message": "0",
    "ttl": 1
} 
```



拉黑UUID
接口 https://api.bilibili.com/x/relation/modify
方法：POST
参数类型：application/x-www-form-urlencoded


| 参数名            | 类型     | 内容                                                                                                                                                                                                              | 必要性 | 备注                                   |
|----------------|--------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|--------------------------------------|
| fid            | str    | 1830345558                                                                                                                                                                                                      | 必要  | 要拉黑的uuid                             |
| act            | number | 5                                                                                                                                                                                                               | 必要  | modify类型 5应该是拉黑 ，6是移除黑名单             |
| re_src         | number | 11                                                                                                                                                                                                              | 必要  | 未知                                   |
| spmid          | number | 333.999.0.0                                                                                                                                                                                                     | 必要  | 未知                                   |
| extend_content | json   | {"entity":"user","entity_id":1830345558,"fp":"undefined\u0001undefined\u0001undefined\u0001undefined\u0001undefined\u0001undefined\u0001undefined\u0001undefined\u0001undefined\u0001undefined\u0001undefined"} | 必要  | 具体信息,只有需要entity_id是要拉黑的uuid ，其他字段值固定 |
| jsonp          | str    | jsonp                                                                                                                                                                                                           | 必要  | 序列化类型                                |
| csrf           | str    | 5ebd55ca8627064b9c77a66f128b1fe0                                                                                                                                                                                | 必要  | cookie中bili_jct字段                    |


请求例子
## 黑名单列表请求
```shell
## 拉黑用户
curl -X "POST" "https://api.bilibili.com/x/relation/modify" \
     -H 'cookie: buvid3=A196E54B-BD49-61DC-CA79-8C5474A0E00F91642infoc; i-wanna-go-back=-1; buvid_fp=A196E54B-BD49-61DC-CA79-8C5474A0E00F91642infoc; buvid_fp_plain=undefined; hit-dyn-v2=1; CURRENT_BLACKGAP=0; LIVE_BUVID=AUTO2416550166022866; blackside_state=0; nostalgia_conf=-1; is-2022-channel=1; buvid4=null; hit-new-style-dyn=0; rpdid=|(YYl~JRJkk0J\'uYY)YYk)R|; DedeUserID=421177496; DedeUserID__ckMd5=ba9894aa5da6f16e; b_ut=5; dy_spec_agreed=1; CURRENT_FNVAL=4048; fingerprint=1a351ff4afeedd4fba4c55aec5fa476e; CURRENT_QUALITY=80; SESSDATA=5ea40568,1690169086,9bfa3*12; bili_jct=5ebd55ca8627064b9c77a66f128b1fe0; bp_video_offset_421177496=754547594301014100; sid=6a6xi0b9; innersign=1; b_lsid=32B1765B_185E8FCA1B3; b_nut=1674651148' \
     -H 'Content-Type: application/x-www-form-urlencoded; charset=utf-8' \
     -H 'Accept-Encoding: gzip, zlib, deflate, zstd, br' \
     --data-urlencode "fid=1830345558" \
     --data-urlencode "act=5" \
     --data-urlencode "re_src=11" \
     --data-urlencode "spmid=333.999.0.0" \
     --data-urlencode "extend_content={\"entity\":\"user\",\"entity_id\":1830345558,\"fp\":\"undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\"}" \
     --data-urlencode "jsonp=jsonp" \
     --data-urlencode "csrf=5ebd55ca8627064b9c77a66f128b1fe0"

```

HTTPie
```shell
http --form POST 'https://api.bilibili.com/x/relation/modify' \
    'cookie':'buvid3=A196E54B-BD49-61DC-CA79-8C5474A0E00F91642infoc; i-wanna-go-back=-1; buvid_fp=A196E54B-BD49-61DC-CA79-8C5474A0E00F91642infoc; buvid_fp_plain=undefined; hit-dyn-v2=1; CURRENT_BLACKGAP=0; LIVE_BUVID=AUTO2416550166022866; blackside_state=0; nostalgia_conf=-1; is-2022-channel=1; buvid4=null; hit-new-style-dyn=0; rpdid=|(YYl~JRJkk0J'uYY)YYk)R|; DedeUserID=421177496; DedeUserID__ckMd5=ba9894aa5da6f16e; b_ut=5; dy_spec_agreed=1; CURRENT_FNVAL=4048; fingerprint=1a351ff4afeedd4fba4c55aec5fa476e; CURRENT_QUALITY=80; SESSDATA=5ea40568,1690169086,9bfa3*12; bili_jct=5ebd55ca8627064b9c77a66f128b1fe0; bp_video_offset_421177496=754547594301014100; sid=6a6xi0b9; innersign=1; b_lsid=32B1765B_185E8FCA1B3; b_nut=1674651148' \
    'Content-Type':'application/x-www-form-urlencoded; charset=utf-8' \
    'Accept-Encoding':'gzip, zlib, deflate, zstd, br' \
    'fid'='1830345558' \
    'act'='5' \
    're_src'='11' \
    'spmid'='333.999.0.0' \
    'extend_content'='{\"entity\":\"user\",\"entity_id\":1830345558,\"fp\":\"undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\\u0001undefined\"}' \
    'jsonp'='jsonp' \
    'csrf'='5ebd55ca8627064b9c77a66f128b1fe0'

```
响应例子
```json
{"code":0,"message":"0","ttl":1}
```