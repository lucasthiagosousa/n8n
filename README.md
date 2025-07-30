## Instalação do Docker

Siga os passos abaixo para instalar o Docker no Debian:

1. Instale os pacotes necessários:

```sh
apt install -y apt-transport-https ca-certificates curl software-properties-common gnupg2
```

2. Adicione a chave GPG oficial do Docker:

```sh
curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

3. Adicione o repositório do Docker às fontes do APT:

```sh
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null
```

4. Atualize a lista de pacotes do APT e instale o Docker:

```sh
apt update
```
```sh
apt install -y docker-ce docker-ce-cli containerd.io
```

5. Verifique se o serviço Docker está em execução:

```sh
systemctl status docker
```

6. Adicione seu usuário ao grupo Docker para executar comandos sem sudo:

```sh
usermod -aG docker $USER
```

**Nota:** Pode ser necessário fazer logout e login novamente para que as mudanças tenham efeito.

7. Verifique a instalação do Docker executando o contêiner de teste:

```sh
docker run hello-world
```

## Instalação do Docker Compose

Siga os passos abaixo para instalar o Docker Compose:

1. Baixe a versão específica do Docker Compose:

```sh
curl -L "https://github.com/docker/compose/releases/download/v2.17.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

2. Aplique permissões executáveis ao binário:

```sh
chmod +x /usr/local/bin/docker-compose
```

3. Verifique a instalação do Docker Compose:

```sh
docker-compose --version
```

## Configuração do Docker Compose

1. Crie um arquivo `docker-compose.yml`:

```sh
vim docker-compose.yml
```
