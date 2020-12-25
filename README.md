# Provisionar um servidor web com Nginx, PHP e MySQL com Ansible

Esse repositório faz parte de um [artigo publicado](https://aristides.dev/ansible-provisionando-um-servidor-web-com-nginx-php-e-mysql) no meu blog.

## O que esse script faz?

Provisiona um servidor web com os seguintes serviços.

- Nginx
- PHP 7.4
- MySQL 5.7 (Ubuntu 18.04) / Mysql 8.0 (Ubuntu 20.04)

Ao final do provisionamento você terá um servidor web completo e uma página web criada que acessa o banco de dados que foi importado durante o processo.

## Passos

### MySQL

- Instalação do MySQL
- Configuração da senha de root
- Criação de usuários
- Criação de banco de dados
- Importação de dois arquivos .sql

### Nginx

- Instalação do Nginx
- Criação de um arquivo vhost de configuração
- Criação de uma página feita em PHP que acessa os dados do banco de dados e lista

### PHP

- Instalação do PHP 7.4
- Configuração e otimização do arquivo `php.ini`
  - Timezone
  - Upload
  - Memory limit
  - entre outras...

Após o término você pode acessar a aplicação no browser pelo endereço IP que foi disponibilizado pelo seu Cloud.