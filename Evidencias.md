# Evidencias

## Instalación

Una vez instalado xampp, laravel y composer confirmar que se encuentran en el PATH

**Laravel**

![laravel version](images/laravel-v.PNG)

**Composer**

![composer version](images/Composer-v.PNG)

**PHP**

![php version](images/php-v.PNG)

**Creación del proyecto**

Para crear la aplicación se debe escribir en en la ventana de comandos la instrucción **laravel new [nombre de applicacion]**

![laravel-new-blog](images/laravel-error.PNG)

Para corregir este error se debe modificar el archivo php.ini ubicado en la dirección C:\xampp\php\windowsXamppPhp\php.ini. 
Para ver la ubicación puede usar el comando php --ini

![php-ini-address](images/php-ini-address.PNG)

Una vez abiero el archivo debe revisar que la linea extension=fileinfo no esté comentada, no tenga ';'.

![php-fix](images/laravel-fix.PNG)

Después de esto deberíamos poder construir nuestra aplicación sin problemas

![app-ready](images/app-ready.PNG)

Podemos ver los archivos creados desde el browser, para eso debemos iniciar Apache en xampp

![localhost-blog](images/localhost-blog.PNG)

Para ver la aplicación que fue creada accedemos a la carpeta public

![localhost-public](images/localhost-public.PNG)

**Creación y manipulación de rutas**

Desde la carpeta routes dentro de nuestra aplicación, podemos encontrar el archivo web.php, en este archivo definiremos las rutas a las que el usuario puede acceder
Las rutas nos permiten mantener partes de nuestra aplicación fuera del alcance de los usuarios y también permiten al usuario navegar por aquellas partes que estén permitidas.

el archivo web.php contiene una ruta que nos dirige a la vista welcome

![route-welcome](images/route-welcom.PNG)

Modifique este archivo para incluir diferentes rutas, para esto cree una función get de la clase Route que acepta como parametros un subdiretorio seguido de '/' y las variables que el usuario pondrá en el URL entre '{}', después una función anónima que acepta estas variables, dentro de esta última se pueden realizar las operaciones que se desee. Este método no es el correcto para laravel, solo es un ejemplo de como pueden crearse más rutas.

![route-basicMath](images/route-basicMath.PNG)

**Suma**

![route-suma](images/route-suma.PNG)

**Resta**

![route-resta](images/route-resta.PNG)

**Multiplicación**

![route-multiplicacion](images/route-multiplicacion.PNG)

**División**

![route-division](images/route-division.PNG)

La forma correcta de hacer esto es usando controladores, podemos crear controladores de manera sencilla desde la ventana de comandos
con la instrucción 'php artisan make:controller BasicMathController'

![controller-math](images/controller-math.PNG)

Esto puede simplificarse usando la función group

![controller-group](images/controller-group-fix.PNG)
