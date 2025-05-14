# Guia-de-Cria-o-e-Gerenciamento-de-M-quinas-Virtuais

Guia de Criação e Gerenciamento de Máquinas Virtuais no Microsoft Azure

Este repositório contém anotações, resumos e procedimentos práticos para criação, configuração e gerenciamento de máquinas virtuais (VMs) no Microsoft Azure. Ideal para estudantes e profissionais que desejam aprender ou revisar o uso da plataforma de nuvem da Microsoft.

 Conteúdo:
1 - Criação de VMs
2 - Configurações de rede e segurança
3 -  Instalar o servidor IIS (Internet Information Services)
4 -  Visualizar a página inicial do IIS
5 - Como limpar os recursos que você não vai mais usar
6 - Configurar o desligamento automático da VM

1. Criação da VM.

  1.2  Ao entrar no Microsoft Azure, você vai visualizar os Serviços Azure e nas opções abaixo clique na Máquinas Virtuais.
![Figura 1 2](https://github.com/user-attachments/assets/5bcb4aed-2cda-4901-846e-d1d2846b1f71)


  1.3 Na página Infraestrutura de computação clique em criar e selecione Máquina Virtual da Azure.
  ![Figura 1 3](https://github.com/user-attachments/assets/4dcc569a-4062-4e35-a75d-663e7dcf39fb)


  1.4 Em Detalhes da Instâncias crie uma máquina virtual que execute Linux ou Windows. Foi inserido o nome da VM - MyAzureVM, e neste caso foi selecionada uma imagem do Windows Server 2022 Datacenter: Azure Edition - x64 Gen 2.
![Figura 1 4](https://github.com/user-attachments/assets/a25a10be-f833-406a-a348-542135bb471c)


  1.5 Após selecionar dar nome a Máquina Virtual e a imagem, crie um usuário e senha que deve conter 12 caracteres seguindo as orientações do link em caso de dúvida. https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/faq#what-are-the-password-requirements-when-creating-a-vm-
  
![Figura 1 5](https://github.com/user-attachments/assets/b57bb806-6df3-467b-83eb-1ac02865d866)


  1.6  Regras de portas de entrada - Selecione quais portas de rede da máquina virtual podem ser acessadas pela internet pública. Mas antes selecione Permitir portas selecionadas e em seguida as portas HTTP(80), RDP(3389).
![Figura 1 6](https://github.com/user-attachments/assets/4d0cc35e-58bc-4263-87fe-2a0745632a7c)


  1.7 Clique em Revisar + criar na parte inferior da página.
  
  ![Figura 1 7](https://github.com/user-attachments/assets/2c639bed-09ee-4703-89eb-1bf9cd03af45)
  

  1.8 Selecione o botão Criar na parte inferior da página, após a execução da validação.
  ![Figura 1 8](https://github.com/user-attachments/assets/d5007aac-80d1-4579-85cf-1e72da29fc2e)


  1.9 Concluída a implantação, selecione Ir para recursos.
  
  ![Figura 1 9](https://github.com/user-attachments/assets/3af71e7c-86e2-450d-9fe1-344379f33295)


2. Configurações de rede e segurança.

	2.1 Conectar-se à Máquina Virtual.
	
	2.2 Na guia Conectar-se ao RDP, mantenha as opções padrão para se conectar por endereço IP pela porta 3389 e clique em Baixar arquivo RDP.
   
  ![Figura 2](https://github.com/user-attachments/assets/aa1c7410-d7a5-42f9-b414-4c0fb30e2e74)


  2.3 Informe as credenciais no seguinte formato:
  
    Nome de usuário: localhost\nome-de-usuário
    Senha: use a que você definiu para a VM.
OBS: Pode aparecer um aviso sobre o certificado de segurança. Se isso acontecer, clique em Sim ou Continuar para prosseguir com a conexão.


3. Instalar o servidor IIS (Internet Information Services)
  3.1 Com a VM aberta, inicie o PowerShell.
  3.2 Execute o comando abaixo para instalar o servidor Web e suas ferramentas de gerenciamento:

	    Install-WindowsFeature -name Web-Server -IncludeManagementTools
3.3 Após a instalação ser concluída, encerre a conexão RDP com a VM.


4. Visualizar a página inicial do IIS
   
  4.1 Volte ao portal da Azure, selecione sua máquina virtual.
  4.2 Na aba Visão geral, passe o mouse sobre o endereço IP público da VM e clique no ícone de copiar.
  4.3 Abra o navegador da sua preferência e cole o IP copiado na barra de endereços.
  4.4 Você verá a página padrão de boas-vindas do IIS, indicando que o servidor Web está funcionando corretamente.
  
  ![Figura 4 4](https://github.com/user-attachments/assets/7fa18439-8046-47e4-a570-53bc6f679278)


5. Como limpar os recursos que você não vai mais usar

  5.1 Excluir a máquina virtual e tudo relacionado: Se você não precisar mais da VM nem dos recursos criados junto com ela, é melhor apagar tudo para não gerar custos.
  5.2 Na página inicial da sua VM, clique no link com o nome do grupo de recursos.
  5.3 Na parte de cima da nova página, clique em Excluir grupo de recursos.
  5.4 Uma mensagem vai aparecer pedindo para confirmar. Digite o nome do grupo de recursos e clique em Excluir.
  5.6 Isso vai apagar a VM e todos os serviços conectados a ela.


6. Configurar o desligamento automático da VM
  6.1 Se você ainda vai usar a VM, mas quer evitar pagar quando esquecer de desligá-la, ative o desligamento automático:
  6.2 No menu da VM, vá até a parte de Operações e clique em Desligamento automático.
  6.3 Uma nova tela vai abrir. Ative a opção "Ativado".
  6.4 Escolha um horário para que a VM desligue sozinha todos os dias.

6.5 Clique em Salvar no topo da tela.


OBS: Assim, você evita gastar sem querer quando a máquina ficar ligada sem uso.

