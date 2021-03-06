# sms-server 

[![](https://img.shields.io/badge/readme%20style-standard-green)](https://www.github.com/my-sakura/sms-server)
[![Go Report Card](https://goreportcard.com/badge/github.com/my-sakura/go-sms-server)](https://goreportcard.com/report/github.com/my-sakura/go-sms-server)
[![](https://camo.githubusercontent.com/a534d512dd511cc3dbba106a143f49102de27441cefb97421d90dc8d8ea7661f/68747470733a2f2f696d672e736869656c64732e696f2f61706d2f6c2f61746f6d69632d64657369676e2d75692e7376673f)](https://github.com/my-Sakura/go-sms-server/blob/main/LICENSE)

  sms-server could send a custom length verification code 
  
## Table of Contents

- [smsProvider](https://github.com/my-Sakura/sms-server#smsprovider)
  - [tianyan](https://github.com/my-sakura/sms-server#tianyan)
  - [dingxin](https://github.com/my-sakura/sms-server#dingxin)
- [Usage](https://github.com/my-Sakura/sms-server#usage)
- [result](https://github.com/my-Sakura/go-sms-server#succeed)
- [API](https://github.com/my-Sakura/sms-server#api)
- [Examples](https://github.com/my-Sakura/sms-server#example)
- [License](https://github.com/my-Sakura/sms-server#license)

## smsProvider
### tianYan

  https://market.aliyun.com/products/57000002/cmapi00039249.html
  测试模板: M09DD535F4
### dingXin

  https://market.aliyun.com/products/56928004/cmapi023305.html
  测试模板: TP1711063

## Usage

1.select [smsProvider](https://github.com/my-Sakura/sms-server#smsprovider)
   选择短信 API 服务商，目前支持 [tianyan](https://market.aliyun.com/products/57000002/cmapi00039249.html) 和 [dingxin](https://market.aliyun.com/products/56928004/cmapi023305.html)，记录供应商名称(全部小写)，之后会用到
   
2.进入云市场购买产品，购买完之后申请模板，记录 templateCode 和 appCode, eg:
  ![](https://github.com/my-Sakura/sms-server/blob/main/pictures/first.png)
   
  ![](https://github.com/my-Sakura/sms-server/blob/main/pictures/second.png)
   
  联系客服申请模板，获得 templateCode
  ![](https://github.com/my-Sakura/sms-server/blob/main/pictures/third.png)
   
  ![](https://github.com/my-Sakura/sms-server/blob/main/pictures/fourth.png)
   
  记录 appCode
  ![](https://github.com/my-Sakura/sms-server/blob/main/pictures/fifth.png)
  
3.调用 API

```
client := api.NewClient([smsProvider], [appCode], [templateCode])
err := client.Send([phone_number], 6)
if err != nil {
	log.Println(err)
}
```

## succeed
  ![](https://github.com/my-Sakura/go-sms-server/blob/main/pictures/succeed.png)
## API

To see how the specification has been applied, see the [API](https://github.com/my-Sakura/sms-server/tree/main/api) directory.

## Example

To see how the specification has been applied, see the [Examples](https://github.com/my-Sakura/sms-server/tree/main/examples) directory.

```
package main

import (
	"log"

	"github.com/my-Sakura/go-sms-server/api"
)

func main() {
	client := api.NewClient("tianyan", [appCode], "M09DD535F4")
	err := client.Send([phone_number], 6)
	if err != nil {
		log.Println(err)
	}
}
```

## License

[MIT](https://github.com/my-Sakura/sms-server/blob/main/LICENSE) © my-Sakura :heart: :star: :sparkles: :dizzy:
