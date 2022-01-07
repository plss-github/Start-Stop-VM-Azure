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
 
 Com o Runbook criado, deve-se agora editá-lo. Vamos utilizar o script [start-stop.ps1](https://github.com/plss-github/Start-Stop-VM-Azure/blob/main/start-stop.ps1). Copie e cole o scrip no editor, em seguida clique em salvar e publicar
 ![image](https://user-images.githubusercontent.com/83661016/148555683-f0351f8a-4332-4de4-932c-bc0c716ed6aa.png)

3. Criação de Agenda(Schedule)
 
 Ainda dentro do Runbook, devemos agora criar um agendamento. Clique na opção agenda(schedule) e crie um novo.
 
 ![image](https://user-images.githubusercontent.com/83661016/148556034-b32afc5d-13b4-4e46-bd97-06226834a752.png)

 A configuração de uma agenda consiste em duas etapas, a configuração do agendamento em si e a configuração dos parametros de execução.
 
 ![image](https://user-images.githubusercontent.com/83661016/148556311-87822f93-6be8-43e5-b80b-4ede1fab075f.png)
 
 Agendamento: clique em criar, configure de acordo com os requisitos do cliente e com a imagem abaixo
 
 ![image](https://user-images.githubusercontent.com/83661016/148556748-653e4b42-65be-4eff-8fb8-67632349ce0b.png)
 
 Parametros: configure os parametros, nome da instancia, grupo de recursos e ação("Iniciar" sem aspas)
 
 ![image](https://user-images.githubusercontent.com/83661016/148557108-8259d90c-1cb6-4f55-a27e-008f5dd3e130.png)
 
 Clique em ok para finalizar a criação da agenda.
 
 4. Ajustes de permissão
  A conta de automação precisará receber as devidas permissões para executar este runbook. Na conta de automação recém criada, selecione contas de rodar como( runas accounts) e clique em criar uma conta azure

 ![image](https://user-images.githubusercontent.com/83661016/148557640-b7ffa700-393e-419d-b462-1de110d3fb18.png)

 ![image](https://user-images.githubusercontent.com/83661016/148557944-69f1444c-2314-43a7-b55f-636bef5c434f.png)

Nesse momento finalizamos a configuração do primeiro metodo, lembrar que nesse modelo de permissão temos uma validade de um ano.
 



 



