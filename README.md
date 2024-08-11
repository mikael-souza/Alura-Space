## Alura-Space
> O Django é uma ótima ferramenta para o front-end e back-end trabalharem e se comunicarem em sintonia.
# Arquitetura 
<small>Separação das responsabilidades das diferentes partes do sistema</small> </br> 

<b>Duas aplicações distintas:</b> </br>
🪲 Galeria - Inserção de novas fotografias; <br/>
🪲 Users - Processos relativos aos usuários (cadastro, login e autenticação).

# Ambiente de desenvolvimento

## IDE
<img src="https://user-images.githubusercontent.com/87834766/235193658-b384ad55-57d4-4079-9d5a-8eff514401c0.svg" widht="30" height="30" /> Vscode


## Extensões 
SQlite Viewer - [Florian Klampfer](https://qwtel.com/)

## Linguagem
<img src="https://user-images.githubusercontent.com/87834766/235193947-7bdec81d-5a8f-47dd-8357-ea90f1b5b353.svg" widht="30" height="30" />  Python **3.10.9**


### Instalação Pip 
(Sistema utilizado: Windows)
```
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
```
```
python get-pip.py 
``` 
### Ambiente Virtualizado 
[virtualenv](https://github.com/pypa/virtualenv)
```
pip install virtualenv
```
# Virtualenv
``` 
python3 --version
virtualenv --version
```

```
venv/Scripts/Activate 
``` 
```
pip install django
```
# Servidor
>  Visualizar todas as dependências do projeto e os módulos que precisam ser instalados para que o projeto funcione: 
```
pip freeze 
```
<small>
Informa a versão de <b>Django, sqlparse, sgireft</b></small>

>asgiref==3.6.0
Django==4.2
sqlparse==0.4.3
tzdata==2023.3
> 
Execute o comando: 
```
pipfreeze > requiriments.txt 
```

# Setup
~~~
Django-admin startproject setup . 
~~~

~~~
pip install -r requirements.txt
~~~

## manage.py
Responsável por realizar a maioria dos comandos que utilizaremos para o desenvolvimento de aplicações Django e também por subir servidores.
 <br />

~~~
python manage.py runserver 
~~~
## Configuração do interpretador no VS Code 
<small>O python que instalmos na virtualenv</small>
"CTRL + SHIFT + P" --> Pesquisar "Interpretador" e selecionar <b>python:selecionar interpretador</b> --> <b>Insira o caminho do interpretador</b>  e depois em <b>localizar...</b>.
Navegando até <mark>alura_space > .venv > Scripts</mark>, selecione o arquivo <code>python.exe</code> e clique em <b>Selecionar interpretador</b>


# Idioma Principal e Fuso Horário
**setup > setting.py** 
## setting.py 
Arquivo que contém todas as configurações do projeto
- dependências;
- <i>templates</i>;
- e mais. <br/>

Linhas 106 e 108 - <i>LANGUAGE_CODE</i> e <i>TIME_ZONE</i>

# Versionamento
Dependência python-dotenv
```
pip install python-dotenv
pip freeze > requirements.txt
```
# Criação do primeiro app
```
python manage.py startapp galeria 
```

~~~
INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'galeria', <-- o app que acabamos de criar!
~~~
# Persistência de dados e Admin
~~~
python manage.py makemigrations
python manage.py migrate
~~~

## Criando Dados
Para adicionar um item 
~~~
python manage.py shell 
~~~
Para importar photography 
~~~
from galeria.models import photography
~~~
Após importar, a criação do dado:
~~~
picture = photography(name="NOME_DA_FOTOGRAFIA, legend="LEGENDA_DA_FOTOGRAFIA")
~~~
Para salvar
~~~
picture.save() 
~~~
Exibir os objetos criados no <i>model</i> de photography
~~~
photography.objects.all() 
~~~
## Criação do Administrator
~~~
python manage.py createsuperuser 
~~~
# Autenticação de formulários e alerta
<b>Funcionalidades de login e de cadastro de novas pessoas com o banco de dados interno do Django, utilizando o <i>users</i> do Django admin. Será aplicado também uma regra de negócio: apenas pessoas cadastradas podem visualizar a galeria da página inicial.</b>


# Instrutor
[Guilherme Lima](https://cursos.alura.com.br/user/guilhermelima) e [Bruno Divino](https://github.com/BrunoDivino) </br>
![django](https://maxmautner.com/public/images/django.gif)
