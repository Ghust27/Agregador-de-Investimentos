# Agregador‑de‑Investimentos

Projeto: **Agregador‑de‑Investimentos**  
Autor: [Seu Nome ou Usuário]  
Data de Início: (inserir)  
Versão: 0.x (protótipo)

## 🧾 Visão Geral

O Agregador‑de‑Investimentos é uma API back‑end desenvolvida em Java (com Spring Boot) cujo objetivo é consolidar e gerir dados de investimentos de usuários, associando contas, ações/ativos e informações externas de mercado para apoiar decisões de investimento.

A ideia central:

- Permitir o cadastro de usuários e suas contas de investimento.
- Permitir o cadastro de ativos (ações, etc) e associá‑los às contas dos usuários.
- Consultar APIs externas de mercado (por exemplo, para obter preços de ações) e integrar esses dados para análise ou exibição.
- Persistir dados em banco de dados relacional (por exemplo, MySQL) e facilitar o desenvolvimento com contêineres (por exemplo, via Docker / docker‑compose).

## 📂 Principais Tecnologias

- Java (versão utilizada no projeto: conforme `pom.xml`)
- Spring Boot (para construção da API REST)
- JPA / Hibernate (para persistência)
- MySQL (ou outro banco relacional configurado)
- Docker / Docker Compose (facilita levantar ambiente)
- Maven (gerenciamento de dependências / build)
- (Se aplicável) FeignClient ou outra solução para consumo de APIs externas
- (Se aplicável) Bibliotecas de testes (ex: JUnit, Mockito)

## 🔧 Funcionalidades

- CRUD de Usuários: criação, leitura, atualização e deleção de usuários do sistema.
- CRUD de Contas de Investimento vinculadas aos usuários.
- CRUD de Ativos/ações: cadastro de ativos que o usuário pode guardar ou acompanhar.
- Associação de ativos a contas de usuários: qual usuário/com conta possui qual ativo, quanto possui, etc.
- Integração com API externa de mercado para obter informações de preços, variações, etc.
- Configuração via Docker Compose (exemplo: banco de dados + aplicação) para facilitar o ambiente de desenvolvimento.

## 🚀 Como executar localmente

1. Clone este repositório:
   ```bash
   git clone https://github.com/Ghust27/Agregador‑de‑Investimentos.git
   ```
   (ou seu fork)
2. Acesse a pasta do projeto:
   ```bash
   cd Agregador‑de‑Investimentos
   ```
3. Verifique o arquivo `docker‑compose.yml` — ele possui configurações para levantar o banco de dados (MySQL) e possivelmente outros serviços.
   ```bash
   docker‑compose up ‑d
   ```
4. Ajuste o arquivo `application.properties` (ou `application.yml`) para apontar para o banco de dados:
   - host, porta, nome do banco
   - usuário / senha
   - demais configurações de JPA/Hibernate
5. Execute a aplicação via Maven:
   ```bash
   mvn spring‑boot:run
   ```
   Ou se preferir, gere o jar e execute:
   ```bash
   mvn clean package
   java ‑jar target/…‑jar
   ```
6. Acesse a API via navegador ou ferramenta de cliente HTTP (ex: Postman, Insomnia):  
   ‑ Endpoints base: `http://localhost:8080/api/...` (ou conforme configuração)  
   ‑ Exemplos de endpoints:
   > `GET /api/usuarios`  
   > `POST /api/contas`  
   > `POST /api/ativos`  
   > e assim por diante
