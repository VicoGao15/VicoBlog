---
layout: wiki  # 使用wiki布局模板
wiki: twosix # 这是项目名
title: Polo API 代理
banner: /assets/cover/note.jpg
---

### 一、代理网站和账号
代理网址：https://nano.580ai.net/
13500042947@163.com/@Vico202204

### 二、文档

自定义apifox文档：https://580ai.apifox.cn/

apifox接口文档：https://polodaili.apifox.cn

Banana API调用参考文档：https://www.yuque.com/yuqueyonghumhm84z/rkuauy/yre0s8d92pl1lv3p?singleDoc#

Polo API网站：https://poloapi.com/

PoloAPI接口文档：https://apidoc.poloapi.com/342125236e0

Gemini官方文档：https://ai.google.dev/gemini-api/docs/image-generation?hl=zh-cn#optional_configurations

### 三、调用地址
```
HEADERS_nanoapi = {
            "Content-Type": "application/json",
            "Authorization": "sk-lIweJiwjWJxqdTyufQ3r2PLZAsmiGunbqKXqngthp2PLDGeN"
        }
NANO_BANANA_URL = 'https://nanoapi.poloai.top/v1beta/models/gemini-2.5-flash-image-preview:generateContent'
NANO_BANANA_PRO_URL = 'https://nanoapi.poloai.top/v1beta/models/gemini-3-pro-image-preview:generateContent'
NANO_BANANA_PRO_HIGT_URL = 'https://nano.580ai.net/v1beta/models/gemini-3-pro-image-preview-high:generateContent'
```

### 四、参数
``` Nano banana / Pro 文生图
{
    "contents": [
        {
            "role": "user",
            "parts": [
                {
                    "text": "小黄人在吃西瓜"
                }
            ]
        }
    ],
    "generationConfig": {
        "responseModalities": [
            "IMAGE"
        ],
        "imageConfig": {
            "aspectRatio": "1:1",
            "imageSize": "4K",  # banana pro可选2k/4k, nano banana无用，生图均为1k
        }
    }
}
```

``` Nano banana / Pro 图编辑
{
    "contents": [
        {
            "role": "user",
            "parts": [
                {
                    "inlineData": {
                        "mimeType": "image/png",
                        "data": base64_str
                    }
                },
                {
                    "text": "红帽子改为绿白相间竖条纹帽子"
                }
            ]
        }
    ],
    "generationConfig": {
        "responseModalities": [
            "IMAGE"
        ],
        "imageConfig": {
            "aspectRatio": "1:1",
            "imageSize": "4K"   # banana pro可选2k/4k, nano banana无用，生图均为1k
        }
    }
}
```
#### 多图
```
"parts": [
    {
        "inlineData": {
            "mimeType": "image/png",
            "data": base64_str
        }
    },
    {
        "inlineData": {
            "mimeType": "image/png",
            "data": base64_str1
        }
    },
    {
        "text": "图片融合"
    }
]
```

### 五、注意事项
- 参数"imageSize": "4K"，K必需为大写
- Pro，最多 6 张高保真对象图片，用于包含在最终图片中
- 默认情况下，模型会返回文本和图片响应（即 response_modalities=['Text', 'Image']）。可以使用 response_modalities=['Image'] 将响应配置为仅返回图片而不返回文本
- 默认情况下，模型会使输出图片的大小与输入图片的大小保持一致，否则会生成 1:1 的正方形
- 支持的分辨率，参考官方
