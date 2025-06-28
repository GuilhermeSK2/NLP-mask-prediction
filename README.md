# Preenchimento de Máscaras com BERT em Português

Este projeto demonstra a capacidade de um modelo de linguagem pré-treinado, o BERT base em português (`neuralmind/bert-base-portuguese-cased`), para prever palavras ausentes em uma sentença. A tarefa de "preenchimento de máscaras" (fill-mask) é fundamental para entender como os modelos de linguagem aprendem o contexto e a semântica da língua.

## Visão Geral

Modelos como o BERT (Bidirectional Encoder Representations from Transformers) são treinados em uma grande quantidade de texto e aprendem a entender o contexto bidirecional das palavras. A tarefa de fill-mask é um dos principais objetivos de treinamento desses modelos, onde o modelo tenta prever uma palavra que foi intencionalmente "mascarada" (substituída por `[MASK]`) em uma frase. Este projeto utiliza a biblioteca `transformers` da Hugging Face para carregar e usar um modelo BERT em português.

## Estrutura do Projeto

* `Fillmask.ipynb`: O notebook Jupyter que contém todo o código para configurar o ambiente, carregar o modelo e realizar as previsões de preenchimento de máscaras.

## Tecnologias Utilizadas

* **Python 3**
* **Hugging Face `transformers` library**: Para acesso e utilização do modelo BERT.
* **Jupyter Notebook**: Para execução e demonstração interativa do código.
* **Modelo**: `neuralmind/bert-base-portuguese-cased` (um modelo BERT pré-treinado para a língua portuguesa).

## Exemplo de Uso

No notebook, você pode modificar a(s) frase(s) na variável `texto` e incluir o token `[MASK]` onde deseja que o modelo preveja uma palavra. O modelo retornará uma lista das palavras mais prováveis para preencher a máscara, juntamente com suas pontuações de confiança.

```python
# Exemplo de uma única frase
frase1 = "O [MASK] é um dos esportes mais populares do Brasil."
print(mascarar(frase1))

# Exemplo com múltiplas frases
frases = [
    "Ontem, eu fui ao [MASK] para comprar pão.",
    "A inteligência artificial tem um grande [MASK] no futuro da tecnologia."
]
for resultado in mascarar(frases):
    print(resultado)
