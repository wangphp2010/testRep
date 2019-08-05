#### 总结 

	1. config\packages\recaptcha.yaml 定义 值 
	2. lib\RecaptchaBundle\Resources\config\services.yaml 获取上面定义的值 给某个类的构造函数 传入这个 参数 
	3. lib\RecaptchaBundle\DependencyInjection\RecaptchaExtension.php 使用上面两个个yaml文件,ps这个文件会自动调用  
	4. 使用方法 , 在某个类的构造函数传入这个参数 如 
```php
public function __construct(string $key )
{
	$this->key = $key ;
}
```	
