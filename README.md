# 🍽️ Reserva de Restaurante API

![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/express.js-%23404d59?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b?style=for-the-badge&logo=mongodb&logoColor=white)

API de gerenciamento de reservas de restaurantes com autenticação JWT, integração com Overpass API (geolocalização) e suporte a múltiplos bancos de dados.

## 🚀 Tecnologias

- **Linguagem:** TypeScript
- **Runtime:** Node.js
- **Framework:** Express
- **Bancos de Dados:** MongoDB (via Mongoose) e SQLite (via sqlite3)
- **Segurança:** bcryptjs (hash de senha) e JSON Web Token (autenticação)
- **Integração:** Axios para chamadas à Overpass API

## 🛣️ Endpoints da API

Todas as rotas (exceto registro e login) exigem o Header: `Authorization: Bearer <seu_token>`.

### 🔐 Autenticação (`/user`)
| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `POST` | `/user/register` | Cria uma nova conta de usuário |
| `POST` | `/user/login` | Autentica usuário e retorna o Token JWT |

### 🏠 Restaurantes (`/restaurants`)
| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `GET` | `/restaurants` | Lista todos os restaurantes cadastrados |
| `GET` | `/restaurants/:id` | Detalhes de um restaurante específico |
| `POST` | `/restaurants` | Cadastra um novo restaurante |
| `PUT` | `/restaurants/:id` | Atualiza dados de um restaurante |
| `DELETE` | `/restaurants/:id` | Remove um restaurante |

### 📅 Reservas (`/reservations`)
| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `GET` | `/reservations` | Lista todas as reservas |
| `GET` | `/reservations/:reservationId` | Detalhes de uma reserva específica |
| `POST` | `/reservations` | Cria uma nova reserva |
| `PUT` | `/reservations/:reservationId` | Altera dados de uma reserva |
| `DELETE` | `/reservations/:reservationId` | Cancela/Exclui uma reserva |

### 🌍 Integração Externa (`/overpass`)
| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `GET` | `/overpass/restaurants` | Busca restaurantes via Overpass API por localização |

### Passo a Passo

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/jotor-dev/reserva-restaurante.git](https://github.com/jotor-dev/reserva-restaurante.git)
    ```

2.  **Acesse a pasta do projeto:**
    ```bash
    cd reserva-restaurante
    ```

3.  **Instale as dependências:**
    ```bash
    npm install
    # ou
    yarn install
    ```

4.  **Configure as variáveis de ambiente:**
    Crie um arquivo `.env` na raiz do projeto e adicione as configurações de banco de dados e chaves secretas.
      MONGO_URI=mongodb://usuario:senha@localhost:27017/meu_banco_de_dados?authSource=admin
      SECRET_KEY=minha_chave_secreta
      PORT=3000

6.  **Execute a aplicação:**
    ```bash
    npm start
    ```

## 🤝 Contribuindo
1.  Faça um **Fork** do projeto.
2.  Crie uma **Branch** para sua feature (`git checkout -b feature/NovaFeature`).
3.  Dê um **Commit** nas suas alterações (`git commit -m 'Add: Nova Feature'`).
4.  Dê um **Push** na Branch (`git push origin feature/NovaFeature`).
5.  Abra um **Pull Request**.
