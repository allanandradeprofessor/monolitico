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

## Ver versão instalada:

    django-admin --version


## Criar um projeto Django

    django-admin startproject meu_projeto

    python -m django startproject config .


## Entrar na pasta:

    cd meu_projeto

## Rodar o servidor

    python manage.py runserver

## Servidor padrão:

    http://127.0.0.1:8000/

**Rodar em outra porta**:

    python manage.py runserver 8080

## Criar um app

    python manage.py startapp meu_app



Depois adicione no settings.py:

INSTALLED_APPS = [
    ...
    'meu_app',
]

Criar Classe

from django.db import models


class Tarefa(models.Model):

    STATUS_CHOICES = [
        ("nao_iniciado", "Não iniciado"),
        ("aprovado", "Aprovado"),
        ("paralisado", "Paralisado"),
        ("finalizado", "Finalizado"),
    ]
    # nao precisa colocar a ID
    nome = models.CharField(max_length=100)
    descricao = models.TextField()
    data_inicio = models.DateField()

    status = models.CharField(
        max_length=20,
        choices=STATUS_CHOICES,
        default="nao_iniciado"
    )

    def __str__(self):
        return self.nome

## Criar migrations:

    python manage.py makemigrations

## Aplicar no banco:

    python manage.py migrate


## Criar superusuário (admin)
    
    python manage.py createsuperuser

## Adicionar Tarefa ao Admin

    from django.contrib import admin
    from .models import Tarefa

    admin.site.register(Tarefa)

Painel admin:

http://127.0.0.1:8000/admin
