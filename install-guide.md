<h1 align="center">

[![image](https://github.com/Shuffle/Shuffle/blob/main/frontend/public/images/Shuffle_logo_new.png)](https://shuffler.io/)

Guia de Instalação do Shuffle

</h1>

<h4 align="center">

Instruções para a instalação do Shuffle e o primeiro acesso à plataforma.

</h4>

## Pré-Requisitos

Antes de iniciar a instalação, verifique se o seu servidor atende aos seguintes requisitos:

- **Sistema operacional:** Ubuntu e Debian
- **Mínimo de disco:** 32 GB
- **Mínimo de memória RAM:** 8 GB
- **Mínimo de CPU:** 4 CPU


## Instalação do Docker

**1. Atualizar o servidor**

Antes de iniciar a instalação, certifique-se de que o servidor está atualizado. Isso garante que os pacotes necessários sejam instalados corretamente.
```bash
sudo apt update && sudo apt upgrade -y
```

**2. Adicionar a chave GPG oficial do Docker**

```bash
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

**3. Adicionar o repositório ao Apt sources**

```bash
echo \
   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
   $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

**4. Instalar e configurar o Docker**

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```


## Instalação do Shuffle

**1. Baixar e configurar o projeto Shuffle**

```bash
git clone https://github.com/Shuffle/Shuffle
cd Shuffle
sudo chown -R 1000:1000 shuffle-database
```

**2. Iniciar os serviços do Shuffle**

```bash
docker compose up -d
```

![image](https://github.com/user-attachments/assets/81e6853f-f712-43a6-a2ce-8fb05c690571)



## Primeiro acesso à plataforma

**1. Acessar a interface web**

Após a instalação, abra o seu navegador e insira a seguinte URL para acessar a plataforma do Shuffle:
```bash
http://<IP-do-Servidor:3001>
```
**Nota:** Caso você esteja acessando a plataforma remotamente, substitua o **localhost** pelo endereço IP ou nome de domínio do servidor onde o Wazuh foi instalado.

**2. Login inicial**

Ao acessar pela primeira vez, você verá a tela de login do Shuffle. Crie um nome de usuário e uma senha para acessar a plataforma na próxima vez.

![image](https://github.com/user-attachments/assets/3a7e4df0-e982-4c6a-9021-51824d107508)

Feito a criação do nome de usuário e da senha, só acessar a plataforma.

![image](https://github.com/user-attachments/assets/975c9638-38ef-4dc5-93a0-bc6296677dea)

**3. Após o Login**

Após a troca de senha, você será redirecionado para a interface principal do Shuffle.

![image](https://github.com/user-attachments/assets/9b1e01e0-ba1b-469d-a57c-ad431f61fbb5)











