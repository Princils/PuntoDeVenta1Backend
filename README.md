## Aprende a usar la Api
Para el correcto uso de la api es nesesario tener instalado 
- Composer [Instalación de Composer](https://getcomposer.org/Composer-Setup.exe) 
- node.js  [Instalación de NodeJS](https://nodejs.org/dist/v20.15.0/node-v20.15.0-x64.msi)
- Es nesesario tener instalado NPM en caso de que nodejs no lo installe solo
- Larael global usando el siguiente comando -- <b>composer global require laravel/installer</b>

## El laravel que usa la api es <b>LARAVEL 8</b>


Para inicializar el vendor de laravel usa
- <b>npm i</b>

Crear proyecto Laravel
- laravel new example-app

crear proyecto laravel 8
- composer create-project --prefer-dist laravel/laravel:^8.x yutub-rest

Correr un proyecto, Entrar a la carpeta y poner
- php artisan serve

Migrar tablas
- php artisan migrate

Crear seeder para registros de prueba
- php artisan make:seeder nombreSingularSeeder

Desplegar seeder
- php artisan db:seed

Crear modelo
- php artisan make:model nombreModelo

Crear un controlador
- php artisan make:controller carpeta/nombreControlador

Controlador pero indicandole que queremos la estructura para una API
- php artisan make:controller carpeta/nombreControlador --api

Crear un request
- php artisan make:request nombreRequest

## Para manejo de errores comunes
Cuando hay errores con las peticiones hay que entrar a la ruta, normalmente este error lo vamos a conocer cuando intentamos insertar con el update, Va dar un error de csfr o algo asi de un token hay que lo siguiente.

- Hay que buscar esta ruta en el proyecto
- nombreProyecto\vendor\laravel\framework\src\Illuminate\Foundation\Http\Middleware\Veril,afyCsrfToken.php


buscar la siguiente funcion y agregarle los metodos al array normalmente nomas trae , head get y option <br>
    protected function isReading($request) <br>
    { <br>
        return in_array($request->method(), ['HEAD', 'GET', 'OPTIONS', 'POST', 'PUT', 'DELETE']); <br>
    } <br>


Crear un recurso
- php artisan make:resource NombreResource

Handler para errores esta en la siguiente carpeta el vato en el curso lo tiene en otro
- nombreProyecto\vendor\laravel\framework\src\Illuminate\Foundation\Exceptions\Handler.php
