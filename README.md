# Folha de Pagamentos Refatorado (Prova 2)

## Padrões aplicados

  - <b>Strategy</b><br/>
    - Motivo: Foi aplicado strategy para os empregados com o objetivo facilitar na hora de realizar o pagamento.<br/>
    Para realizar o pagamento de um empregado qualquer, só é necessário chamar o método calculatePayment()
    sem precisar utilizar IF para verificar que tipo de funcionário é esse e aplicar o cálculo específico.<br/>
    - Vantagens: O mesmo método é chamado para todos, ele realizará o cálculo do valor de pagamento independente de tipo utilizando o seguinte código:<br/>
    
      <code>double pay = employeeStrategy.calculatePayment();</code>   (employeeStrategy objeto do tipo EmployeeStrategy)<br/><br/>
      Caso for necessário implementar novas formas de pagamento não é necessário mexer em códigos já feitos. É só fazer um método calculatePayment() para essa forma de pagamento também.<br/>
   - <b> Iterator</b><br/>
      - Motivo: Era preciso utilizar ArrayList's (registrar) dados, de maneira a percorrer esses registros em diversas partes do código.<br/>
      - Vantagens: O Iterator Pattern vai prover uma interface simples para manejar esses dados, visto que é necessário em várias partes do código, compensa trabalhar os dados no iterador ao invés de no próprio Loop.<br/>
   - <b> Command</b><br/>
      - Motivo: O padrão Command foi utilizado para implementar as funções <b>Undo e Redo</b>. De acordo com a teoria, a classe CommandManager foi utilizada como classe Invoker. A classe Operations será a classe Receiver.<br/>
      - Vantagens: Utilizando tal padrão, para adicionar uma nova funcionalidade que deve ser possível desfazer ou refazer, basta criar a própria funcionalidade e gerar um comando referente a ela, sem ser preciso alterar IF's.<br/>


## Outras Classes

A classe <b>Register</b> seria uma classe de utilidade para guardar registros e manejá-los.
A classe <b>Sale</b> é uma classe que gera objetos com dados referentes a uma única venda, de modo a ser possível registrar todas as vendas e fazer cálculos de salário.
A classe <b>TimeCard</b> é uma classe que gera objetos com horários referentes a um dia de trabalho, necessários para cálculos de salário (se houve hora extra, se é necessário algum desconto).
