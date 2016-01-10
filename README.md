# NodeJs
### NodeScholl - Estudos

# Express + Jade

### Adicionando uma página

Precisa fazer uma rota e adicionar um view. A rota é criada no arquivo padrão index.js
<i>routes/index.js</i>

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

Agora que já tem a rota, precisa de um view
<i>views/helloworld.jade</i>

<code>
    extends layout
    
    block content
      h1= title
      p Hello, World! Welcome to #{title}
</code>
