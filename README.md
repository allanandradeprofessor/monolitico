## App MinhasTarefas

Monolitico
-> Django

Backend
-> Node 

Frontend
-> React





## python

# verificar versao do python
python --version



# Criar o ambiente virtual
python -m venv env

# Ativar o ambiente
env/scripts/activate


-> cada projeto um ambiente


## Criar um arquivo .gitignore

-> nao versionar banco, variaveis sensiveis, dados


-> em python, o gerenciador de pacotes mais comumente utilizado
é o ´pip´


### Comandos basicos de Django

## Instalar Django
pip install django



Ver versão instalada:

django-admin --version
Criar um projeto Django
django-admin startproject meu_projeto

Entrar na pasta:

cd meu_projeto
Rodar o servidor
python manage.py runserver

Servidor padrão:

http://127.0.0.1:8000/

Rodar em outra porta:

python manage.py runserver 8080
Criar um app
python manage.py startapp meu_app

Depois adicione no settings.py:

INSTALLED_APPS = [
    ...
    'meu_app',
]
Criar migrations

Gerar migrations:

python manage.py makemigrations

Aplicar no banco:

python manage.py migrate

Ver status das migrations:

python manage.py showmigrations
Criar superusuário (admin)
python manage.py createsuperuser

Painel admin:

http://127.0.0.1:8000/admin
Shell do Django
python manage.py shell
Coletar arquivos estáticos
python manage.py collectstatic
Criar arquivo requirements.txt
pip freeze > requirements.txt

Instalar dependências depois:

pip install -r requirements.txt