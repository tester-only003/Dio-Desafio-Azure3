# Dio-Desafio-Azure3
Criar uma implantação da Instância Gerenciada de SQL do Azure usando o portal do Azure.

  Observação: <br>
  > [**Experimente a Instância Gerenciada de SQL do Azure sem custo**](https://learn.microsoft.com/pt-br/azure/azure-sql/managed-instance/free-offer?view=azuresql) e obtenha 720 horas de vCore em uma Instância Gerenciada de SQL de Uso Geral com até 100 bancos de dados por instância nos primeiros 12 meses.
<br>

## Pré-requisitos
Para criar uma instância gerenciada de SQL, você precisa dos seguintes pré-requisitos: <br>
- Uma assinatura do Azure. Se você não tem uma assinatura do Azure, crie uma conta gratuita
- No caso geral, seu usuário precisa ter a função SQL Managed Instance Contributor atribuída no âmbito da assinatura.
- Se o provisionamento for em uma sub-rede que já está delegada à Instância Gerenciada do Azure SQL, o seu usuário só precisará da permissão Microsoft.Sql/managedInstances/write atribuída em nível de escopo de assinatura.
- O módulo Az.SQL mais recente para a versão atual do PowerShell ou a versão mais recente da CLI do Azure.
<br>

### Criar uma Instância Gerenciada de SQL do Azure

Você pode criar uma implantação de Instância Gerenciada de SQL do Azure usando o portal do Azure, o PowerShell ou a CLI do Azure.

Considere o seguinte: <br>
- Cancele o processo de provisionamento por meio do portal do Azure, do PowerShell, da CLI do Azure ou de outras ferramentas usando a API REST.
- A implantação da instância será atrasada se for afetada por outras operações na mesma sub-rede, como uma restauração de longa duração ou o dimensionamento de uma instância.
- As permissões de leitura do grupo de recursos são necessárias para visualizar a instância gerenciada do SQL no seu grupo de recursos.


#### Entre no Portal do Azure

Para criar sua instância no portal do Azure, primeiro você precisará entrar no portal do Azure e preencher as informações na página **Criar Instância Gerenciada de SQL do Azure**.

Para sua instância, siga estas etapas: <br>
1. Entre no portal do Azure. <br>
2. Vá para o [Hub SQL do Azure em aka.ms/azuresqlhub](https://aka.ms/azuresqlhub). <br>
3. No painel da **Instância Gerenciada de SQL do Azure**, selecione **Mostrar opções**. <br>
4. Na janela de opções da **Instância Gerenciada de SQL do Azure**, selecione **Criar Instância Gerenciada de SQL**.

<img width="1474" height="487" alt="Azure-SQL-Manageg-Instance1" src="https://github.com/user-attachments/assets/598420b3-55ea-4b61-9717-696daac73321" />
<br>
<br>
<img width="591" height="560" alt="Opções-Instância-Gerida-SQL-Azure1" src="https://github.com/user-attachments/assets/ac318483-a8fe-4eea-a260-c946e8ef0608" />










