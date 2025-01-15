# Python Commands Cheat Sheet

Este documento apresenta um tutorial abrangente de comandos Python, explicando o que cada um faz. Ideal para iniciantes e desenvolvedores intermediários!

---

## **1. Comandos Básicos**

### `print()`

- Exibe mensagens ou resultados no console.
- **Exemplo:**
  ```python
  print("Hello, World!")
  # Saída: Hello, World!
  ```

### `input()`

- Recebe entrada do usuário.
- **Exemplo:**
  ```python
  nome = input("Digite seu nome: ")
  print("Olá,", nome)
  ```

### `type()`

- Retorna o tipo de dado de um objeto.
- **Exemplo:**
  ```python
  print(type(42))
  # Saída: <class 'int'>
  ```

### `len()`

- Retorna o comprimento de uma sequência (string, lista, etc.).
- **Exemplo:**
  ```python
  print(len("Python"))
  # Saída: 6
  ```

---

## **2. Operadores Matemáticos**

### `+` (Adição)

- Soma dois valores.
- **Exemplo:**
  ```python
  print(5 + 3)
  # Saída: 8
  ```

### `-` (Subtração)

- Subtrai dois valores.
- **Exemplo:**
  ```python
  print(10 - 7)
  # Saída: 3
  ```

### `*` (Multiplicação)

- Multiplica dois valores.
- **Exemplo:**
  ```python
  print(4 * 2)
  # Saída: 8
  ```

### `/` (Divisão)

- Realiza divisão.
- **Exemplo:**
  ```python
  print(9 / 3)
  # Saída: 3.0
  ```

### `//` (Divisão Inteira)

- Retorna apenas a parte inteira da divisão.
- **Exemplo:**
  ```python
  print(10 // 3)
  # Saída: 3
  ```

### `%` (Módulo)

- Retorna o resto da divisão.
- **Exemplo:**
  ```python
  print(10 % 3)
  # Saída: 1
  ```

### `**` (Exponenciação)

- Eleva um número a uma potência.
- **Exemplo:**
  ```python
  print(2 ** 3)
  # Saída: 8
  ```

---

## **3. Controle de Fluxo**

### `if`, `elif`, `else`

- Estruturas condicionais.
- **Exemplo:**
  ```python
  x = 10
  if x > 5:
      print("Maior que 5")
  elif x == 5:
      print("Igual a 5")
  else:
      print("Menor que 5")
  ```

### `for`

- Loop que itera sobre sequências.
- **Exemplo:**
  ```python
  for i in range(5):
      print(i)
  # Saída: 0, 1, 2, 3, 4
  ```

### `while`

- Loop baseado em condição.
- **Exemplo:**
  ```python
  count = 0
  while count < 5:
      print(count)
      count += 1
  ```

### `break`

- Encerra o loop atual.
- **Exemplo:**
  ```python
  for i in range(10):
      if i == 5:
          break
      print(i)
  ```

### `continue`

- Pula para a próxima iteração.
- **Exemplo:**
  ```python
  for i in range(5):
      if i == 2:
          continue
      print(i)
  ```

---

## **4. Trabalhando com Listas**

### `append()`

- Adiciona um elemento ao final da lista.
- **Exemplo:**
  ```python
  lista = [1, 2, 3]
  lista.append(4)
  print(lista)
  # Saída: [1, 2, 3, 4]
  ```

### `remove()`

- Remove a primeira ocorrência de um valor na lista.
- **Exemplo:**
  ```python
  lista = [1, 2, 3, 4]
  lista.remove(2)
  print(lista)
  # Saída: [1, 3, 4]
  ```

### `pop()`

- Remove e retorna o último elemento (ou o índice especificado).
- **Exemplo:**
  ```python
  lista = [1, 2, 3]
  ultimo = lista.pop()
  print(ultimo)
  # Saída: 3
  ```

### `sort()`

- Ordena a lista.
- **Exemplo:**
  ```python
  lista = [3, 1, 4, 2]
  lista.sort()
  print(lista)
  # Saída: [1, 2, 3, 4]
  ```

### `reverse()`

- Inverte a ordem da lista.
- **Exemplo:**
  ```python
  lista = [1, 2, 3]
  lista.reverse()
  print(lista)
  # Saída: [3, 2, 1]
  ```

---

## **5. Funções**

### `def`

- Define uma função.
- **Exemplo:**

  ```python
  def saudacao(nome):
      return f"Olá, {nome}!"

  print(saudacao("Maria"))
  ```

### `lambda`

- Cria funções anônimas.
- **Exemplo:**
  ```python
  soma = lambda x, y: x + y
  print(soma(2, 3))
  # Saída: 5
  ```

---

## **6. Trabalhando com Dicionários**

### `keys()`

- Retorna as chaves do dicionário.
- **Exemplo:**
  ```python
  dicionario = {"nome": "João", "idade": 30}
  print(dicionario.keys())
  ```

### `values()`

- Retorna os valores do dicionário.
- **Exemplo:**
  ```python
  print(dicionario.values())
  ```

### `items()`

- Retorna chaves e valores como tuplas.
- **Exemplo:**
  ```python
  print(dicionario.items())
  ```

### `get()`

- Retorna o valor de uma chave.
- **Exemplo:**
  ```python
  print(dicionario.get("nome"))
  # Saída: João
  ```

---

## **7. Manipulação de Arquivos**

### `open()`

- Abre um arquivo para leitura ou escrita.
- **Exemplo:**
  ```python
  with open("arquivo.txt", "r") as file:
      conteudo = file.read()
      print(conteudo)
  ```

### `write()`

- Escreve em um arquivo.
- **Exemplo:**
  ```python
  with open("arquivo.txt", "w") as file:
      file.write("Olá, arquivo!")
  ```

---
