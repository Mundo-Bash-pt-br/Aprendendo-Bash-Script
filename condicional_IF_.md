# Uso do `if` no Shell

O comando `if` no shell é usado para executar comandos condicionalmente, baseado no resultado de uma expressão ou comando. Ele é útil em scripts para tomada de decisões.

---

## **Sintaxe básica:**

```bash
if [ condição ]; then
    # comandos a serem executados se a condição for verdadeira
fi
```

### **Variantes mais comuns:**

1. **`if-else`:**
   ```bash
   if [ condição ]; then
       # comandos se a condição for verdadeira
   else
       # comandos se a condição for falsa
   fi
   ```

2. **`if-elif-else`:**
   ```bash
   if [ condição1 ]; then
       # comandos se condição1 for verdadeira
   elif [ condição2 ]; then
       # comandos se condição2 for verdadeira
   else
       # comandos se todas as condições forem falsas
   fi
   ```

---

## **Exemplos de uso:**

### **Com strings:**

```bash
#!/bin/bash

read -p "Digite seu nome: " nome

if [ "$nome" == "admin" ]; then
    echo "Bem-vindo, administrador!"
else
    echo "Olá, $nome!"
fi
```

### **Com números:**

```bash
#!/bin/bash

read -p "Digite um número: " num

if [ "$num" -gt 10 ]; then
    echo "O número é maior que 10."
elif [ "$num" -eq 10 ]; then
    echo "O número é igual a 10."
else
    echo "O número é menor que 10."
fi
```

---

## **Testando arquivos e diretórios:**

- Verificar se um arquivo existe:
  ```bash
  if [ -f arquivo.txt ]; then
      echo "O arquivo existe."
  else
      echo "O arquivo não existe."
  fi
  ```

- Verificar se um diretório existe:
  ```bash
  if [ -d /caminho/para/diretorio ]; then
      echo "O diretório existe."
  else
      echo "O diretório não existe."
  fi
  ```

---

## **Uso avançado com comandos:**

Verificar o sucesso de um comando usando seu **código de saída**:

```bash
if ping -c 1 google.com &> /dev/null; then
    echo "Conexão com a internet está disponível."
else
    echo "Sem conexão com a internet."
fi
```

---

## **Operadores comuns no `if`:**

### **Para strings:**
- `[ "$str1" == "$str2" ]`: Verdadeiro se as strings forem iguais.
- `[ "$str1" != "$str2" ]`: Verdadeiro se as strings forem diferentes.
- `[ -z "$str" ]`: Verdadeiro se a string for vazia.
- `[ -n "$str" ]`: Verdadeiro se a string não for vazia.

### **Para números:**
- `-eq`: Igual a (`[ "$num1" -eq "$num2" ]`).
- `-ne`: Diferente de (`[ "$num1" -ne "$num2" ]`).
- `-gt`: Maior que.
- `-lt`: Menor que.
- `-ge`: Maior ou igual a.
- `-le`: Menor ou igual a.

### **Para arquivos:**
- `-f`: Existe e é um arquivo regular.
- `-d`: Existe e é um diretório.
- `-r`: Arquivo é legível.
- `-w`: Arquivo é gravável.
- `-x`: Arquivo é executável.

---

Com essas informações, você pode criar scripts interativos e dinâmicos no shell! Se precisar de mais exemplos, é só pedir. 😊
