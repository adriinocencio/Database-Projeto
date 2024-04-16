# Database-Projeto

### Apresentação:
[Apresentação Projeto Clínica Greenside - SQl DB](https://docs.google.com/presentation/d/1yT5mf9uAuse0tx13mvH4v_xmfMxdI4dIy_rsFveiliI/edit?usp=sharing)

### Código SQL:

```sql
-- Criação da tabela PACIENTES
CREATE TABLE PACIENTES (
    codigo INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100),
    endereco VARCHAR(255),
    cpf VARCHAR(14),
    data_nascimento DATE,
    email VARCHAR(100),
    telefone VARCHAR(20)
);

-- Criação da tabela MEDICOS
CREATE TABLE MEDICOS (
    codigo INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100),
    especialidade VARCHAR(100),
    endereco VARCHAR(255),
    cpf VARCHAR(14),
    data_nascimento DATE,
    email VARCHAR(100),
    telefone VARCHAR(20)
);

-- Criação da tabela CONSULTAS
CREATE TABLE CONSULTAS (
    codigo INT PRIMARY KEY AUTO_INCREMENT,
    codigo_paciente INT,
    codigo_medico INT,
    data_consulta DATE,
    hora_consulta TIME,
    descricao TEXT,
    FOREIGN KEY (codigo_paciente) REFERENCES PACIENTES(codigo),
    FOREIGN KEY (codigo_medico) REFERENCES MEDICOS(codigo)
);




-- Inserção de dados fictícios na tabela PACIENTES
INSERT INTO PACIENTES (nome, endereco, cpf, data_nascimento, email, telefone) VALUES
('João Silva', 'Rua A, 123', '123.456.789-00', '1980-05-15', 'joao@example.com', '(11) 98765-4321'),
('Maria Santos', 'Avenida B, 456', '987.654.321-00', '1992-10-20', 'maria@example.com', '(22) 12345-6789'),
('José Oliveira', 'Rua C, 789', '456.789.123-00', '1985-03-08', 'jose@example.com', '(33) 54321-9876'),
('Ana Pereira', 'Rua D, 321', '654.321.987-00', '1976-12-30', 'ana@example.com', '(44) 24680-1357'),
('Carlos Souza', 'Avenida E, 654', '789.123.456-00', '1998-07-25', 'carlos@example.com', '(55) 13579-0246'),
('Mariana Lima', 'Rua F, 987', '321.654.987-00', '1989-09-18', 'mariana@example.com', '(66) 80246-3579'),
('Antônio Costa', 'Avenida G, 159', '987.654.321-00', '1982-02-14', 'antonio@example.com', '(77) 35791-6024'),
('Fernanda Castro', 'Rua H, 357', '456.789.123-00', '1995-06-03', 'fernanda@example.com', '(88) 91357-2460'),
('Paulo Santos', 'Avenida I, 753', '123.456.789-00', '1973-08-22', 'paulo@example.com', '(99) 57913-4026'),
('Aline Oliveira', 'Rua J, 753', '789.123.456-00', '1990-11-12', 'aline@example.com', '(11) 24680-1357'),
('Rafaela Pereira', 'Avenida K, 357', '654.321.987-00', '1987-04-17', 'rafaela@example.com', '(22) 57913-4026'),
('Gustavo Souza', 'Rua L, 159', '321.654.987-00', '1980-01-05', 'gustavo@example.com', '(33) 80246-3579'),
('Camila Lima', 'Avenida M, 753', '987.654.321-00', '1993-12-10', 'camila@example.com', '(44) 35791-6024'),
('Rodrigo Costa', 'Rua N, 357', '456.789.123-00', '1978-07-01', 'rodrigo@example.com', '(55) 91357-2460'),
('Juliana Castro', 'Avenida O, 753', '123.456.789-00', '1996-09-28', 'juliana@example.com', '(66) 24680-1357'),
('Lucas Santos', 'Rua P, 753', '789.123.456-00', '1984-05-03', 'lucas@example.com', '(77) 57913-4026'),
('Patrícia Oliveira', 'Avenida Q, 357', '654.321.987-00', '1991-03-14', 'patricia@example.com', '(88) 80246-3579'),
('Anderson Souza', 'Rua R, 159', '321.654.987-00', '1986-11-20', 'anderson@example.com', '(99) 35791-6024'),
('Tatiane Lima', 'Avenida S, 753', '987.654.321-00', '1979-10-07', 'tatiane@example.com', '(11) 91357-2460'),
('Eduardo Costa', 'Rua T, 357', '456.789.123-00', '1997-02-23', 'eduardo@example.com', '(22) 24680-1357'),
('Carolina Castro', 'Avenida U, 753', '123.456.789-00', '1983-06-19', 'carolina@example.com', '(33) 57913-4026'),
('Marcelo Santos', 'Rua V, 753', '789.123.456-00', '1994-08-26', 'marcelo@example.com', '(44) 80246-3579'),
('Beatriz Oliveira', 'Avenida W, 357', '654.321.987-00', '1981-01-31', 'beatriz@example.com', '(55) 35791-6024'),
('Ricardo Souza', 'Rua X, 159', '321.654.987-00', '1999-04-05', 'ricardo@example.com', '(66) 91357-2460'),
('Fernanda Lima', 'Avenida Y, 753', '987.654.321-00', '1974-11-11', 'fernanda@example.com', '(77) 24680-1357'),
('Alexandre Costa', 'Rua Z, 357', '456.789.123-00', '1988-07-30', 'alexandre@example.com', '(88) 57913-4026'),
('Patrícia Castro', 'Avenida AA, 753', '123.456.789-00', '1992-09-15', 'patricia@example.com', '(99) 80246-3579'),
('Roberto Santos', 'Rua BB, 753', '789.123.456-00', '1985-04-02', 'roberto@example.com', '(11) 35791-6024'),
('Mariana Oliveira', 'Avenida CC, 357', '654.321.987-00', '1977-12-07', 'mariana@example.com', '(22) 91357-2460'),
('José Souza', 'Rua DD, 159', '321.654.987-00', '1990-02-18', 'jose@example.com', '(33) 24680-1357'),
('Ana Santos', 'Avenida EE, 753', '987.654.321-00', '1986-05-26', 'ana@example.com', '(44) 57913-4026'),
('Rafael Oliveira', 'Rua FF, 357', '456.789.123-00', '1998-08-11', 'rafael@example.com', '(55) 80246-3579'),
('Vanessa Lima', 'Avenida GG, 753', '123.456.789-00', '1975-10-29', 'vanessa@example.com', '(66) 35791-6024'),
('Carlos Castro', 'Rua HH, 753', '789.123.456-00', '1989-03-07', 'carlos@example.com', '(77) 91357-2460'),
('Fernanda Oliveira', 'Avenida II, 357', '654.321.987-00', '1982-11-14', 'fernanda@example.com', '(88) 24680-1357'),
('Lucas Souza', 'Rua JJ, 159', '321.654.987-00', '1995-01-23', 'lucas@example.com', '(99) 57913-4026'),
('Mariana Costa', 'Avenida KK, 753', '987.654.321-00', '1978-06-09', 'mariana@example.com', '(11) 80246-3579'),
('Gabriel Santos', 'Rua LL, 753', '456.789.123-00', '1991-09-17', 'gabriel@example.com', '(22) 35791-6024'),
('Juliana Oliveira', 'Avenida MM, 357', '123.456.789-00', '1984-04-25', 'juliana@example.com', '(33) 91357-2460'),
('Marcos Castro', 'Rua NN, 159', '789.123.456-00', '1997-07-03', 'marcos@example.com', '(44) 24680-1357'),
('Amanda Lima', 'Avenida OO, 753', '654.321.987-00', '1980-12-20', 'amanda@example.com', '(55) 57913-4026'),
('Felipe Oliveira', 'Rua PP, 753', '321.654.987-00', '1993-03-28', 'felipe@example.com', '(66) 80246-3579'),
('Ana Costa', 'Avenida QQ, 357', '987.654.321-00', '1976-08-11', 'ana@example.com', '(77) 35791-6024'),
('Vinícius Santos', 'Rua RR, 159', '456.789.123-00', '1981-11-29', 'vinicius@example.com', '(88) 91357-2460'),
('Isabela Oliveira', 'Avenida SS, 753', '123.456.789-00', '1994-02-05', 'isabela@example.com', '(99) 24680-1357'),
('Pedro Castro', 'Rua TT, 753', '789.123.456-00', '1987-05-13', 'pedro@example.com', '(11) 57913-4026'),
('Carla Lima', 'Avenida UU, 357', '654.321.987-00', '1980-10-18', 'carla@example.com', '(22) 80246-3579'),
('Leandro Souza', 'Rua VV, 159', '321.654.987-00', '1996-01-27', 'leandro@example.com', '(33) 35791-6024'),
('Raquel Costa', 'Avenida WW, 753', '987.654.321-00', '1979-04-07', 'raquel@example.com', '(44) 91357-2460'),
('Bruno Santos', 'Rua XX, 753', '456.789.123-00', '1982-07-15', 'bruno@example.com', '(55) 24680-1357'),
('Luiza Oliveira', 'Avenida YY, 357', '123.456.789-00', '1995-09-23', 'luiza@example.com', '(66) 57913-4026'),
('Gustavo Castro', 'Rua ZZ, 159', '789.123.456-00', '1988-12-31', 'gustavo@example.com', '(77) 80246-3579'),
('Bianca Lima', 'Avenida AAA, 753', '654.321.987-00', '1983-02-09', 'bianca@example.com', '(88) 35791-6024'),
('Marcela Souza', 'Rua BBB, 753', '321.654.987-00', '1990-05-16', 'marcela@example.com', '(99) 91357-2460');

-- Inserindo dados fictícios na tabela MEDICOS
INSERT INTO MEDICOS (nome, especialidade, endereco, cpf, data_nascimento, email, telefone)
VALUES
    ('Dr. Ricardo Mendes', 'Cardiologia', 'Rua das Flores, 123, São Paulo - SP', '123.456.789-00', '1975-08-20', 'ricardo.mendes@email.com', '(11) 98765-4321'),
    ('Dra. Camila Fernandes', 'Dermatologia', 'Av. das Palmeiras, 456, Rio de Janeiro - RJ', '987.654.321-00', '1980-05-15', 'camila.fernandes@email.com', '(21) 12345-6789'),
    ('Dr. Fernanda Oliveira', 'Ginecologia', 'Rua do Bosque, 789, Belo Horizonte - MG', '234.567.890-12', '1983-12-10', 'fernanda.oliveira@email.com', '(31) 23456-7890'),
    ('Dr. André Santos', 'Ortopedia', 'Av. dos Estados, 321, Porto Alegre - RS', '345.678.901-23', '1978-07-25', 'andre.santos@email.com', '(51) 34567-8901'),
    ('Dra. Marina Costa', 'Pediatria', 'Rua das Gaivotas, 456, Florianópolis - SC', '456.789.012-34', '1985-03-18', 'marina.costa@email.com', '(48) 45678-9012'),
    ('Dr. Lucas Rodrigues', 'Oftalmologia', 'Av. Central, 987, Brasília - DF', '567.890.123-45', '1980-11-05', 'lucas.rodrigues@email.com', '(61) 56789-0123'),
    ('Dra. Patrícia Lima', 'Endocrinologia', 'Rua das Rosas, 789, Salvador - BA', '678.901.234-56', '1976-09-30', 'patricia.lima@email.com', '(71) 67890-1234');

-- Inserindo dados fictícios na tabela CONSULTAS
INSERT INTO CONSULTAS (codigo_paciente, codigo_medico, data_consulta, hora_consulta, descricao)
VALUES 
    (1, 1, '2024-04-17', '10:00:00', 'Consulta de rotina'),
    (2, 2, '2024-04-18', '14:30:00', 'Consulta para verificar quadro gripal'),
    (1, 1, '2024-04-20', '09:00:00', 'Consulta de acompanhamento cardiológico'),
    (2, 2, '2024-04-21', '10:30:00', 'Consulta dermatológica para tratamento de acne'),
    (1, 3, '2024-04-22', '14:00:00', 'Consulta ginecológica de rotina'),
    (2, 4, '2024-04-23', '11:00:00', 'Consulta ortopédica para lesão no joelho'),
    (1, 5, '2024-04-24', '15:30:00', 'Consulta pediátrica para vacinação');
```
