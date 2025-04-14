<h1 align="center">

[![image](https://github.com/Shuffle/Shuffle/blob/main/frontend/public/images/Shuffle_logo_new.png)](https://shuffler.io/)

Guia de Instalação do Shuffle

</h1>

<h4 align="center">

Instruções para a instalação do Shuffle e o primeiro acesso à plataforma.

</h4>

## Pré-Requisitos

Antes de iniciar a instalação, verifique se o seu servidor atende aos seguintes requisitos:

- **Sistema operacional:** Red Hat Enterprise Linux (RHEL), Fedora, Ubuntu e Debian
- **Mínimo de disco:** 32 GB
- **Mínimo de memória RAM:** 8 GB
- **Mínimo de CPU:** 4 CPU


## Instalação do Shuffle

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
echo \
   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
   $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```





## Iniciar e habilitar o serviço Grafana

**1. Iniciar os serviços**

Depois da instalação, é necessário iniciar o serviço do Grafana e garantir que ele seja iniciado automaticamente junto com o sistema operacional.
```bash
sudo systemctl daemon-reload
sudo systemctl start grafana-server
```

**2. Configurar o servidor Grafana para iniciar na inicialização**

Ativar o serviço do Grafana para que ele seja iniciado automaticamente ao ligar ou reiniciar o servidor.
```bash
sudo systemctl enable grafana-server.service
```

![image](https://github.com/user-attachments/assets/a23bbd1d-7f2e-4a15-87f3-3064cba765b7)

**3. Verificar se o serviço está sendo executado**

Verificar se o serviço está **active (running)** ou se ocorreu algum erro.
```bash
sudo systemctl status grafana-server
```

![image](https://github.com/user-attachments/assets/7d6ac3b6-c8b6-4001-a7cd-c9c32473f744)

**Nota:** Se o serviço estiver em execução corretamente, você verá uma mensagem indicando que ele está ativo. Caso contrário, revise os passos anteriores.


## Primeiro acesso à plataforma

**1. Acessar a interface web**

Após a instalação, abra o seu navegador e insira a seguinte URL para acessar a plataforma do Grafana:
```bash
http://<IP-do-Servidor:3000>
```
**Nota:** Caso você esteja acessando a plataforma remotamente, substitua o **localhost** pelo endereço IP ou nome de domínio do servidor onde o Wazuh foi instalado.

**2. Login inicial**

Ao acessar pela primeira vez, você verá a tela de login do Grafana. Use as credenciais **admin** tanto para o nome de usuário quanto para a senha.

![image](https://github.com/user-attachments/assets/fa85656b-8335-4a6e-a53a-16b5514b56b6)

**3. Trocar a senha**

Por segurança, o Grafana exige que a senha padrão do usuário admin seja alterada logo após o primeiro login.

![image](https://github.com/user-attachments/assets/356056b6-8854-47cc-99be-6ca8de42c5f1)


**4. Após o Login**

Após a troca de senha, você será redirecionado para a interface principal do Grafana.

![image](https://github.com/user-attachments/assets/8388280c-41cf-42b7-90f3-ff09c2c37c2b)


## Solução de Problemas
Caso a instalação não tenha ocorrido conforme esperado, verifique o seguinte:

- **Falha na conexão com a internet:** Verifique se a sua conexão está funcionando corretamente e que o servidor pode acessar os repositórios do Grafana.
- **Acesso à interface web:** Se você não consegue acessar a interface web, verifique se a porta 3000 está aberta no firewall do servidor.
- **Serviço Grafana não está em execução:** Certifique-se de que o serviço está ativo.

