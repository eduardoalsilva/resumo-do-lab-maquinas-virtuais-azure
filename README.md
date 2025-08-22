# Resumo do Lab

## Máquinas virtuais Azure

Para criar uma máquina virtual basta acessar o portal do Azure pelo endereço https://www.portal.azure.com. No portal, direto do navegador, é possível criar máquinas virtuais para distribuições Linux ou versões do Windows. Com a máquina criada você pode acessá-la por protocolo RDP ou via SSH. Também é necessário instalar um servidor Web, como o NGINX ou IIS. A seguir veremos o passo a passo para criar uma máquina virtual.

### Criar uma máquina virtual Azure

Passo a passo para criar uma máquina virtual:
1. Acesse **Máquinas Virtuais** pelo menu lateral ou pelo buscador.
2. Clique no botão **Criar** e escolha a opção **Máquina Virtual**.
3. Em *Instance Details* preencha os campos. Escolha a imagem do Sistema Operacional que deseja:
  ![Detalhes da instancia](/images/instance-details.png)
4. Crie uma senha para administrador com o nome de usuário Azure ou conecte por SSH:
  ![Conta de Administrador](/images/administrator-account.png)
5. Em *Inbound port rules* selecione a opção *Allow selected ports* escolha qual porta será utilizada: RDP (3389) e HTTP (80):
  ![Regras de porta de entrada](/images/inbound-port-rules.png)
6. Clique no botão **Review + create** para revisar a máquina virtual:
  ![Revisar e criar](/images/review-create.png)
7. Um formulário será exibido para validar as informações da máquina virtual a ser criada. Se estiver tudo certo clique no botão **Create**:
  ![Validar](/images/validation.png)
8. Sua máquina virtual está criada. Clique no botão **Go to resource** para ir para a área de recursos.

### Conectar à uma máquina virtual

Com a máquina virtual criada vamos ver como se conectar a ela. Para isso vamos seguir o passo a passo para se conectar via RDP (Windows):
1. Na página de *Overview* da sua máquina virtual clique em **Connect**:
  ![Validar](/images/connect.png)
2. Clique em **Download RDP file** na guia *Connect with RDP* para se conectar através da porta 3389.
3. Abra o arquivo baixado e aguarde até que a conexão seja solicitada. E então clique em **Connect**.
4. Na tela seguinte clique em **More choices** e então **Use a different account**. No campo *username* digite *localhost\<nome-de-usuario>* (Troque <nome-de-usuario> pelo seu nome de usuário). Entre com a senha que você cadastrou ao criar a máquina virtual. Clique em **OK**.
5. Clique em **OK** para se conectar.

E pronto. Você já tem sua máquina virtual criada com sucesso e já está conectado. Para ver ela em ação conecte ao servidor Web IIS. Abra o terminal do Shell e digite o comando:
```Shell
Install-WindowsFeature -name Web-Server -IncludeManagementTools
```
