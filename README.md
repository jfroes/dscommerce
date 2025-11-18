# 🛒 DSCommerce

[![Java](https://img.shields.io/badge/Java-17+-orange.svg)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen.svg)](https://spring.io/projects/spring-boot)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

> API REST de um sistema de comércio eletrônico desenvolvido durante o curso Java Spring Professional da DevSuperior

## 📋 Sobre o Projeto

O DSCommerce é uma aplicação backend que simula um sistema de e-commerce completo, permitindo o gerenciamento de produtos, pedidos, usuários e categorias. O projeto implementa as melhores práticas de desenvolvimento com Spring Boot, incluindo autenticação, autorização e validação de dados.

## ✨ Funcionalidades

### 👤 Usuários
- Cadastro e autenticação de usuários
- Perfis de acesso (Cliente e Admin)
- Visualização de perfil

### 🛍️ Produtos
- Listagem de produtos com paginação
- Busca de produtos por nome
- Detalhamento de produto
- **[Admin]** Cadastro, atualização e remoção de produtos

### 📦 Pedidos
- Criação de pedidos
- Listagem de pedidos do usuário
- Visualização de detalhes do pedido

### 🏷️ Categorias
- Organização de produtos por categorias
- Navegação entre categorias

## 🚀 Tecnologias

### Backend
- **Java 17** - Linguagem de programação
- **Spring Boot 3.x** - Framework principal
- **Spring Data JPA** - Abstração de persistência
- **Spring Security** - Autenticação e autorização
- **Bean Validation** - Validação de dados

### Banco de Dados
- **H2 Database** - Ambiente de desenvolvimento/testes
- **PostgreSQL** - Ambiente de produção (configurável)

### Ferramentas
- **Maven** - Gerenciamento de dependências
- **Postman** - Testes de API (collection disponível)

## 🏗️ Arquitetura

O projeto segue uma arquitetura em camadas:

```
├── Controllers     # Camada de apresentação (REST)
├── Services        # Camada de lógica de negócio
├── Repositories    # Camada de acesso a dados
├── Entities        # Modelos de domínio
├── DTOs            # Objetos de transferência de dados
└── Config          # Configurações da aplicação
```

### Principais Padrões Utilizados
- **DTO (Data Transfer Object)** - Transferência de dados entre camadas
- **Repository Pattern** - Abstração de acesso a dados
- **Dependency Injection** - Inversão de controle
- **REST** - Arquitetura de API

## 🔐 Segurança

- Autenticação via Spring Security
- Senhas criptografadas com BCrypt
- Controle de acesso baseado em roles (ROLE_CLIENT, ROLE_ADMIN)
- Proteção de endpoints sensíveis

## 📦 Instalação e Execução

### Pré-requisitos
- Java 17 ou superior
- Maven 3.6+
- IDE de sua preferência (IntelliJ IDEA, Eclipse, VS Code)

### Passo a Passo

1. **Clone o repositório**
```bash
git clone https://github.com/jfroes/dscommerce.git
cd dscommerce
```

2. **Instale as dependências**
```bash
mvn clean install
```

3. **Execute a aplicação**
```bash
mvn spring-boot:run
```

4. **Acesse a aplicação**
- API: `http://localhost:8080`
- Console H2: `http://localhost:8080/h2-console`
  - JDBC URL: `jdbc:h2:mem:testdb`
  - User: `sa`
  - Password: *(deixe em branco)*

## 📍 Principais Endpoints

### Autenticação
```http
POST /login
Content-Type: application/json

{
  "username": "maria@gmail.com",
  "password": "123456"
}
```

### Produtos
```http
GET    /products              # Listar produtos (paginado)
GET    /products/{id}         # Buscar produto por ID
GET    /products?name=phone   # Buscar produtos por nome
POST   /products              # Criar produto [Admin]
PUT    /products/{id}         # Atualizar produto [Admin]
DELETE /products/{id}         # Deletar produto [Admin]
```

### Pedidos
```http
GET    /orders                # Listar pedidos do usuário
GET    /orders/{id}           # Buscar pedido por ID
POST   /orders                # Criar novo pedido
```

### Usuários
```http
GET    /users/me              # Obter dados do usuário logado
```

## 📊 Modelo de Dados

### Principais Entidades

- **User** - Usuários do sistema
- **Product** - Produtos disponíveis
- **Category** - Categorias de produtos
- **Order** - Pedidos realizados
- **OrderItem** - Itens de um pedido
- **Payment** - Pagamentos

### Relacionamentos
- User 1:N Order
- Order 1:N OrderItem
- Product N:M Category
- Order 1:1 Payment

## 🎯 Melhorias Futuras

- [ ] Implementar testes de integração
- [ ] Adicionar documentação Swagger/OpenAPI
- [ ] Implementar cache com Redis
- [ ] Adicionar logs estruturados
- [ ] Configurar Docker Compose para ambiente de desenvolvimento
- [ ] Implementar CI/CD com GitHub Actions

## 👨‍💻 Autor

**José Paulo Froes**

- GitHub: [@jfroes](https://github.com/jfroes)
- Email: josepaulo.froes@gmail.com
- LinkedIn: [José Paulo Froes](https://linkedin.com/in/seu-perfil)

## 📝 Licença

Este projeto foi desenvolvido como parte do curso **Java Spring Professional** da [DevSuperior](https://devsuperior.com.br/).

---

⭐ Se este projeto foi útil para você, considere dar uma estrela!

**Desenvolvido com ☕ e Spring Boot**
