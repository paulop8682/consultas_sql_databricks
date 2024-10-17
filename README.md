# CONSULTAS SQL 

## Link do HTML para Acompanhamento do Projeto:
[Databricks HTML](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/8921395357682262/104875607630245/2223498099691995/latest.html)

## Instruções para Execução:
1. Crie uma conta no **Databricks Community**.
2. Crie uma pasta no Databricks.
3. Importe o link do HTML mencionado acima para essa pasta.
4. Na função `create_connection`, insira as configurações do banco de dados. Isso eliminará a necessidade de criar outro notebook para armazenar credenciais e permitirá a exclusão da primeira célula.
5. Execute o código.

Além disso, também está disponível um arquivo `.ipynb` contendo o código.

---

## Objetivo
Este projeto tem como propósito resolver as questões propostas por meio da utilização de **SQL** e/ou **Python**, demonstrando a proficiência no manuseio dessas tecnologias. 

---

## Banco de Dados
O banco de dados utilizado é um **MySQL hospedado na AWS RDS (Relational Database Service)**. Dentro desse banco, temos duas tabelas RAW:

- **raw_transactions_table**: armazena os dados relacionados às transações das carteiras de investimentos, incluindo detalhes como ativos, quantidades, datas de transação, e valores envolvidos.
- **raw_transactions_fee**: contém informações detalhadas sobre as taxas associadas às transações, como taxas administrativas, corretagens e outras despesas.

Essas tabelas são usadas para armazenar os dados em sua forma original, servindo como a base para futuros processos de transformação e análise.


---

## Justificativa da Escolha da Ferramenta
A escolha do **Databricks** se fundamenta em sua capacidade de suportar múltiplas linguagens de programação, como Python e SQL, além de integrar o **Apache Spark**, facilitando o processamento de grandes volumes de dados. Sua plataforma em nuvem oferece um ambiente ágil, além de permitir análises gráficas, tornando o processo de exploração de dados mais eficiente. Ademais, o Databricks permite o agendamento de execuções automatizadas, assegurando a recorrência dos processos de forma otimizada.

---

## Explicação do Código
Foi utilizado um notebook não versionado para armazenar as credenciais de acesso ao banco de dados, garantindo que as informações sensíveis não fiquem expostas no código. Embora o uso de soluções como o **Databricks Secret** seja a prática recomendada para a gestão segura de credenciais, a versão gratuita da ferramenta utilizada não oferece suporte a essa funcionalidade.

Após estabelecer a conexão com o banco de dados, foi desenvolvida a função `select_table`, que será empregada ao longo do desafio para responder às questões propostas. Essa função realiza consultas SQL no banco e retorna os resultados em um dataframe. Isso permite, além da visualização dos dados, o armazenamento em variáveis e a aplicação de funções do Python no dataframe, proporcionando maior flexibilidade na manipulação dos dados.

---

## Principais Consultas:

### 1. Endereço com Maior Volume de Transações Enviadas:
- A carteira com o maior volume de transações enviadas é a **A-99**.
- O HTML gerado também exibe as 10 carteiras com os maiores volumes de transações em tabelas e gráficos.

### 2. Dia do Mês com Maior Volume de Transações Realizadas:
- O dia do mês com o maior volume de transações é o **dia 07**.
- Um ranking com os 10 dias de maior volume é exibido em tabelas e gráficos no HTML, com a soma dos valores transacionados.

### 3. Dia da Semana com Maior Frequência de Transações:
- O **sábado** é o dia da semana com o maior número de transações.
- Tabelas e gráficos mostram os dias organizados por volume de transações.

### 4. Transações com Condições Atípicas:
- As transações atípicas são aquelas com valores nulos ou com status diferente de "confirmado". Elas exigem análise detalhada pelo time de negócios. 
- Outliers também foram identificados para análise futura.

### 5. Carteira com Maior Saldo Final:
- A carteira com o maior saldo final é a **A-12**, com um saldo total de **46.125.129,00**.

---

## Parte 2:

### 1. Carteiras com Maior Pagamento de Taxas em Janeiro e Fevereiro:
- Em janeiro, a carteira com o maior pagamento de taxas foi a **A-62**, enquanto em fevereiro foi a **A-91**.

### 2. ID da Transação com a Maior Taxa:
- A transação com a maior taxa registrada possui o ID **ID1092**.

### 3. Média de Taxa Paga:
- A média de taxa paga é **5,87**.

---

