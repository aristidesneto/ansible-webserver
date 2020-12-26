# Provisionando um servidor web com Nginx, PHP e MySQL com Ansible

Esse repositório faz parte de um [artigo publicado](https://aristides.dev/ansible-provisionando-um-servidor-web-com-nginx-php-e-mysql) no meu blog.


## Como usar?

> Necessário ter o Ansible instalado em sua máquina local.

Execute os comandos abaixo:

```
git clone https://github.com/aristidesneto/ansible-webserver.git ~/ansible-webserver && cd ~/ansible-webserver
```

Crie uma VPS em um provedor como AWS, Digital Ocean, Linode. Abra o arqivo `hosts` e adicione o IP que o seu Cloud criou para sua VPS.

```
[webserver]
192.168.10.100 ansible_user=root ansible_python_interpreter=/usr/bin/python3
```

Execute o playbook do Ansible

```
time ansible-playbook -i hosts start-server.yml
```

## Suporte

Funciona nas distribuições Ubuntu 18.04, 20.04, Debian 9 e 10

## O que esse script faz?

Provisiona um servidor web com os seguintes serviços.

- Nginx
- PHP 7.4
- MySQL 5.7 (Ubuntu 18.04) / Mysql 8.0 (Ubuntu 20.04)
- MariaDB (Debian)

Ao final do provisionamento você terá um servidor web completo e uma página web criada que acessa o banco de dados que foi importado durante o processo.

## Roles

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

