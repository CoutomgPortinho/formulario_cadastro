# 📦 Desafio: Cadastro de Produtos com Validação em PHP e MySQL

Este repositório contém a solução para o desafio prático **`10a_desafio2`**, que consiste no desenvolvimento de um sistema web para cadastro de produtos com validação de dados no servidor e persistência em banco de dados MySQL.

## 🎯 Objetivos do Projeto

O objetivo principal é construir um formulário interativo em PHP para o envio de dados de produtos, garantindo a validação adequada dos campos antes do salvamento no banco de dados `exercicio`.

### 📋 Requisitos da Aplicação

* \[x\] **Banco de Dados**: Criar a tabela `produtos` no banco de dados `exercicio` através de script SQL.

* \[x\] **Formulário Web**: Exibir campos para inserção do **Nome do Produto** e **Preço**.

* \[x\] **Validação no Servidor (PHP)**:

  * Garantir que o nome do produto não esteja vazio.

  * Garantir que o preço seja numérico e **maior que zero**.

* \[x\] **Respostas de Status**:

  * **Sucesso**: Exibir a mensagem `"Produto cadastrado com sucesso!"`.

  * **Falha/Validação**: Exibir mensagem de erro informativa (ex: `"Erro: O preço deve ser um número positivo."`).

## 🗄️️ Estrutura do Banco de Dados

Para preparar o ambiente, crie o banco de dados `exercicio` e a tabela `produtos` executando o script SQL abaixo:

```
CREATE DATABASE IF NOT EXISTS exercicio;
USE exercicio;

CREATE TABLE IF NOT EXISTS produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(150) NOT NULL,
    preco DECIMAL(10, 2) NOT NULL,
    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

```

## 🛠️ Tecnologias Utilizadas

* **PHP 8.x** — Lógica de validação e conexão com o banco de dados.

* **MySQL / MariaDB** — Armazenamento dos dados.

* **HTML5 & CSS3** — Interface e formulário do usuário.

## 📂 Estrutura do Projeto

```
.
├── config.php          # Arquivo com as configurações de conexão PDO/MySQLi
├── index.php           # Formulário HTML e lógica PHP de validação/inserção
├── 10a_desafio2.md     # Instruções originais do desafio
└── README.md           # Documentação do projeto

```

## 🚀 Como Executar o Projeto

1. **Clone este repositório** na pasta de projetos do seu servidor web (ex: `htdocs` no XAMPP ou `www` no WAMP):

   ```
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   
   ```

2. **Inicie os serviços do servidor local** (Apache e MySQL).

3. **Crie a tabela no Banco de Dados**:

   * Acesse o phpMyAdmin (`http://localhost/phpmyadmin`) ou o terminal do MySQL.

   * Execute o script contido na seção [Estrutura do Banco de Dados](#-estrutura-do-banco-de-dados).

4. **Acesse a aplicação no seu navegador**:

   ```
   http://localhost/nome-do-repositorio/index.php
   
   ```

## 🧪 Regras de Validação Demonstradas

| **Cenário** | **Entrada (Nome / Preço)** | **Resultado Esperado** | 
| **Campos Vazios** | `""` / `""` | `Erro: Preencha todos os campos.` | 
| **Preço Inválido** | `"Teclado"` / `-15.00` | `Erro: O preço deve ser um número positivo.` | 
| **Preço Zero** | `"Mouse"` / `0.00` | `Erro: O preço deve ser um número positivo.` | 
| **Cadastro Válido** | `"Monitor 24"` / `799.90` | `Produto cadastrado com sucesso!` | 

## 📝 Licença

Este projeto é fruto de um exercício prático para estudo de PHP e Banco de Dados. Sinta-se à vontade para reutilizar ou aprimorar a solução.
