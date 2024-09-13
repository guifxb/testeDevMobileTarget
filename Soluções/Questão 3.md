
# Resolução do Desafio 3 - Target Sistemas 

## Descrição do Problema 

Dado um vetor que guarda o valor de faturamento diário de uma distribuidora durante um ano, precisamos: 

1. Encontrar o menor valor de faturamento ocorrido em um dia do ano.
2. Encontrar o maior valor de faturamento ocorrido em um dia do ano.
3. Calcular o número de dias no ano em que o valor de faturamento diário foi superior à média anual.
  
### Condições: 

- Devemos desconsiderar os dias sem faturamento (finais de semana e feriados) no cálculo da média.  

## Solução  

O programa carrega os dados fictícios de faturamento de um arquivo (que simula os dados de todos os dias do ano), realiza as operações de cálculo em funções separadas, e retorna os resultados. Abaixo está o código.  

```python
import json  

# Função para carregar os dados fictícios do arquivo de faturamento diário
def  carregar_faturamento(caminho_arquivo):
with  open(caminho_arquivo, 'r') as file:
return json.load(file) 

# Função para calcular o menor valor de faturamento diário, excluindo dias sem faturamento
def  menor_faturamento(faturamentos):
return  min([f for f in faturamentos if f > 0]) 

# Função para calcular o maior valor de faturamento diário
def  maior_faturamento(faturamentos):
return  max(faturamentos) 

# Função para calcular a média anual, ignorando dias sem faturamento
def  media_anual(faturamentos):
faturamentos_validos = [f for f in faturamentos if f > 0]
return  sum(faturamentos_validos) / len(faturamentos_validos)  

# Função para contar o número de dias com faturamento acima da média
def  dias_acima_da_media(faturamentos, media):
return  len([f for f in faturamentos if f > media])  

# Função principal que chama as demais funções e imprime os resultados
def  analisar_faturamento(caminho_arquivo):
faturamentos = carregar_faturamento(caminho_arquivo)
menor = menor_faturamento(faturamentos)
maior = maior_faturamento(faturamentos)
media = media_anual(faturamentos)
dias_acima = dias_acima_da_media(faturamentos, media)  

print(f"Menor faturamento do ano: {menor}")
print(f"Maior faturamento do ano: {maior}")
print(f"Número de dias com faturamento acima da média anual: {dias_acima}")  

# Executando o programa com um arquivo fictício
if  __name__ == "__main__":
caminho_arquivo = 'faturamento_diario.json'
analisar_faturamento(caminho_arquivo)
``` 
  
### Arquivo Fictício de Faturamento (`faturamento_diario.json`):
  
```
[
1200, 1500, 0, 2500, 0, 3000, 2750, 2000, 1800, 0, 0, 3200,
2100, 1950, 0, 2300, 0, 2500, 2100, 0, 1700, 1800, 1900, 0
]
```  

## Explicação do Código  

1.  **Carregar Dados**: A função `carregar_faturamento` lê os dados de faturamento de um arquivo **JSON**.

2.  **Menor Faturamento**: A função `menor_faturamento` retorna o menor valor de faturamento, excluindo os dias com valor zero (sem faturamento).

3.  **Maior Faturamento**: A função `maior_faturamento` encontra o maior valor no vetor de faturamento.

4.  **Média Anual**: A função `media_anual` calcula a média apenas dos dias com faturamento (valores maiores que zero).

5.  **Dias Acima da Média**: A função `dias_acima_da_media` retorna o número de dias em que o faturamento foi superior à média anual.  

### Saída Esperada  

Ao rodar o programa, a saída seria algo semelhante a:  

```
Menor faturamento do ano: 1200
Maior faturamento do ano: 3200
Número de dias com faturamento acima da média anual: 6
```

Essa solução é organizada, com funções separadas para cada tarefa, e carrega os dados de faturamento a partir de um arquivo JSON fictício.