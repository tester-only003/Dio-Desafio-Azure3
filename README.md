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
<br>
<br>


#### Guia Básico

Preencha as informações obrigatórias exigidas na guia Básico, que é o requisito mínimo para provisionar uma Instância Gerenciada de SQL.

A tabela a seguir fornece detalhes para as informações necessárias na guia Básico:

<table>
  <thead>
  <th> Configuração </th>
  <th> Valor Sugerido </th>
  <th> Description  </th>
  </thead>
  <tbody>
    <tr>
      <td> Assinatura </td>
      <td> Sua Assinatura </td>
      <td> 	Uma assinatura que concede a você permissão para criar recursos. </td>
    </tr>
    <tr>
     <td> Grupo de recursos </td>
     <td> Um grupo de recursos novo ou existente. </td>
     <td> Para ver os nomes do grupo de recursos válidos, consulte <a href="https://learn.microsoft.com/pt-br/azure/architecture/best-practices/resource-naming">Regras e restrições de nomenclatura</a>.
     </td>
    </tr>
    <tr>
     <td> Nome da instância gerenciada </td>
     <td> Qualquer nome válido. </td>
     <td> Para ver os nomes do grupo de recursos válidos, consulte <a href="https://learn.microsoft.com/pt-br/azure/architecture/best-practices/resource-naming">Regras e restrições de nomenclatura</a>. </td>
    </tr>
    <tr>
     <td> Região </td>
     <td> A região na qual você deseja criar a instância gerenciada de SQL. </td>
     <td> Para obter mais informações sobre as regiões, confira <a href="https://azure.microsoft.com/regions/"> Regiões do Azure. </a>. </td>
    </tr>
    <tr>
     <td> Pertence a um pool de instâncias? </td>
     <td> Selecione Sim para que essa instância seja criada dentro de um pool de <a href="https://learn.microsoft.com/pt-br/azure/azure-sql/managed-instance/instance-pools-configure?view=azuresql"> instâncias. </a>  </td>
      <td> </td>
     </tr>
   <tr>
     <td> Método de autenticação </td>
     <td> Usar a autenticação do SQL. </td>
     <td> Para este início rápido, use a autenticação SQL. Mas, para melhorar a segurança, use a autenticação do Microsoft Entra. </td>
  </tr>
   <tr>
     <td> Logon de administrador da Instância Gerenciada </td>
     <td> Qualquer nome de usuário válido. </td>
     <td> Para ver os nomes válidos, consulte Regras e restrições de nomenclatura. Não use serveradmin, pois essa é uma função reservada no nível de servidor. </td>
  </tr>
  <tr>
     <td> Senha </td>
     <td> Qualquer senha válida. </td>
     <td> A senha deve ter no mínimo 16 caracteres e atender a  <a href="https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/faq#what-are-the-password-requirements-when-creating-a-vm-"> requisitos de complexidade definidos. </a>  </td>
  </tr>
  </tbody>
</table>
<br>

Em **Detalhes da instância gerenciada**, selecione **Configurar instância gerenciada** na seção **Computação + armazenamento** para abrir a página **Computação + armazenamento**.

<img width="574" height="329" alt="Create-Azure-SQL-Managed-Instance1" src="https://github.com/user-attachments/assets/bdb6fe55-de89-4b1c-a1c8-0362b6b7ecb5" />
<br>

Depois de designar sua configuração de **Computação + Armazenamento**, use **Aplicar** para salvar suas configurações e navegar de volta para a página **Criar Instância Gerenciada SQL do Azure**. Selecione Próximo para ir para a **guia Rede**.
<br>
<br>


#### Guia Rede
Preencha informações opcionais na guia **Rede**. Se você omitir essas informações, o portal aplicará as configurações padrão.

Selecione **Examinar + criar** para examinar suas escolhas antes de criar uma instância gerenciada de SQL. Ou defina as configurações de segurança selecionando **Avançar: Configurações de segurança**.
<br>
<br>


#### Guia Segurança
Para este início rápido, deixe as configurações na guia Segurança em seus valores padrão.

Selecione **Examinar + criar** para examinar suas escolhas antes de criar uma instância gerenciada de SQL. Ou defina mais configurações personalizadas selecionando **Avançar: configurações adicionais**.
<br>
<br>


#### Configurações adicionais
Preencha as informações opcionais na guia **Configurações adicionais**. Se você omitir essas informações, o portal aplicará as configurações padrão.
<br>

Selecione **Examinar + criar** para examinar suas escolhas antes de criar uma instância gerenciada de SQL. Ou, então, configure as marcas do Azure selecionando **Avançar: Marcas** (recomendado).
<br>
<br>


#### Marcações
Adicione marcas aos recursos no modelo do ARM (modelo do Azure Resource Manager). As marcas ajudam você a organizar logicamente seus recursos. Os valores de marca são mostrados nos relatórios de custo e permitem outras atividades de gerenciamento por marca. Considere pelo menos marcar sua nova instância gerenciada de SQL com a marca Proprietário para identificar quem criou e a marca Ambiente para identificar se esse sistema é Produção, Desenvolvimento etc. Para obter mais informações, consulte Desenvolver sua estratégia de nomenclatura e marcação para recursos do Azure.
<br>

Selecione **Examinar + criar** para prosseguir.










