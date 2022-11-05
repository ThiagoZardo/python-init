# Iniciar um projeto web em Python

## 1- Criar pasta tests

## 2- Criar pasta src

## 3- Criar arquivos de dependencias na raiz
  - requiriments.txt ==> dependencias que serão usadas em produção.
  ```
  -r requirements.txt
  flake
  black
  pytest
  uvicorn
  ```
 
  - dev-requiriments.txt ==> dependencias que serão usadas em desenvolvimento.
  ```
  fastapi==0.85.2
  sqlmodel==0.0.8
  ```
  
  - Criar ambiente virtual e instalar os pacotes
  ```
  # No terminal
  python3 -m venv .venv
  source .venv/bin/activate
  python3 -m pip -r dev-requiriments.txt
  ```
## 4- Dentro de src Criar arquivo main.py
  ```
  from fastapi import FastApi
  
  app - FastApi()
  
  # para iniciar essa app no terminal digite: uvicorn src.main:app --reload
  # por padrão o endereço de acesso será localhost:8000
  # acessar a documentação utilizando localhost:8000/docs
  @app.get('/')
  async def root():
      return {"message": "Online"}
  ```
## 5- Dentro de src Criar arquivo model.py
```
from typing import Optional
from sqlmodel import SQLModel


class Task(SQLModel, table=True):
    id: Optional[int] = Field(default=None, primary_key=True)
    title: str
```

## 6- Dentro de src Criar arquivo db.py
```
from sqlmodel import create_engine, SQLModel

sqlite_file_name = "database.sqlite"
sqlite_url = f"sqlite:///{sqlite_file_name}"

connect_args = {"chec_same_thred": False}
create_engine(sqlite_url, echo=True, connect_args=connect_args)

SQLModel.metadata.create_all(engine)
```







