# TelecomX_parte2_BR
Este modelo preditivo de evasão de clientes (Churn) foi criado para cumprir um Challenge da Alura, indicado aos alunos que estão participando do programa ONE (Oracle Next Education) - Turma 9 (G9). O desafio foi desenvolvido para testar e praticar os conhecimentos adquiridos durante a trilha de Data Science com Python. Este projeto em específico testa habilidades em análise exploratória de dados (EDA), tratamento de bases, balanceamento de classes (SMOTE), treinamento e avaliação de modelos de Machine Learning (como Regressão Logística e Random Forest), além de traduzir métricas matemáticas em estratégias de negócios.
# 📄 Relatório

## 1. O Desafio e a Solução Proposta
O objetivo desta segunda etapa foi construir um pipeline de Machine Learning capaz de prever quais clientes da Telecom X estão sob risco de cancelar seus serviços (Churn).
 
Após o tratamento de dados (limpeza, padronização e balanceamento via SMOTE), treinamos e testamos modelos preditivos. O algoritmo escolhido para produção foi o **Random Forest**, que apresentou um desempenho superior, destacando-se pela métrica de **Recall (95,6%)**. 

Do ponto de vista de negócios, isso significa que o modelo consegue **identificar e alertar a empresa sobre 95 de cada 100 clientes que estão prestes a cancelar**, minimizando drasticamente a perda de receita por "falsos negativos" (clientes que saem sem que a empresa perceba).
 
## 2. O Raio-X da Evasão: O que faz o cliente sair?
Ao analisarmos os modelos preditivos, observando a Importância das Variáveis do Random Forest e os Coeficientes da Regressão Logística, identificamos os principais gatilhos da evasão:
 
* 🚨 **O Risco do Contrato Mensal:** O tipo de contrato é o fator comportamental mais crítico. Clientes no plano "mês a mês" possuem altíssima probabilidade de evasão. Em contrapartida, contratos de 1 a 2 anos atuam como a maior "blindagem" da base.
* 🚨 **O Paradoxo da Fibra Óptica e Gastos:** Clientes com serviços de Fibra Óptica apresentaram forte correlação com o cancelamento. Como o `Gasto.Total` também é uma variável de alto peso, isso sugere que a Fibra Óptica possui um preço que o cliente não considera justificável pela qualidade percebida (possível sensibilidade a preço ou instabilidade técnica).
* 🚨 **A Janela Crítica de Retenção:** A variável `Meses.Contrato` provou que o risco de evasão despenca drasticamente após os primeiros meses. O cliente que fica no início da jornada tende a se tornar vitalício.
* 🚨 **Método de Pagamento:** Clientes que pagam por "Cheque Eletrônico" (Electronic check) cancelam muito mais do que aqueles com pagamento automático em Cartão de Crédito ou Débito em Conta.
 
## 3. Plano de Ação Estratégico
Com base na inteligência preditiva gerada, propomos à diretoria da Telecom X as seguintes frentes de ação imediata:
 
**1. Força-Tarefa nos Primeiros 90 Dias (Onboarding):**
* Criar uma régua de relacionamento intensiva para novos clientes. Como o tempo de casa (`Meses.Contrato`) é vital, oferecer um atendimento de qualidade ou bônus nos 3 primeiros meses reduzirá o índice de saída da base.
 
**2. Campanha Agressiva de Migração de Contrato:**
* Lançar campanhas de **Upsell** *(técnica para aumentar o ticket médio, oferecendo ao cliente uma versão superior, mais completa ou cara de um produto/serviço que ele já demonstrou interesse)* focadas exclusivamente nos clientes do plano Mensal. Oferecer descontos agressivos ou upgrades gratuitos (como inclusão de Suporte Técnico e Segurança Online) em troca da fidelidade por 12 ou 24 meses.
 
**3. Auditoria no Produto "Fibra Óptica":**
* A área de Qualidade e Suporte precisa investigar a tecnologia de Fibra Óptica. É necessário entender se o alto churn atrelado a esse produto é causado por falhas técnicas (quedas de conexão) ou se o preço está desalinhado com o mercado competitivo.
 
**4. Incentivo ao Pagamento Automático:**
* Oferecer um pequeno desconto na fatura (ex: 5%) para clientes que cadastrarem seus pagamentos em Cartão de Crédito Automático. Essa simples mudança de atrito financeiro retira o cliente da zona de risco do "Cheque Eletrônico".
