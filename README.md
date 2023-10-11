# PC2 - Parte 3

Creamos la aplicación de rails

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image1.png)

Vemos que se crea la estructura del proyecto y empieza a ejecutarse el bundle install

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image2.png)

Cambiamos la versión del SQLite3 a 1.3.0 y actualizamos

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image3.png)

Corremos el servidor
Ahora vemos que nos muestra la página por defecto

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image4.png)

Ahora crearemos la base de datos usando el sistema de migraciones proporcionado por rails, el cual es rake
Usamo el comando ‘rails generate migration create_movies’ y vemos que nos genera un archivo en db/migrate

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image5.png)

En el  archivo creado creamos la clase CreateMovies

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image6.png)
![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image7.png)

Vemos que da error debido a que nos pide que especifiquemos la versión de Migration a usar

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image8.png)

Ahora observamos y vemos que la migración se ejecutó correctamente.
Y nos generó el siguiente archivo db/schema.rb

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image9.png)

Creamos el archivo app/models/movie.rb

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image10.png)

Ahora al usar el REPL de rails observamos que podemos instanciar una nueva clase Movie

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image11.png)

Como la base de datos aún está vacía obtenemos nil al querer obtener el primer elemento de la tabla Movie

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image12.png)

Copiamos el código dentro de seeds.rb y usaremos el comando ‘rake db:seed’ para llenar la tabla con datos iniciales

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image13.png)

Como ya llenamos la tabla, ahora al llamar a Movie.first desde la consola de rails, nos devolverá el primer elemento de la tabla

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image14.png)

Ahora crearemos rutas, si vamos al localhost:3000/movies, rails nos dirá que la ruta especificada no existe

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image15.png)

Ahora especificamos la ruta /movies y recargamos la página

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image16.png)
![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image17.png)

Ahora vemos que nos da un error distinto, ya que está buscando el MoviesController, así que nuestra ruta ya funciona.
Ahora para crear el controlador usamos el siguiente comando ‘rails g scaffold_controller Movie title rating description release_date --skip-test’

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image18.png)

Actualizamos las dependencias

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image19.png)

Y vemos que ya corre localmente

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image20.png)

Finalmente conectamos a postgresql para poder correr la aplicación en producción.
Ahora desplegamos la aplicación en heroku

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image21.png)

También podemos agregar más películas y mostrarlas

![img](https://github.com/chandler-pc/rottenpotatoes---PC2/blob/main/images/image22.png)

El proyecto desplegado está en https://thawing-fjord-84712-2c2d0034563e.herokuapp.com/movies
