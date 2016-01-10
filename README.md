# NodeJs
### NodeScholl - Estudos

# Express 

### Adicionando uma página

Precisa fazer uma rota e adicionar um view. A rota é criada no arquivo padrão index.js - <i>routes/index.js</i>

<code>

    var express = require('express');
    var router = express.Router();

    /* GET home page. */
    router.get('/', function(req, res) {
        res.render('index', { title: 'Express' });
    });
    /* Pagina adicionada:  helloworld page. */
    router.get('/helloworld', function(req, res) {
        res.render('helloworld', { title: 'Hello, World!' });
    });
    module.exports = router;
</code>

Agora que já tem a rota, precisa de um view - <i>views/helloworld.jade</i>

<code>

    extends layout
    
    block content
      h1= title
      p Hello, World! Welcome to #{title}
</code>

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









