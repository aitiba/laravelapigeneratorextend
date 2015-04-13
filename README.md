# laravelapigeneratorextend
Laravel API Generator Extend

Steps to Get Started
---------------------

1. Add this package to your composer.json:
  
        "require": {
            "aitiba/laravelapigeneratorextend": "dev-master"
        }
  
2. Run composer update

        composer update
    
3. Add the ServiceProviders to the providers array in ```config/app.php```.<br>
   As we are using these two packages [illuminate/html](https://github.com/illuminate/html) & [laracasts/flash](https://github.com/laracasts/flash) as a dependency.<br>
   so we need to add those ServiceProviders as well.

        'Illuminate\View\ViewServiceProvider',
        'Illuminate\Html\HtmlServiceProvider',
        'Laracasts\Flash\FlashServiceProvider',
        'Mitul\Generator\GeneratorServiceProvider',
        'Pingpong\Modules\ModulesServiceProvider',
        'Aitiba\LaravelApiGeneratorExtend\Generator\GeneratorServiceProvider',

   Also for convenience, add these facades in alias array in ```config/app.php```.

        'Module'=> 'Pingpong\Modules\Facades\Module',
		'Form'  => 'Illuminate\Html\FormFacade',
		'HTML'  => 'Illuminate\Html\HtmlFacade',
		'Flash' => 'Laracasts\Flash\Flash'

4. Publish ```generator.php```

        php artisan vendor:publish --provider="Mitul\Generator\GeneratorServiceProvider"

5. Fire artisan command to generate API, Scaffold with CRUD views or both API as well as CRUD views.

        php artisan mitul.generator:api ModelName
        php artisan mitul.generator:scaffold ModelName
        php artisan mitul.generator:scaffold_api ModelName
        php artisan mitul.generator:scaffold_api ModelName
        php artisan mitul.generator:module_model ModuleName ModelName
        
    e.g.
    
        php artisan mitul.generator:api Project
        php artisan mitul.generator:api Post
 
        php artisan mitul.generator:scaffold Project
        php artisan mitul.generator:scaffold Post
 
        php artisan mitul.generator:scaffold_api Project
        php artisan mitul.generator:scaffold_api Post

        php artisan mitul.generator:module_model Network Project
        php artisan mitul.generator:module_model Blog Post
 
6. If you want to use SoftDelete trait with your models then you can specify softDelete option.
 
        php artisan mitul.generator:api ModelName --softDelete
        
    e.g.
    
        php artisan mitul.generator:api Post --softDelete
        
7. Enter the fields with options<br>

8. And you are ready to go. :)