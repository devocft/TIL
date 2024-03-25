# Create Virtual Environment

**V**irtual **Env**ironment(**venv**)

**_Create_** venv
```shell
python -m venv venv
```

**_Activate_** venv
```shell
source venv/Scripts/Activate
```

**_Deactivate_** venv
```shell
deactivate
```

Install **_dependencies_**
```shell
pip install -r requirements.txt
```

Create `requirements.txt`
```shell
pip freeze > requirements.txt
```

[source](https://docs.python.org/ko/3/library/venv.html)