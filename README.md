lib\RecaptchaBundle\Type\RecaptchaSubmitType.php

```php

增加 
/**
* @var string
*/
private $key ;

public function __construct(string $key )
{
$this->key = $key ;
}



	
public function buildView(FormView $view, FormInterface $form, array $option    )
{
    $view->vars["label"] = false;  # 不显示label 
    $view->vars["key"] =  $this->key ;   增加这一行	 
    $view->vars["button"] = $option['label'] ; 
}	

```
