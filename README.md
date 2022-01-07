# Start-Stop-VM-Azure
Repositorio de base de conhecimento para o processo de configuração da rotina de Start/Stop em uma conta Azure.


## Configurando rotina de desligamento automatico de uma VM
1. Na pagina de Administração da VM procure pela opção de Desligamento Automático(Auto-Shutdown).

![image](https://user-images.githubusercontent.com/83661016/148552277-31540a63-8340-4a2f-a7e5-1cb2a0ffee2e.png)


2. Configure a rotina de acordo com os requisitos, horario e notificações. Selecione a opção Habilitado(On) para ativar a rotina.

![image](https://user-images.githubusercontent.com/83661016/148552757-e03b5b1c-4699-4a19-927f-d5c8cea28e7c.png)


## Configurando rotina de ligamento automatico de uma VM(metodo 1)

O metodo 1 consiste no uso de Runbooks e agendas para executar scripts de ligamento automatico.

1. Crie uma conta de automação(automation accounts)

 ![image](https://user-images.githubusercontent.com/83661016/148553279-af8a4a3f-335e-49be-bf5e-b851a2045218.png)
 
 ![image](https://user-images.githubusercontent.com/83661016/148553427-6b537c07-467d-482d-986f-f90ff67f5774.png)
 
  Preencha os campos de acordo com a necessidade. No campo grupo de recursos(resource group) deve-se escolher o mesmo grupo da instancia em questão. Não há mais nada para ser editado, clique em revisar+criar(review_create).
  
 ![image](https://user-images.githubusercontent.com/83661016/148553845-393e8d83-2c66-48bd-bd6d-f9ea1e30375a.png)


2. Criação de Runbook

 Agora com a conta criada devemos criar um Runbook, na pagina de adminsitração da conta recem criada vamos selecionar a opção runbook e criar um runbook novo.
 
 ![image](https://user-images.githubusercontent.com/83661016/148554617-2ea9a2df-3d38-4fbe-982a-36d663052ebc.png)

 ![image](https://user-images.githubusercontent.com/83661016/148554872-041b558f-ad33-467e-b202-eff0da365044.png)
 
 



