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

Essa chave é usada para verificar a autenticidade dos pacotes baixados do repositório oficial do Docker.
```bash
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

**3. Adicionar o repositório do Docker**

Adiciona o repositório oficial do Docker à lista de fontes do apt para que os pacotes possam ser instalados corretamente.
```bash
echo \
   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
   $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

**4. Instalar o Docker e seus plugins**

Com o repositório adicionado, você pode instalar o Docker Engine e os plugins necessários para utilizar o Docker Compose.
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```
**Nota**: Verifique se o serviço do Docker está ativo com **sudo systemctl status docker**.


## Instalação do Shuffle

**1. Baixar e configurar o projeto Shuffle**

Clona o repositório oficial do Shuffle e garante as permissões corretas para o banco de dados local.
```bash
git clone https://github.com/Shuffle/Shuffle
cd Shuffle
sudo chown -R 1000:1000 shuffle-database
```

**2. Iniciar os serviços do Shuffle**

Com os arquivos prontos, essa etapa inicia todos os containers necessários usando o Docker Compose.
```bash
docker compose up -d
```

![image](https://github.com/user-attachments/assets/81e6853f-f712-43a6-a2ce-8fb05c690571)

**Nota:** O processo pode levar alguns minutos na primeira execução, pois o Docker precisará baixar as imagens e realizar a configuração inicial. Aguarde até que todos os serviços estejam ativos.


## Primeiro acesso à plataforma

**1. Acessar a interface web**

Abra o navegador e acesse a interface web do Shuffle utilizando o IP da sua máquina seguido da porta 3001.
```bash
http://<IP-do-Servidor:3001>
```

**2. Login inicial**

Na primeira vez que você acessar a interface, será solicitado um **nome de usuário** e **senha** para criar sua conta.

**Nota:** Anote suas credenciais, pois serão utilizadas para os próximos acessos.

![image](https://github.com/user-attachments/assets/71737857-2f2d-444c-a669-fcf75b333f6b)

Depois de criar suas credenciais, faça o login e você será direcionado automaticamente para a interface principal do Shuffle.

![image](https://github.com/user-attachments/assets/975c9638-38ef-4dc5-93a0-bc6296677dea)

**3. Após o Login**

Após entrar na plataforma, você já pode começar a explorar e personalizar o Shuffle de acordo com as suas necessidades.

![image](https://github.com/user-attachments/assets/9b1e01e0-ba1b-469d-a57c-ad431f61fbb5)

## Solução de Problemas
Caso a instalação não tenha ocorrido conforme esperado, verifique o seguinte:

- **Falha na conexão com a internet:** Verifique se a sua conexão está funcionando corretamente e que o servidor pode acessar os repositórios do Grafana.
- **Acesso à interface web:** Se você não consegue acessar a interface web, verifique se a porta 3001 está aberta no firewall do servidor.
- **Problemas com Docker:** Confirme se o Docker está em execução com **docker ps**.









