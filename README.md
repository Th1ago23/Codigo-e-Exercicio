# Treinamento de Modelo CNN para MNIST

## Alunos
- Thiago Peixoto dos Santos
- Pablo Candido Pereira de Lana
- Ronald Luigi Galvão
- Maike da Silva Castilho

## Descrição
Este projeto apresenta um exemplo didático e bem documentado de treinamento de uma rede neural convolucional (CNN) utilizando o dataset MNIST de dígitos manuscritos. O código foi desenvolvido em Python com PyTorch e inclui funções para carregamento dos dados, definição do modelo, treinamento, avaliação, early stopping, visualização dos resultados e exemplos de uso.

## Modificações Realizadas
- **Batch size:** Alterado para 128
- **Learning rate:** Alterado para 0.0005
- **Paciência do Early Stopping:** Alterada para 5 épocas

Essas modificações foram feitas para buscar o melhor desempenho do modelo, conforme solicitado na atividade.

## Como Executar
1. Instale as dependências necessárias:
   ```bash
   pip install torch torchvision matplotlib numpy
   ```
2. Execute o notebook `2025_1_Treinamento_de_modelo_CNN_para_MNIST.ipynb` em um ambiente Jupyter Notebook ou Google Colab.
3. O notebook irá baixar automaticamente o dataset MNIST, treinar o modelo, aplicar early stopping e exibir gráficos de loss e acurácia, além de exemplos de classificação.

## Observações
- O código está extensamente comentado para facilitar o entendimento.
- Para testar outros valores de batch size, learning rate ou paciência, basta alterar os parâmetros correspondentes no notebook.

---

## Respostas às questões sobre o funcionamento do código

### 1. Quantas camadas convolucionais existem no modelo? Quais são seus tamanhos de kernel?
O modelo possui **duas camadas convolucionais**:
- Primeira camada: `nn.Conv2d(1, 32, kernel_size=3, padding=1)` → kernel 3x3
- Segunda camada: `nn.Conv2d(32, 64, kernel_size=3, padding=1)` → kernel 3x3

### 2. Por que usamos padding nas camadas convolucionais neste código?
O **padding** é utilizado para manter as dimensões espaciais (altura e largura) da imagem após a convolução. Com `padding=1` e `kernel_size=3`, a saída da convolução tem o mesmo tamanho da entrada, facilitando o cálculo das dimensões e evitando que a imagem fique muito pequena após várias camadas.

### 3. Qual a função da camada MaxPool2d? Como ela afeta as dimensões da imagem?
A camada **MaxPool2d** realiza uma operação de pooling (redução de dimensionalidade), pegando o valor máximo em regiões da imagem (normalmente 2x2). Isso reduz pela metade as dimensões espaciais (altura e largura) da imagem, tornando o processamento mais eficiente e ajudando a extrair características mais robustas.

### 4. Por que precisamos "achatar" (flatten) os dados antes da camada fully connected?
Após as camadas convolucionais e de pooling, os dados ainda estão em formato de múltiplos canais e dimensões espaciais (ex: [batch, canais, altura, largura]). Para passar para a camada **fully connected** (linear), precisamos transformar esses dados em um vetor 1D (flatten), pois as camadas lineares esperam entradas vetoriais.

### 5. Qual a finalidade das camadas de Dropout?
As camadas de **Dropout** servem para evitar overfitting durante o treinamento. Elas "desligam" aleatoriamente uma fração dos neurônios em cada iteração, forçando o modelo a não depender de caminhos específicos e tornando o aprendizado mais robusto.

---

Qualquer dúvida, entre em contato com um dos integrantes do grupo! 