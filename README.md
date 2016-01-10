# NodeJs
### NodeScholl - Estudos

# Express 

### Adicionando uma página

Precisa fazer uma rota e adicionar um view. A rota é criada no arquivo padrão index.js - <i>routes/index.js</i>

    var express = require('express');
    var router = express.Router();
    
    /* GET home page. */
    router.get('/', function(req, res) {
        res.render('index', { title: 'Express' });
    });
    router.get('/helloworld', function(req, res) {
        res.render('helloworld', { title: 'Hello, World!' });
    });
    module.exports = router;


Agora que já tem a rota, precisa de um view - <i>views/helloworld.jade</i>

    extends layout
    
    block content
      h1= title
      p Hello, World! Welcome to #{title}

## Express + MongoDb

### Comandos
<!-- C:\Program Files\MongoDB\Server\3.0\bin -->

Abrir a prompt é digitar

<code>
    mongod --dbpath c:\node\express_example\data\
</code>
<!--express_example - Arquivo padrão criado - porem a pasta data deve ser criada-->

Abrir uma segunda prompt de comando e digitar
<!-- C:\MONGO\BIN\ -->
<code>
mongo
</code>

<strong>Mongo Console</strong>

Apontando 

<code>
    use express_example
</code>

Adicionando um usuário - Insert

<code>
    db.usercollection.insert({ "username" : "usuario", "email" : "usuario@gmail.com" })
</code>

Localizando usuário adicionado

<code>
    db.usercollection.find().pretty()
</code>

Adicionando vários usuários - array

    newstuff = [{ "username" : "usuario2", "email" : "usuario2@dominio.com" }, { "username" : "usuario3", "email":usuario3@dominio.com"}]
    db.usercollection.insert(newstuff);

#### Iniciando uma aplicação com express + jade + mongodb

Va no diretório de express_example,no arquivo app.js lá no topo
    
    var express = require('express');
    var path = require('path');
    var favicon = require('serve-favicon');
    var logger = require('morgan');
    var cookieParser = require('cookie-parser');
    var bodyParser = require('body-parser');

Adicione o código abaixo

    var express = require('express');
    var path = require('path');
    var favicon = require('serve-favicon');
    var logger = require('morgan');
    var cookieParser = require('cookie-parser');
    var bodyParser = require('body-parser');
    
    // Codigo adicionado
    var mongo = require('mongodb');
    var monk = require('monk');
    var db = monk('localhost:27017/nodetest1');


