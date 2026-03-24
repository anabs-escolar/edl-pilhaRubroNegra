# Pilha Rubro-Negra com Array

## Descrição

Este projeto consiste na implementação de uma estrutura de dados que simula duas pilhas dentro de um único array:

* **Pilha Rubro (R)**: cresce da esquerda para a direita
* **Pilha Negro (N)**: cresce da direita para a esquerda

O objetivo é otimizar o uso de memória utilizando um único array compartilhado entre as duas pilhas.

---

## Como começar (fork do repositório)

1. Faça um fork deste repositório para sua conta
2. Clone o fork para sua máquina (ou abra um Codespaces):

   ```bash
   git clone <url-do-seu-fork>
   ```
3. Abra o projeto na sua IDE de preferência (IntelliJ, Eclipse, VS Code)
4. Localize a classe `PilhaArrayRubroNegra`
5. Implemente os métodos indicados

---

## Estrutura da classe

A classe já possui os seguintes atributos:

* `capacidade`: tamanho do array
* `arr`: array que armazena os elementos
* `topRubro`: topo da pilha rubro (inicia em -1)
* `topNegro`: topo da pilha negro (inicia em `capacidade`)

---

## Estratégia de implementação (ordem recomendada)

Siga esta ordem para evitar erros e facilitar testes:

### 1. Operações básicas de inserção (push)

Implemente primeiro:

* `pushR(Object o)`
* `pushN(Object o)`

Regras:

* Antes de inserir, verifique se há espaço
* Caso não haja espaço, chame `grow()`

---

### 2. Operações básicas de remoção (pop)

Implemente:

* `popR()`
* `popN()`

Regras:

* Verifique se a pilha correspondente está vazia
* Lance `PilhaVaziaExcecao` se necessário
* Após remover, considere chamar `shirink()` se o uso estiver baixo

---

### 3. Consultas ao topo (top)

Implemente:

* `topR()`
* `topN()`

Regras:

* Apenas retornam o elemento sem remover
* Devem lançar exceção se a pilha estiver vazia

---

### 4. Métodos auxiliares

* `isEmpty()`
    * Retorna `true` se ambas as pilhas estiverem vazias


* `size()`
    * Retorna a quantidade de elementos de ambas as pilhas

---

### 5. Redimensionamento

#### `grow()`

* Dobra a capacidade do array
* Copia:

  * Pilha rubro mantém posição inicial
  * Pilha negro deve continuar alinhada à direita

Passos:

1. Criar novo array com o dobro do tamanho
2. Copiar elementos da pilha rubra
3. Copiar elementos da pilha negra para o final do novo array
4. Atualizar `topNegro`

---

#### `shirink()`

* Reduz pela metade se o uso for baixo (ex: 1/3 de uso)
* Mesma lógica de cópia do `grow()`

---

## Dicas importantes

* Nunca permita que `topRubro` ultrapasse `topNegro`
* Sempre atualize os índices corretamente após inserção/remoção
* Teste cada método isoladamente antes de avançar
* Use prints ou debug para acompanhar o comportamento

---

## Executando Testes

Execute:

```bash
mvn test
```

---

## Conclusão

A implementação exige atenção ao controle de índices e ao redimensionamento do array. Seguir a ordem sugerida ajuda a evitar erros e facilita a validação da estrutura.

---
