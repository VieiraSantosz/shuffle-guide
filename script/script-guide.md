<h1 align="center">

[![image](https://github.com/Shuffle/Shuffle/blob/main/frontend/public/images/Shuffle_logo_new.png)](https://shuffler.io/)

Script para Instalação do Shuffle

</h1>

<h4 align="center">

Instruções para executar o script install_shuffle.sh e o primeiro acesso à plataforma. 

</h4>

## Pré-Requisitos

Antes de executar o script, verifique se o seu servidor atende aos seguintes requisitos:

- **Sistema operacional:** Ubuntu e Debian
- **Mínimo de disco:** 32 GB
- **Mínimo de memória RAM:** 8 GB
- **Mínimo de CPU:** 4 CPU


## Execução do Script
**1. Atualizar o servidor**

Antes de executar o script, certifique-se de que o servidor está atualizado. Isso garante que os pacotes necessários sejam instalados corretamente.
```bash
sudo apt update && sudo apt upgrade -y
```

**2. Clone o repositório**

Clone o repositório onde o script de instalação está armazenado.
```bash
git clone https://github.com/VieiraSantosz/shuffle-guide.git
```

**3. Navegar até o diretório do script**

Acesse a pasta onde o script foi clonado.
```bash
cd shuffle-guide/script
```

**4. Conceder permissões para o script**

Antes de executar o script, é necessário garantir que ele tenha permissões de execução.
```bash
chmod +x install_shuffle.sh
```

**5. Executar o script de instalação**

Agora, execute o script para iniciar a instalação do Grafana.
```bash
./install_shuffle.sh
```

![image](https://github.com/user-attachments/assets/14ae505e-8a8d-48a4-b260-f7bfa282653e)


Após a instalação, o script fornecerá o link de acesso à interface web. Guarde essa informação, pois você precisará dela para acessar a plataforma do Shuffle.

![image](https://github.com/user-attachments/assets/1e47d32f-5cc7-48fc-b548-0520e2ecb6e3)

**Nota**: Durante o primeiro acesso, o sistema solicitará a criação de um nome de usuário e senha para configurar sua conta inicial.



## Primeiro acesso à plataforma
**1. Acessar a interface web**

Depois que os serviços estiverem ativos, abra o navegador e acesse a interface web do Shuffle utilizando o IP da sua máquina seguido da porta 3001.
```bash
http://<IP-do-Servidor:3001>
```

**2. Login inicial**

Na primeira vez que você acessar a interface, será solicitado um **nome de usuário** e **senha** para criar sua conta.

**Nota:** Anote suas credenciais, pois serão utilizadas para os próximos acessos.

![image](https://github.com/user-attachments/assets/3a7e4df0-e982-4c6a-9021-51824d107508)

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
