# mslearn-ai-fundamentals-machine-learning
Explore Automated Machine Learning in Azure Machine Learning

#1 Criar um recurso Azure Machine Learning

Criar um recurso do tipo workspace da Azure Machine Learning. Para isso, procurar em "Todos os serviços" por "Azure Machine Learning".

Selecionar, abrirá uma lista vazia e clicar em criar.

Necessário informar assinatura (subscription), nome do grupo do recurso (crie um), nome da workspace e região. Storage account, key vault e application insights pode deixar os valores padrão.

Revise e selecione Criar para confirmar.

Aguarde alguns minutos até que conclua a criação da workspace.

#2 Iniciar o Machine Learning Studio

Após concluir a criação da workspace, clicar na workspace criada, e em seguida clicar em "Iniciar o estúdio".

#3 Treinar um modelo

Acessar no menu a esquerda o ML Automatizado.

Clicar em "Novo trabalho de ML Automatizado".

Optar por "Treinar automaticamente". Informe nome do trabalho, criar novo experimento, informar descrição e clicar em avançar.

Em tipo de tarefa selecionar Regressão.

No tipo de dados selecionar tabular.

Na fonte de dados, selecionar "De arquivos da Web".

Informar URL, ignorar validação de dados.

Em configurações, selecionar formato de arquivo delimitado, delimitador vírgula, encoding UTF-8 e cabeçalhos de coluna como somente o primeiro arquivo tem cabeçalhos. 

Revisar e clicar em criar.

Na configuração de tarefas, informar em "Coluna de destino" o campo "Rentals".

Em "Exibir definições de configurações adicionais", a "Métrica primária" deve ser "NormalizedRootMeanSquareError". Desmarcar os demais campos "Explicar o melhor modelo", "Habilitar empilhamento de ensemble" e "Usar todos os modelos suportados".

Ainda na mesma tela, no "Modelos permitidos" selecionar RamdomForest e LightGBM. E clicar em salvar.

Em limites: máximo de avaliações 3, máximo de avaliações simultâneas 3, máximo de nós 3, limite de pontuação da métrica 0.085, templo limite do experimento (minutos) 15, tempo limite de iteração (minutos) 15 e habilitar encerramento antecipado marcado.

Tipo de validação: Divisão de validação de treinamento. Validação de percentual de dados: 10.

Dados de teste: nenhum.

Em computação, selecionar "sem servidor", tipo de máquina virtual CPU, tipo de máquina virtual "dedicado", tamanho da máquina virtual: Standard_DS3_V2 e número de instâncias 1.




