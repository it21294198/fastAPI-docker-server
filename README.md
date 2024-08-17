## Setup FastAPI server for Docker Image

[Read More](https://fastapi.tiangolo.com/deployment/docker/#one-process-per-container)

1. file and folder structure

```
server/
│
├── app/
│   └── __init__.py
|   |__ main.py
│
└── project_env/
│
└──requirement.txt
│
└──Dockerfile
```

1. Create virtual environment(for first time setup)
    ```
    virtualenv project_env
    ```

2. If clone from git(if above doesn't work)

    ```
    python3 -m venv project_env
    ```
   
3. Run virtual environment

    Windows
    ```
    project_env\Scripts\activate
    ```

    Unix or MacOS
    ```
   source project_env/bin/activate
    ```

   * Run this to stop virtual environment.

    ```
    deactivate
    ```

4. Install FastAPI(add here if when new lib is added)

    ```
    pip3 install fastapi pydantic opencv-python-headless numpy aiofiles
    ```

5. Run server

    ```
    fastapi dev main.py
    ```

6. Add all dependencies

```
pip install fastapi pydantic
```
or
```
pip3 install fastapi pydantic
```

7. Create a `requirements.txt` File

```
pip freeze > requirements.txt
```

8. To build the Docker image, run:

```
docker build -t myfastapiapp .
```

9. To run the container:

```
docker run -d --name myfastapiapp -p 8000:8000 myfastapiapp
```

10. If using `docker-compose`,

```
docker-compose up --build
```

[http://localhost:8000](http://localhost:8000)

[http://localhost:8000/docs](http://localhost:8000/docs)