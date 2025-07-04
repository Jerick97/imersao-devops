# Imersão DevOps - Alura Google Cloud

Este projeto é uma API desenvolvida com FastAPI para gerenciar alunos, cursos e matrículas em uma instituição de ensino.

## Pré-requisitos

- [Python 3.10 ou superior instalado](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)
- [Docker](https://www.docker.com/get-started/)

## Passos para subir o projeto

1. **Faça o download do repositório:**
   [Clique aqui para realizar o download](https://github.com/guilhermeonrails/imersao-devops/archive/refs/heads/main.zip)

2. **Crie um ambiente virtual:**
   ```sh
   python3 -m venv ./venv
   ```

3. **Ative o ambiente virtual:**
   - No Linux/Mac:
     ```sh
     source venv/bin/activate
     ```
   - No Windows, abra um terminal no modo administrador e execute o comando:
   ```sh
   Set-ExecutionPolicy RemoteSigned
   ```

     ```sh
     venv\Scripts\activate
     ```

4. **Instale as dependências:**
   ```sh
   pip install -r requirements.txt
   ```

5. **Execute a aplicação:**
   ```sh
   uvicorn app:app --reload
   ```

6. **Acesse a documentação interativa:**

   Abra o navegador e acesse:  
   [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

   Aqui você pode testar todos os endpoints da API de forma interativa.

---

## Estrutura do Projeto

- `app.py`: Arquivo principal da aplicação FastAPI.
- `models.py`: Modelos do banco de dados (SQLAlchemy).
- `schemas.py`: Schemas de validação (Pydantic).
- `database.py`: Configuração do banco de dados SQLite.
- `routers/`: Diretório com os arquivos de rotas (alunos, cursos, matrículas).
- `requirements.txt`: Lista de dependências do projeto.

---

- O banco de dados SQLite será criado automaticamente como `escola.db` na primeira execução.
- Para reiniciar o banco, basta apagar o arquivo `escola.db` (isso apagará todos os dados).

---

## 🚀 Ejecutar con Docker

Si prefieres usar Docker en lugar de instalar dependencias localmente, puedes levantar la aplicación con los siguientes pasos:

1. Asegúrate de tener Docker instalado:  
   [Instalar Docker](https://www.docker.com/get-started/)

2. En la raíz del proyecto, ejecuta el siguiente comando para construir y levantar el contenedor en segundo plano:

```bash
docker compose up -d
```

> Este comando:
> - Construye la imagen definida en el `Dockerfile`.
> - Inicia el contenedor exponiendo la aplicación en el puerto `8000`.
> - Monta tu código local en el contenedor para reflejar cambios automáticamente (gracias al `--reload` de Uvicorn).

3. Accede a la API desde tu navegador en:  
[http://localhost:8000/docs](http://localhost:8000/docs)


## Autenticando no Google Cloud
```bash
gcloud auth login
gcloud config set project Project_id
gcloud run deploy --port=8000
```