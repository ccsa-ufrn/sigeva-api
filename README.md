# sigeva/api
API provedor de dados para a aplicação Sistema de Gestão de Eventos Acadêmicos.

![Node](https://img.shields.io/badge/Node.js-v7.0.0-green.svg)
![NPM](https://img.shields.io/badge/npm-v3.10.8-blue.svg)
![Express](https://img.shields.io/badge/Express-v4.14.0-lightgrey.svg)
![MongoDB](https://img.shields.io/badge/MongoDB-v3.2.9-green.svg)
![Python](https://img.shields.io/badge/Python-v2.7-green.svg)

## Instalação
Antes de iniciar realmente a instalação do 'sigeva-api', é necessário que uma versão
do **Python 2.7** esteja instalada na máquina que vai rodar o programa, pois
a biblioteca para a geração e verificação de hashs em **bcrypt** depende do Python.

Baixe o diretório ccsa-ufrn/sigeva-api.
```
# git clone https://github.com/ccsa-ufrn/sigeva-api.git
Mova-se para o diretório '/sigeva-api' e instale as dependências com NPM
```

# cd /path/to/sigeva-api
# npm install
```
Por fim, pode inicializar o serviço:
```
# npm start
```
Se nenhum erro for mostrado a instalação foi realizada com sucesso.

## Api
Para acessar a documentação completa da API do sigeva, [clique aqui](docs/README.md).

## Arquivo de Configuração
```javascript
{
    APP_NAME: "Sistema de Gestão de Eventos Acadêmicos", // Nome da aplicação
    SERVER_PORT: 3000, // Porta para iniciar o servidor express
    MONGO_DB_PRODUCTION: "mongodb://host/database", // Banco de dados de produção
    MONGO_DB_DEV: "mongodb://host/database_dev", // Banco de dados de desenvolvimento
    MONGO_DB_TEST: "mongodb://host/database_test", // Banco de dados de teste
    JWT_KEY: "secret_key", // Chave privada do JSON Web Token 
    HOST: "http://host:3000", // ?
    INTERNAL_HOSTS: ['host:port'] // ?
}
```

## Testando
Para testar, apenas rode:
```
npm start test // Inicia o servidor em modo desenvolvimento
npm run test
```

## Em produção
O sigeva utiliza o serviço PM2 da Keymetrics como gerenciador de processos Node.JS. ([Conheça aqui](http://pm2.keymetrics.io/)).

Em modo de produção, um único script é utilizado para fazer deploy e monitoramento de toda aplicação (sigeva-api). 
Para fazer deploy somente do core, execute os seguintes passos (com pm2 instalado):
```
# pm2 start process.yml --env [production|development]
```
O pm2 irá iniciar 4 instancias do core. Para monitorar em tempo real estas instâncias, informações de uso de memória 
e processamento execute:
```
pm2 monit
```
O resultado será parecido com este:

![](http://i.imgur.com/Qn7rcIA.png)

## Referências
 - [Protejendo a API com JWT](https://scotch.io/tutorials/authenticate-a-node-js-api-with-json-web-tokens)
 - [Assegurando informações via transações em JSON](http://security.stackexchange.com/questions/58965/securing-json-data)
 - [JWT](https://jwt.io/introduction/)
 - [Protocolo HTTP](https://tools.ietf.org/html/rfc7231#section-4.3)
 - [Frisbyjs to test rest api](http://frisbyjs.com/docs/api/)
 - [Upload Files - Angular 2](http://stackoverflow.com/questions/40214772/file-upload-in-angular-2)
