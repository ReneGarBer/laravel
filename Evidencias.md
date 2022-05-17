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

## Creación y manipulación de rutas

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

## Vistas y Blade

El propósito de los controladores es dirigir al usuario a las vistas que conforman nuestra pagina web,
para lograr esto debemos primero crear las vistas en la carpeta 'resources\views' aqui crearemos una carpeta basicMath
dentro de esta crearemos los archivos 'suma.blade.php','resta.blade.php','multiplicacion.blade.php','division.blade.php'.
Tambien crearemos una carpeta 'layouts' en la dirección 'resources\views' y dentro crearemos el archivo 'Math.blade.php'

La extensión '.blade' en nuestros archivos '.php' permite usar una sintaxis que reduce el código php que usamos dentro del codigo html

**Suma y Resta**

![views-suma-resta](images/views-suma-resta.PNG)

**Multiplicación y División**

![views-multiplicacion-division-fix](images/views-multiplicacion-division-fix.PNG)

Estos archivos contiene solo las carácterísticas que los hacen únicos, aquellas elementos y atributos que todos comparten se encuentran en
el archivo Math.blade.php' que funciona como un tamplate para nuestas vistas.

**Math.blade.php**

![views-layout](images/views-layout.PNG)


## Generar un dominio local con xampp

Para generar un dominio local deben modificarse los archivos 'httpd-vhosts.conf', ubicado en la dirección 'C:\xampp\apache\conf\extra' y 'hosts', 
ubicado en la dirección 'C:\Windows\System32\drivers\etc'. Después de los deben verse así

**httpd-vhosts.conf**

![vhosts](images/vhosts.PNG)

**hosts**

![hosts](images/host.PNG)

Después de reiniciar xampp podremos acceder a nuestra aplicacion escribiendo 'blog.test' en nuestro buscador.

**URL -blog.test-**

![blog.test](images/blog-test.PNG)

## Trabajando con bases de datos y migraciones

Para trabajar con una base de datos primero tenemos que crearla, debemos acceder a phpmyadmin de nuestra aplicacion, dar click en Nueva y seguir los pasos indicados.
Es importante recordar el nombre de la base de datos, y por razones de seguridad crear un usuario diferente al usuario por defecto y asignarle una contraseña segura

**phpMyAdmin**

![phpmyadmin](images/phpmyadmin.PNG)

**Creación de tablas usando migraciones**

Para este ejemplo usaremos las migraciones que crea laravel al crear el proyecto.

![migraciones](images/migrations.PNG)

Para crear las tablas usamos el comando 'php artisan migrate'

![error-mysql](images/pdo-mysql-error.PNG)

Si aparece el error anterior una posible solución es la siguiente. Ir al archivo C:\xampp\php\windowsXamppPhp\php.ini y asegurarse que la linea con 
la extensión del pdo que corresponde a la base de datos usada. 

![pdo-mysql-fix](images/pdo-mysql-fix.PNG)

Después de hacerlo las tablas pueden ser creadas

![migrate](images/migrate.PNG)

**Base de datos después de crear las tablas**

![db-with-tables](images/db-with-tables.PNG)
