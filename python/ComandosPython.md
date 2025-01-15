# Python CLI Commands Cheat Sheet

Este documento apresenta um tutorial sobre os comandos da linha de comando (CLI) do Python, explicando suas funcionalidades. Ideal para desenvolvedores que utilizam o terminal para interagir com o Python!

---

## **1. Executar o Interpretador Python**

### `python` ou `python3`

- Inicia o interpretador Python no terminal.
- **Exemplo:**
  ```bash
  python
  # ou
  python3
  ```
  - Você entrará no modo interativo do Python onde poderá executar comandos diretamente.

---

## **2. Verificar a Versão do Python**

### `python --version` ou `python3 --version`

- Exibe a versão instalada do Python.
- **Exemplo:**
  ```bash
  python --version
  # Saída: Python 3.x.x
  ```

---

## **3. Executar Scripts Python**

### `python script.py` ou `python3 script.py`

- Executa um script Python.
- **Exemplo:**
  ```bash
  python script.py
  ```
  - Onde `script.py` é o arquivo contendo o código Python.

---

## **4. Instalar Pacotes com `pip`**

### `pip install nome_do_pacote`

- Instala pacotes Python a partir do PyPI.
- **Exemplo:**
  ```bash
  pip install requests
  ```

### `pip list`

- Lista os pacotes instalados no ambiente Python.
- **Exemplo:**
  ```bash
  pip list
  ```

### `pip uninstall nome_do_pacote`

- Remove um pacote instalado.
- **Exemplo:**
  ```bash
  pip uninstall requests
  ```

---

## **5. Criar e Gerenciar Ambientes Virtuais**

### `python -m venv nome_do_ambiente`

- Cria um ambiente virtual.
- **Exemplo:**
  ```bash
  python -m venv meu_ambiente
  ```

### `source nome_do_ambiente/bin/activate` (Linux/Mac) ou `nome_do_ambiente\Scripts\activate` (Windows)

- Ativa o ambiente virtual.
- **Exemplo:**
  ```bash
  source meu_ambiente/bin/activate
  ```

### `deactivate`

- Desativa o ambiente virtual.
- **Exemplo:**
  ```bash
  deactivate
  ```

---

## **6. Iniciar um Servidor HTTP Simples**

### `python -m http.server`

- Inicia um servidor HTTP simples na porta 8000.
- **Exemplo:**
  ```bash
  python -m http.server
  ```

### `python -m http.server 8080`

- Especifica a porta para o servidor.
- **Exemplo:**
  ```bash
  python -m http.server 8080
  ```

---

## **7. Executar um Comando Python**

### `python -c "comando_python"`

- Executa um comando Python diretamente no terminal.
- **Exemplo:**
  ```bash
  python -c "print('Hello, World!')"
  ```

---

## **8. Verificar Módulos Instalados**

### `python -m site`

- Lista os diretórios de pacotes padrão e locais.
- **Exemplo:**
  ```bash
  python -m site
  ```

---

## **9. Depurar Código Python**

### `python -m pdb script.py`

- Inicia o depurador (debugger) para o script Python.
- **Exemplo:**
  ```bash
  python -m pdb script.py
  ```

---

## **10. Documentação e Ajuda**

### `python -m pydoc nome_do_módulo`

- Exibe a documentação de um módulo.
- **Exemplo:**
  ```bash
  python -m pydoc math
  ```

### `python -m pydoc -b`

- Inicia um servidor de documentação acessível via navegador.
- **Exemplo:**
  ```bash
  python -m pydoc -b
  ```
