## Arquivo .sql

[Banco de Dados.zip](https://github.com/user-attachments/files/23831002/Dump20251128.1.zip)

## Scripts SQL.

<code>
-- Tabela Unidade
CREATE TABLE unidade (
idunidade INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
nome VARCHAR(100) NOT NULL,
endereco VARCHAR(150),
telefone VARCHAR(15),
data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP
);


-- Tabela Cliente
CREATE TABLE cliente (
idcliente INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
nome VARCHAR(100) NOT NULL,
tipopessoa ENUM('FISICA','JURIDICA') NOT NULL,
cpf CHAR(11),
cnpj CHAR(14),
numero_cnh VARCHAR(20),
cep CHAR(8),
numero_casa VARCHAR(10),
email VARCHAR(100),
senha VARCHAR(255) NOT NULL,
data_nascimento DATE,
telefone VARCHAR(15),
data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
data_atualizacao DATETIME ON UPDATE CURRENT_TIMESTAMP,
tipo_cnh ENUM('A','B','AB','C','D','E')
);


-- Tabela Funcionario
CREATE TABLE funcionario (
idfuncionario INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
nome VARCHAR(100) NOT NULL,
cpf CHAR(11) NOT NULL UNIQUE,
cep CHAR(8),
numero_casa VARCHAR(10),
email VARCHAR(100),
senha VARCHAR(100) NOT NULL,
telefone VARCHAR(15),
matricula VARCHAR(20) NOT NULL UNIQUE,
cargo VARCHAR(50),
permissao ENUM('GERENTE','ATENDENTE') DEFAULT 'ATENDENTE',
idunidade INT,
data_nascimento DATE,
data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
ativo TINYINT(1) DEFAULT 1,
ultimo_login DATETIME,
FOREIGN KEY (idunidade) REFERENCES unidade(idunidade)
);


-- Tabela Automoveis
CREATE TABLE automoveis (
idautomovel INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
placa VARCHAR(10) NOT NULL UNIQUE,
chassi VARCHAR(50) NOT NULL UNIQUE,
status ENUM('DISPONIVEL','ALUGADO','MANUTENCAO','RESERVADO') DEFAULT 'DISPONIVEL',
cor VARCHAR(30),
ano YEAR,
modelo VARCHAR(50) NOT NULL,
marca VARCHAR(50) NOT NULL,
grupo ENUM('Econômicos','Esportivos','Sedans','SUV','Picapes','Luxo','Elétricos-Híbridos','Minivan-Vans') DEFAULT 'Econômicos',
cnh_necessaria ENUM('A','B','C','D','E') DEFAULT 'B',
valor DECIMAL(10,2) NOT NULL DEFAULT 0.00,
idunidade INT,
descricaoTexto TEXT,
caracteristicas VARCHAR(500),
data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
data_atualizacao DATETIME ON UPDATE CURRENT_TIMESTAMP,
FOREIGN KEY (idunidade) REFERENCES unidade(idunidade)
);


-- Tabela Aluguel
CREATE TABLE aluguel (
idaluguel INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
idcliente INT NOT NULL,
idautomovel INT NOT NULL,
idfuncionario INT,
data_inicio DATE NOT NULL,
data_fim DATE NOT NULL,
valor_previsto DECIMAL(10,2) NOT NULL,
valor_final DECIMAL(10,2),
seguro TINYINT(1) DEFAULT 0,
status ENUM('RESERVADO','EM_ANDAMENTO','FINALIZADO','CANCELADO') DEFAULT 'RESERVADO',
data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
data_atualizacao DATETIME ON UPDATE CURRENT_TIMESTAMP,
tipo_seguro ENUM('SEM SEGURO','BÁSICO','COMPLETO','PREMIUM') DEFAULT 'SEM SEGURO',
FOREIGN KEY (idcliente) REFERENCES cliente(idcliente),
FOREIGN KEY (idautomovel) REFERENCES automoveis(idautomovel),
FOREIGN KEY (idfuncionario) REFERENCES funcionario(idfuncionario)
);


-- Tabela Avaliacao
CREATE TABLE avaliacao (
idAvaliacao INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
idCliente INT NOT NULL,
idAluguel INT NOT NULL,
nota TINYINT NOT NULL,
comentario TEXT,
dataAvaliacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
FOREIGN KEY (idCliente) REFERENCES cliente(idcliente),
FOREIGN KEY (idAluguel) REFERENCES aluguel(idaluguel)
);


-- Tabela AvaliacaoSite
CREATE TABLE avaliacaoSite (
idavaliacaosite INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
idcliente INT NOT NULL,
nota INT NOT NULL,
comentario TEXT,
data_avaliacao DATETIME DEFAULT CURRENT_TIMESTAMP,
FOREIGN KEY (idcliente) REFERENCES cliente(idcliente)
);


-- Tabela ImgAutomovel
CREATE TABLE imgautomovel (
idimgautomovel INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
idautomovel INT NOT NULL,
img1 VARCHAR(255),
img2 VARCHAR(255),
img3 VARCHAR(255),
img4 VARCHAR(255),
img5 VARCHAR(255),
img6 VARCHAR(255),
FOREIGN KEY (idautomovel) REFERENCES automoveis(idautomovel)
);


-- Tabela ListaNegra
CREATE TABLE listanegra (
idlista_negra INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
idcliente INT NOT NULL UNIQUE,
idfuncionario INT,
motivo TEXT,
data_inclusao DATETIME DEFAULT CURRENT_TIMESTAMP,
FOREIGN KEY (idcliente) REFERENCES cliente(idcliente),
FOREIGN KEY (idfuncionario) REFERENCES funcionario(idfuncionario)
);


-- Tabela Manutencao
CREATE TABLE manutencao (
idmanutencao INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
idautomovel INT NOT NULL,
descricao TEXT,
data_manutencao DATE,
valor DECIMAL(10,2),
data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
FOREIGN KEY (idautomovel) REFERENCES automoveis(idautomovel)
);


-- Tabela Pagamento
CREATE TABLE pagamento (
idpagamento INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
idaluguel INT NOT NULL,
idfuncionario INT,
forma_pagamento VARCHAR(50) NOT NULL,
valor DECIMAL(10,2) NOT NULL,
data_pagamento DATE NOT NULL,
status ENUM('PENDENTE','PAGO','CANCELADO') DEFAULT 'PENDENTE',
data_cadastro DATETIME DEFAULT CURRENT_TIMESTAMP,
FOREIGN KEY (idaluguel) REFERENCES aluguel(idaluguel),
FOREIGN KEY (idfuncionario) REFERENCES funcionario(idfuncionario)
);
</code>
