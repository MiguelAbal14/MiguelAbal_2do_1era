
<h1>Parcial Programación</h1>
<h2>Miguel Abal 2°1° </h2>

<h3> Pasos realizados </h3>


1.Con la carpeta del proyecto abierta en nuestro editor de texto, ejectuamos una consola y escribimos el comando  **npm init -y**<br>
2. Instalamos express  **npm i express**<br>
3. Instalamos la dependencia para manejar archivos de ambiente **npm i dotenv**<br>
4. Instalamos el orm en este caso sequelize y la dependencia para Mysql en la misma línea **npm i sequelize mysql2**<br>
5. Instalamos el manejador de líneas de comando del ORM como dependencia del desarollo **npm i sequelize-cli --D**<br>
6. Instalar nodemon globalmente para reiniciar la app más dinamicamente **npm i -g nodemon**<br>
7. Creamos en la raíz del proyecto la carpeta public y src, en esta última crear el archivo app.js asi como otras 2 carpetas llamadas "controller" y "routes".<br>
8. En la raíz del proyecto crear los archivos:<br><br>
                                                .gitignore (Ignorar los modulos al momento de subir el repo)<br>
                                                .env (variables de entorno)<br>
                                                .sequelizerc (Configuración del orm)<br>

configuración del .sequelizerc
```
const path = require('path')
module.exports = {
config: path.resolve('./src/database/config', 'config.js'),
'models-path': path.resolve('./src/database/models'),
'seeders-path': path.resolve('./src/database/seeders'),
'migrations-path': path.resolve('./src/database/migrations'),
}
```

Para que se produzcan los cambios del .sequelizerc ejecutar el comando **sequelize init**<br>

9. Empezar a crear los modelos<br>
```
sequelize model:generate --name Category --attributes name:string

sequelize model:generate --name Gender --attributes name:string

sequelize model:generate --name Brand --attributes name:string

sequelize model:generate --name Size --attributes name:string

sequelize model:generate --name Image --attributes name:string,url:string,description:string

sequelize model:generate --name State --attributes name:string

sequelize model:generate --name Role --attributes description:string

sequelize model:generate --name Province --attributes name:string

sequelize model:generate --name Address --attributes street:string,number:integer,state_id:integer

sequelize model:generate --name User --attributes first_name:string,last_name:string,username:string,email:string,password:string,address_id:integer

sequelize model:generate --name Payment --attributes type:string

sequelize model:generate --name Shipping --attributes type:string,date:date,address_id:integer

sequelize model:generate --name Order --attributes number:integer,date:date,user_id:integer,payment_id:integer,shipping_id:integer

sequelize model:generate --name Product --attributes name:string,price:decimal,brand_id:integer,category_id:integer,size_id:integer,gender_id:integer,image_id:integer

sequelize model:generate --name OrderDetail --attributes quantity:decimal,subtotal:decimal,order_id:integer,product_id:integer

sequelize model:generate --name UserRole --attributes user_id:integer,role_id:integer```


10. Se crearon las relaciones entre modelos. Para ver los detalles src/dabase/models/ <br>
11.Por último se ejecutó el comando **sequelize db:migrate** Para migrar la tabla como bien indica el nombre lol.

