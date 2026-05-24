# MyPokemon - Pokedex App

O **MyPokemon** é uma aplicação Full-Stack desenvolvida para funcionar como uma Pokedex pessoal e interativa. O objetivo principal do sistema é oferecer uma plataforma segura e responsiva onde os entusiastas de Pokémon possam registrar e gerenciar suas jornadas como treinadores. 

A aplicação vai além de uma simples listagem, implementando um sistema completo de gestão de usuários e segurança de dados.

**Principais Funcionalidades:**

* **👤 Autenticação e Gestão de Usuários:** Sistema completo de cadastro e login de "Treinadores". Cada usuário possui um ambiente isolado e seguro, garantindo que sua coleção seja privada e acessada apenas mediante autenticação.
* **🎒 Pokedex Pessoal (CRUD):** Uma interface intuitiva onde os usuários podem gerenciar suas coleções. É possível adicionar novos Pokémons capturados, visualizar detalhes, atualizar informações ou remover registros da sua lista.
* **🔐 Recuperação de Conta Segura:** Para garantir que os usuários não percam o acesso às suas coleções, o sistema conta com um fluxo de "Esqueci minha senha". A aplicação gera e envia de forma automatizada um e-mail com instruções e tokens de redefinição de senha.
* **⚡ Arquitetura Moderna e Escalável:** Construído com uma separação clara entre Frontend (React.js) e Backend (Node.js/Express), o projeto é totalmente conteinerizado com Docker, garantindo que rode de maneira uniforme em qualquer ambiente.

## 🛠 Ferramentas Utilizadas

* **Frontend:** React.js com Vite, React Router DOM, CSS modularizado.
* **Backend:** Node.js com Express e CORS.
* **Infraestrutura:** Docker e Docker Compose.
* **Serviço de E-mail:** Nodemailer integrado ao Mailtrap.
* **Gerenciamento de Estado:** Context API (`AuthContext`).

## 🚀 Setup e Execução

### Pré-requisitos
* Docker e Docker Compose instalados.
* Node.js instalado (para desenvolvimento local).

### Executando com Docker (Recomendado)
Para subir a aplicação completa (Frontend + Backend), utilize o Docker Compose na raiz do projeto:

```bash
docker-compose up --build
```

* **Frontend:** Disponível em `http://localhost:3000` (ou a porta mapeada).
* **Backend:** Disponível em `http://localhost:3001`.

## 📧 Utilizando o Mailtrap

O projeto utiliza o Mailtrap para simular o envio de e-mails de recuperação de senha, evitando o envio de e-mails reais durante o desenvolvimento.

1. Crie uma conta gratuita em [Mailtrap.io](https://mailtrap.io).
2. No seu "Inbox" do Mailtrap, acesse a aba **SMTP Settings**.
3. No arquivo `backend/email.js`, substitua as credenciais (`user` e `pass`) pelos dados fornecidos pelo seu Sandbox do Mailtrap.
4. Quando o sistema disparar um e-mail de recuperação, ele aparecerá na interface do Mailtrap.

## 🏗 Escolhas Técnicas

### 1. Docker Multi-stage Build
Para o Frontend, optamos por um multi-stage build:
* **Estágio 1 (Build):** Utiliza Node.js para instalar dependências e compilar o código (Vite).
* **Estágio 2 (Entrega):** Utiliza o servidor Nginx (Alpine) para servir apenas os arquivos estáticos compilados (`dist`), resultando em uma imagem extremamente leve e performática.

### 2. Backend Containerizado
O Backend roda em uma imagem Node Alpine. O uso do `docker-compose` garante que a rede interna do Docker (`bridge`) permita que o Frontend e o Backend se comuniquem com segurança, isolando o ambiente de execução.

### 3. Modularização de CSS
Para manter a escalabilidade, o CSS foi separado do JSX. Cada componente possui seu próprio arquivo `Styles.css`, garantindo que o estilo seja específico e fácil de manter, seguindo a convenção de nomenclatura com hífens (*kebab-case*).

## 🐳 Estrutura do Docker

* **Frontend (`nginx:stable-alpine`):** Servidor de alta performance para arquivos estáticos.
* **Backend (`node:20-alpine`):** Ambiente isolado para a API Express.
* **Docker Compose:** Orquestrador que gerencia a inicialização, rede e volumes dos serviços.

## 📝 Comandos Úteis

| Ação | Comando |
| :--- | :--- |
| Subir tudo | `docker-compose up --build` |
| Parar tudo | `docker-compose down` |
| Logs do Backend | `docker logs mypokemon-backend-1` |
| Limpar imagens órfãs | `docker system prune` |
