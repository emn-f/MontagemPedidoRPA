# Montagem de Pedido RPA

Este é um projeto de RPA (Automação Robótica de Processos) desenvolvido no **UiPath Studio**. A automação tem como objetivo principal processar e calcular o valor final de pedidos, aplicando regras de desconto específicas baseadas na categoria do cliente (Comum ou Premium).

## Funcionamento do fluxo
A automação interage com o usuário para coletar dados e realizar cálculos matemáticos. O fluxo de execução funciona da seguinte forma:
1. **Coleta de Dados do Cliente:** Solicita via interface gráfica (InputDialog) o nome completo e o endereço do cliente.
2. **Coleta de Dados do Pedido:** Pergunta o ID do pedido e o valor do subtotal.
3. **Classificação do Cliente:** Solicita a definição do tipo do cliente, dando as opções "1 - Comum" e "2 - Premium".
4. **Cálculo de Desconto:** Verifica o tipo do cliente e aplica a regra de negócio correspondente, reduzindo o desconto apropriado do valor total.
5. **Resumo Final:** Exibe uma caixa de mensagem informando o nome do cliente, o subtotal e o valor final com o desconto já calculado.

## Estrutura do Projeto 
O projeto adota boas práticas de modularização para facilitar a manutenção. Os fluxos estão divididos nos seguintes arquivos:
* `Main.xaml`: O ponto de entrada (Entry Point) da automação. Ele orquestra as chamadas para as outras etapas do processo.
* `DadosCliente.xaml`: Responsável por abrir as caixas de diálogo para capturar informações pessoais do cliente.
* `MontagemPedido.xaml`: Captura os dados do pedido, invoca o cálculo de desconto e exibe o resumo em tela.
* `TipoCliente.xaml`: Contém a lógica de menu para selecionar a categoria de fidelidade do cliente.
* `AplicarDesconto.xaml`: Arquivo que processa a matemática do negócio, aplicando percentuais diferentes baseados na variável do tipo de cliente.

**Principais Pacotes UiPath Utilizados:**
* `UiPath.System.Activities`
* `UiPath.UIAutomation.Activities`
* `UiPath.Excel.Activities`
* `UiPath.Mail.Activities`
