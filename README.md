# dio-formacao-ai-900-1
Projeto criado para conclusão de aula - Trabalhando com Machine Learning na Prática no Azure ML

Passo a passo
1 - Logar em https://portal.azure.com

2 - Clicar em Create a Resource

3 - Localizar "Azure Machine Learning"

4 - Escolher o plano "Azure Machine Learning" e "Create"

5 - Escolher as opções:
Subscription = Sua assinatura - se for uma conta grátis, terá apenas uma opção
Resource group = Se for o primeiro acesso, crie um grupo
Name = Crie um nome para o workspace
Region = Selecione a região - Recomendado "East US" por ter um custo menor
Storage account, Key vault, Application insights e Container registry = deixe a opção default - mais informações, consultar a documentação: https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html

6 - Nas próximas abas: Networking, Encryption e Tags = deixe o default

7 - Review + Create = nesta aba, clique em "Create"

8 - Aguarde o deploy

9 - Após o deploy = Go to resource

10 - No workspace, selecione "Automated ML"

11 - Em seguida "+ New Automated ML Job"
Preencha com as informações:
Job name: mslearn-bike-automl
New experiment name: mslearn-bike-rental
Description: Automated machine learning for bike rental prediction
Tags: none

12 - Selecione o tipo de task: Regression

13 - Na parte de selecionar data, clicar em "+ Create"

14 - Preencha com as informações:
Name: bike-rentals
Description: Historic bike rental data
Type: Tabular

15 - Em data source, selecione "From web files"

16 - Preencha com as informações:
Web URL: https://aka.ms/bike-rentals
Skip data validation: do not select

17 - Em "Settings", preencha:
File format: Delimited
Delimiter: Comma
Encoding: UTF-8
Column headers: Only first file has headers
Skip rows: None
Dataset contains multi-line data: do not select

18 - Em "Schema":
Include all columns other than Path
Review the automatically detected types

19 - Create

20 - Selecione no radio box, o "Data" criado.

21 - Em Task Settings, siga o passo:
Task type: Regression
Dataset: bike-rentals
Target column: Rentals (integer)
Additional configuration settings:
Primary metric: Normalized root mean squared error
Explain best model: Unselected
Use all supported models: Unselected. You’ll restrict the job to try only a few specific algorithms.
Allowed models: Select only RandomForest and LightGBM — normally you’d want to try as many as possible, but each model added increases the time it takes to run the job.
Limits: Expand this section
Max trials: 3
Max concurrent trials: 3
Max nodes: 3
Metric score threshold: 0.085 (so that if a model achieves a normalized root mean squared error metric score of 0.085 or less, the job ends.)
Timeout: 15
Iteration timeout: 15
Enable early termination: Selected
Validation and test:
Validation type: Train-validation split
Percentage of validation data: 10
Test dataset: None
Compute:

Select compute type: Serverless
Virtual machine type: CPU
Virtual machine tier: Dedicated
Virtual machine size: Standard_DS3_V2*
Number of instances: 1

21 - Clique em "Submit train job"

22 - 










 
