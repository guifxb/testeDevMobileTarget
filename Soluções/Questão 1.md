# Resolução do Desafio 1 - Target Sistemas
  

## Descrição do Problema  

Dado o seguinte trecho de código:  

```c
int INDICE = 12, SOMA = 0, K = 1; 
enquanto K < INDICE faça
{
K = K + 1;
SOMA = SOMA + K;
} 
imprimir(SOMA);
```
Nosso objetivo é descobrir o valor final da variável `SOMA` após o processamento.,

## Análise

Esse código pode ser descrito da seguinte forma:

1.  Temos três variáveis: `INDICE`, `SOMA` e `K`.
    -   `INDICE = 12`
    -   `SOMA = 0`
    -   `K = 1`
2.  O loop vai rodar enquanto `K < INDICE`, e a cada iteração:
    -   `K` é incrementado em 1.
    -   O valor de `K` é adicionado à variável `SOMA`.
3.  No final do loop, a variável `SOMA` será impressa.

Agora, vamos converter esse código para **Dart** e verificar o valor final da variável `SOMA`.

## Código em Dart

Aqui está a implementação em **Dart** para resolver o problema:

````
void main() {
  int indice = 12;
  int soma = 0;
  int k = 1;

  while (k < indice) {
    k = k + 1;
    soma = soma + k;
  }

  print(soma);
}
````

### Explicação

1.  Definimos as variáveis `indice`, `soma` e `k` com os valores iniciais.
2.  O loop `while` continua rodando enquanto `k < indice`. A cada iteração:
    -   `k` é incrementado.
    -   O valor de `k` é adicionado à variável `soma`.
3.  No final do loop, o valor final de `soma` é impresso.

### Saída do Código

Quando rodamos esse código em **Dart**, o valor final impresso para a variável `soma` é:
```
77
```