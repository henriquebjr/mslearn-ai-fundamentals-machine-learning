# mslearn-ai-fundamentals-machine-learning

Explore Automated Machine Learning in Azure Machine Learning

# 1 Criar um recurso Azure Machine Learning

Criar um recurso do tipo workspace da Azure Machine Learning. Para isso, procurar em "Todos os serviços" por "Azure Machine Learning".

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image1.png)

Selecionar, abrirá uma lista vazia. Clique então em criar.

Necessário informar assinatura (subscription), nome do grupo do recurso (crie um), nome da workspace e região. Rede deixe como pública. Storage account, key vault e application insights pode deixar os valores padrão.

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image2.png)


Revise e selecione Criar para confirmar.

Aguarde alguns minutos até que conclua a criação da workspace.

# 2 Iniciar o Machine Learning Studio

Após concluir a criação da workspace, clicar na workspace criada, e em seguida clicar em "Iniciar o estúdio".

Caso não encontre o recurso criado, acesse no menu lateral esquero o item "Todos recursos" e então pelo item do tipo "Workspace do Azure Machine Learning". Clique nele que abrirá a opção para iniciar o estúdio.

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image3.png)


# 3 Treinar um modelo

No Azure Machine Learning Studio acesse no menu a esquerda o ML Automatizado.

Clicar em "Novo trabalho de ML Automatizado".

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image4.png)


Optar por "Treinar automaticamente". Informe nome do trabalho, criar novo experimento, informar descrição e clicar em avançar.

Em tipo de tarefa selecionar Regressão.

No tipo de dados selecionar tabular.

Na fonte de dados, selecionar "De arquivos da Web".

Informar URL, ignorar validação de dados.

Em configurações, selecionar formato de arquivo delimitado, delimitador vírgula, encoding UTF-8 e cabeçalhos de coluna como somente o primeiro arquivo tem cabeçalhos.

Revisar e clicar em criar.

Na configuração de tarefas, informar em "Coluna de destino" o campo "Rentals".

Em "Exibir definições de configurações adicionais", a "Métrica primária" deve ser "NormalizedRootMeanSquareError". Desmarcar os demais campos "Explicar o melhor modelo", "Habilitar empilhamento de ensemble" e "Usar todos os modelos suportados".

Ainda na mesma tela, no "Modelos permitidos" selecionar apenas RamdomForest e LightGBM. E clicar em salvar.

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image5.png)


Em limites: máximo de avaliações 3, máximo de avaliações simultâneas 3, máximo de nós 3, limite de pontuação da métrica 0.085, templo limite do experimento (minutos) 15, tempo limite de iteração (minutos) 15 e habilitar encerramento antecipado marcado.

Tipo de validação: Divisão de validação de treinamento. Validação de percentual de dados: 10.

Dados de teste: nenhum.

Em computação, selecionar "sem servidor", tipo de máquina virtual CPU, tipo de máquina virtual "dedicado", tamanho da máquina virtual: Standard_DS3_V2 e número de instâncias 1.

O modelo será então processado por cerca de 15 minutos.

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image6.png)


# 4 Verificando o Modelo

Com o processamento concluído, poderá ser possível avaliar o modelo. Basta clicar no nome dos algoritmos do modelo.

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image7.png)


No modelo gerado, acesse então a aba de métricas.

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image8.png)


# 5 Deploy e disponibilização de API

Na aba "Modelo" selecione "Implantar".

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image9.png)


Selecione como "Serviço Web".

Preencha nome, descrição, tipo de computação como "Instância de Conteiner do Azure" e marque habilitar autenticação.

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image10.png)

Confirme clicando em "Implantar".

Em tarefas é possível acompanhar.

Quando concluído, estará disponível no item "Pontos de extermidade" do menu a esquerda.

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image11.png)


Para validar e testar o modelo, basta selecionar o modelo e ir na aba "Testar".

Preencha o json conforme a previsão desejada e clique em testar:

![](https://raw.githubusercontent.com/henriquebjr/mslearn-ai-fundamentals-machine-learning/main/images/image12.png)



