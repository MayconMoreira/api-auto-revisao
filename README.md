# API AUTO REVISÃO

## Descrição

A API AUTO REVISÃO é uma solução para gerenciar a manutenção básica de veículos. A API permite controlar trocas de óleo, abastecimentos e fornecer alertas para vencimento da CNH e próximas manutenções. Ideal para proprietários de veículos e empresas de gestão de frotas.

## Funcionalidades

- **Troca de Óleo:** Registre e acompanhe trocas de óleo com datas e quilometragem.
- **Abastecimentos:** Registre abastecimentos com detalhes como data, quantidade e preço.
- **Alertas de Vencimento da CNH:** Receba notificações sobre a proximidade do vencimento da CNH.
- **Próximas Manutenções:** Notificações sobre manutenções futuras com base na quilometragem e/ou data.

## Tecnologias Utilizadas

- **Linguagem:** Python 3.10
- **Framework Web:** FastAPI
- **Banco de Dados:** MongoDB, MySQL
- **Cache:** Redis
- **Autenticação:** JWT (JSON Web Tokens)
- **Documentação:** Swagger

## Pré-requisitos

- Python 3.10
- MongoDB
- MySQL
- Redis

## Instalação

1. Clone o repositório:

   ```bash
   git clone https://github.com/MayconMoreira/api-auto-revisao.git
   cd api-auto-revisao

2. Crie e ative um ambiente virtual:

   ```bash
   python -m venv venv
   source venv/bin/activate  # No Windows, use `venv\Scripts\activate`

3. Instale as dependências:
   
   ```bash
   pip install -r requirements.txt

4. Configure as variáveis de ambiente:

   ```bash
   PORT=8000
   MONGODB_URI=mongodb://localhost:27017/auto-revisao
   MYSQL_URI=mysql://usuario:senha@localhost:3306/auto-revisao
   REDIS_URL=redis://localhost:6379/0

5. Inicie o servidor:

   ```bash
   uvicorn app.main:app --reload

6. Acesse a documentação da API no navegador:

   ```bash
   http://localhost:8000/docs

## Endpoints Principais

Autenticação
- POST /auth/register: Registrar um novo usuário
- POST /auth/login: Login de usuário e obtenção de token

Troca de Óleo
- POST /oil-change: Registrar uma troca de óleo
- GET /oil-change: Listar todas as trocas de óleo
- GET /oil-change/{id}: Obter detalhes de uma troca de óleo específica
- PUT /oil-change/{id}: Atualizar uma troca de óleo
- DELETE /oil-change/{id}: Remover uma troca de óleo

Abastecimentos
- POST /fuel: Registrar um abastecimento
- GET /fuel: Listar todos os abastecimentos
- GET /fuel/{id}: Obter detalhes de um abastecimento específico
- PUT /fuel/{id}: Atualizar um abastecimento
- DELETE /fuel/{id}: Remover um abastecimento

Alertas
- GET /alerts/license-expiry: Obter alertas de vencimento da CNH
- GET /alerts/maintenance: Obter alertas de próximas manutenções
