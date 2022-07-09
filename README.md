# Prevendo Compra de Carros

Neste projeto, obtido a partir do kaggle (que pode ser acessado [aqui](https://www.kaggle.com/datasets/gabrielsantello/cars-purchase-decision-dataset)), com base nas informações do cliente, se o mesmo irá comprar o carro ou não, em que será utilizado a teoria CRISP-DM muito utilizada na ciência de dados, cuja imagem abaixo ilustra bem o processo.

## Metodologia Crisp-dm
![crispdm](https://2315530342-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fb66bdV3JnCYJ5yeWf5dy%2Fuploads%2Fgit-blob-e3eea337334d513c6bceedd362fbd336cd41817d%2Fcrisp_dm.drawio.png?alt=media)

**obs**: Alguns passos dessa metodologia vão ser pulado pois são meramente técnico e não considerei importante colocar aqui, mais caso queira ver com mais clareza, acesse o notebook.

## Entendimento dos Dados

### Dicionário dos Dados
- **User ID**: ID do cliente.
- **Gender**: Genero do cliente.
- **Age**: Idade do cliente.
- **AnnualSalary**: Salário Anual.
- **Purchased**: Se adquiriu o carro.

Neste dataset tem um conjunto bem razoavel de dados, como pode ver neste gráfico de pizza:

![image](https://user-images.githubusercontent.com/39843884/178125456-6f6a2e6e-1bc0-42d8-b9f1-7a89379a60a2.png)

Ou seja, temos que uma grande parte dos clientes acabam não comprando um carro, mas não se tem uma diferença tão grande quanto aos cliente que compram.

![image](https://user-images.githubusercontent.com/39843884/178125529-9c1413d0-b11e-4a7c-a76f-a46fd8f2366d.png) ![image](https://user-images.githubusercontent.com/39843884/178125545-32587b03-a3c5-4f22-9864-87eeafe27acd.png)

Observando primeiro esse gráfico de barras, as mulheres acabam comprando mais carros que os homens, mas não se tem uma diferença tão grande, e no segundo gráfico, comparando o salário anual por genero, não se tem muita diferença se compararmos os generos, não seignifique que não há, só que nesse **dataset** não há uma diferença grande nos salários.

![image](https://user-images.githubusercontent.com/39843884/178125594-243d5615-76b8-4486-b8b2-f139b0b33078.png)

Neste gráfico de dispersão acima acredito que seria uns do gráficos mais importantes que poderia ser de base ao gestor ou vendedor que poderia auxiliar muito em seu trabalho, pois podemos ver claramente que neste dataset que:
- Pessoas de até 40 anos e com salário anual de até 80 mil tem uma grande chance de não comprarem o carro;
- Pessoas com mais de 50 anos tem chance de comprar um carro;
- Clientes com um salário anual acima de 100 mil tem uma grande chance de comprar um carro.

## Modelagem

Aplicando modelos de Machine Learning, utilizando o *cross validation* dividindo em 10 partes, obteve as seguintes métricas (no caso a média de cada treinamento feito):

![image](https://user-images.githubusercontent.com/39843884/178125782-60317a84-625e-4dec-a8be-57e399a5f2e3.png)

Tivemos três modelo que tiveram uma boa perfomace: KNN, SVM e Gradiente Boosting, pela simplicidade, acabei escolhendo o KNN, que no caso, foi aplicado uma otimização de parametros aplicado otimização bayesiana com o comando *BayesSearchCV* em que se obteve os seguintes parametros:

![image](https://user-images.githubusercontent.com/39843884/178125844-3a94faec-6ec5-46a2-940a-34cd71f3f950.png)

Assim obteve essas metricas
- Acuracia: 0,909
- Precisão: 0,874
- Recall: 0,907

## Conclusão

Temos que o modelo acima pode ser um bom recurso para auxiliar os vendedores e gestores em suas decisões, mas poderia ser melhorado se coletassem outras variaveis como preço do carro, ano do carro, etc, trazendo mais informações que poderiam melhorar o desempenho do modelo, que para poucas variaveis já se tem uma perfomace muito boa e mostra como modelos de machine learning poderia ser benefico a uma empresa de venda de carros, e como essess modelos tem um ampla variedade de aplicações.


