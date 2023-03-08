# googlecolabXvscode

using vscode in google colab

**Colab** notebook: &nbsp;&nbsp; [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/asifajrof/googlecolabXvscode/blob/main/files/googlecolabXvscode.ipynb)


## installation

we need [`colabcode`](https://github.com/abhishekkrthakur/colabcode), but as of now, google colaboratory does not support the use of it. you will see a warning if you want to install `colabcode`.

![colab-warning.svg](/imgs/colab-warning.svg)

### the workaround

put the install command in a [file](/files/install-colabcode), run that file from colab. apparently they are dumb like that.

```bash
wget "https://raw.githubusercontent.com/asifajrof/googlecolabXvscode/main/files/install-colabcode"
bash install-colabcode
```

## ngrok setup

### signup

register an account at [ngrok](https://ngrok.com/signup).

### get authtoken

after signing up, get your authtoken from [your dashboard](https://dashboard.ngrok.com/get-started/your-authtoken).

### setup config

put your authtoken in [`ngrok.yml`](/files/ngrok.yml) file.

```bash
wget "https://raw.githubusercontent.com/asifajrof/googlecolabXvscode/main/files/ngrok.yml"
```

```bash
mkdir -p ~/.ngrok2/
mv ngrok.yml ~/.ngrok2/ngrok.yml
```

## run vscode in google colaboratory

```python
from colabcode import ColabCode
ColabCode(port=1234, password="googlecolabXvscode", mount_drive=True)
```
