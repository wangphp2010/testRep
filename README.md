#### 为样式文件传入参数

lib\RecaptchaBundle\Resources\views\fields.html.twig

	#修改 
	{% set attr = attr | merge({class:'g-recaptcha' , 'data-sitekey':key , 'data-callback':'' }) %} 

config\packages\recaptcha.yaml

```
services:
  recaptcha.type : #定义一个名为 recaptcha.type 的服务
    class: MyLib\RecaptchaBundle\Type\RecaptchaSubmitType # 定义要载入的class
    tags: ['form.type']
    arguments:
      $key: '6LeIohoUAAAAAOtXJI_WbAwVoPiALQcg3q2JKiKX'
 ```
