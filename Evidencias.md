# Evidencias

## Video 2

### Creación del proyecto

Una vez instalado xampp, laravel y composer confirmar que se encuentran en el PATH

**Laravel**

![laravel version](images/laravel-v.PNG)

**Composer**

![composer version](images/Composer-v.PNG)

**PHP**

![php version](images/php-v.PNG)

Para crear la aplicación se debe escribir en en la ventana de comandos la instrucción **laravel new [nombre de applicacion]**

![laravel-new-blog](images/laravel-error.PNG)

Para corregir este error se debe modificar el archivo php.ini ubicado en la dirección C:\xampp\php\windowsXamppPhp\php.ini. 
Para ver la ubicación puede usar el comando php --ini

![php-ini-address](images/php-ini-address.PNG)

Una vez abiero el archivo debe revisar que la linea extension=fileinfo no esté comentada, no tenga ';'.

![php-fix](images/laravel-fix.PNG)
