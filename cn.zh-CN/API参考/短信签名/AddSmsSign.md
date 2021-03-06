# AddSmsSign {#doc_api_Dysmsapi_AddSmsSign .reference}

调用短信AddSmsSign申请短信签名。

您可以通过短信服务API接口或短信服务控制台申请短信签名，签名需要符合[个人用户签名规范](~~108076~~)或[企业用户签名规范](~~108254~~)。

短信签名审核流程请参考[签名审核流程](~~108083~~)。

**说明：** 个人用户每天最多可以申请一个短信签名，适用场景默认为**通用**。企业用户每天最多可以申请100个签名。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Dysmsapi&api=AddSmsSign&type=RPC&version=2017-05-25)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|SignName|String|是|阿里云|签名名称。

 **说明：** 签名必须符合[个人用户签名规范](~~108076~~)或[企业用户签名规范](~~108254~~)。

 |
|SignSource|Integer|是|1|签名来源。其中：

 -   0：企事业单位的全称或简称。
-   1：工信部备案网站的全称或简称。
-   2：APP应用的全称或简称。
-   3：公众号或小程序的全称或简称。
-   4：电商平台店铺名的全称或简称。
-   5：商标名的全称或简称

 **说明：** 签名来源为1时，请在申请说明中添加网站域名，加快审核速度。

 |
|Remark|String|是|当前的短信签名应用于双11大促推广营销|短信签名申请说明。请在申请说明中详细描述您的业务使用场景，申请工信部备案网站的全称或简称请在此处填写域名，长度不超过200个字符。

 |
|Action|String|否|AddSmsSign|系统规定参数。取值：**AddSmsSign**。

 |
|AccessKeyId|String|否|LTAIP00vvvvvvvvv|主账号AccessKey的ID。

 |
|SignFileList.N.FileSuffix|String|否|jpg|签名的证明文件格式，支持上传多张图片。当前支持jpg、png、gif或jpeg格式的图片。

 个别场景下，申请签名需要上传证明文件。详细说明请参考[个人用户签名规范](~~108076~~)和[企业用户签名规范](~~108254~~)。

 |
|SignFileList.N.FileContents|String|否|R0lGODlhHAAmAKIHAKqqqsvLy0hISObm5vf394uLiwAA|签名的资质证明文件经base64编码后的字符串。图片不超过2 MB。

 个别场景下，申请签名需要上传证明文件。详细说明请参考[个人用户签名规范](~~108076~~)和[企业用户签名规范](~~108254~~)。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|SignName|String|阿里云|签名名称。

 |
|Message|String|OK|状态码的描述。

 |
|RequestId|String|F655A8D5-B967-440B-8683-DAD6FF8DE990|请求ID。

 |
|Code|String|OK|请求状态码。

 -   返回OK代表请求成功。
-   其他错误码详见[错误码列表](~~101346~~)。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=AddSmsSign
&SignName=阿里云
&SignSource=1
&Remark=当前的短信签名应用于双11大促推广营销
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AddSmsSignResponse>
      <SignName>阿里云</SignName>
      <Message>OK</Message>
      <RequestId>F655A8D5-B967-440B-8683-DAD6FF8DE990</RequestId>
      <Code>OK</Code>
</AddSmsSignResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"SignName":"阿里云",
	"Message":"OK",
	"RequestId":"F655A8D5-B967-440B-8683-DAD6FF8DE990",
	"Code":"OK"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Dysmsapi)查看更多错误码。

