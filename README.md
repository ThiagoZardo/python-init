# python-init

## 1- Criar pasta tests

## 2- Criar pasta src

## 3- Criar arquivos de dependencias
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
