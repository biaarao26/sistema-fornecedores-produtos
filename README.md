# Sistema de cadastro de fornecedor e produto
## Criaçao do Banco de dados

CREATE DATABASE sistema CHARACTER SET utf8mb4;


## Criar tabela usuarios
-- Expressão SQL para criar a tabela de usuários
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario VARCHAR(50) NOT NULL,
    senha VARCHAR(255) NOT NULL
);

## Criar tabela fornecedores
-- Expressão SQL para criar a tabela de fornecedores
CREATE TABLE fornecedores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100),
    telefone VARCHAR(20)
);

## Criar tabela produtos
-- Expressão SQL para criar a tabela de produtos relacionada via FK com a tabela de fornecedores
CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    fornecedor_id INT,
    nome VARCHAR(100) NOT NULL,
    descricao TEXT,
    preco DECIMAL(10, 2),
    FOREIGN KEY (fornecedor_id) REFERENCES fornecedores(id)
);

