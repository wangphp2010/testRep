lib/RecaptchaBundle/RecaptchaBundle.php
```
 #增加 
 public function build(ContainerBuilder $container)
    {
        parent::build($container);
        $container->addCompilerPass(new RecaptchaCompilerPass());
    }
```

lib\RecaptchaBundle\RecaptchaCompilerPass.php
```php
namespace MyLib\RecaptchaBundle;

use Symfony\Component\DependencyInjection\ContainerBuilder ;
use Symfony\Component\DependencyInjection\Compiler\CompilerPassInterface ;

class RecaptchaCompilerPass implements CompilerPassInterface{

    public function process(ContainerBuilder $container){

        if($container->hasParameter("twig.form.resources"))
        {
            $resources = $container->getParameter("twig.form.resources")?: [] ;

            array_unshift($resources , '@Recaptcha/fields.html.twig' ) ;
            $container->setParameter( "twig.form.resources", $resources ) ;
        }
            
        
    }
}
