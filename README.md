# DSCommerce - Sistema de Comércio Eletrônico

DSCommerce é um sistema de comércio eletrônico desenvolvido para fins educativos, projetado para explorar conceitos fundamentais de desenvolvimento web, arquitetura de software e manipulação de dados em sistemas comerciais.

## ✍️ Objetivo

O sistema foi projetado para ser utilizado em cursos da [DevSuperior](https://devsuperior.com.br), com foco no aprendizado de alunos em:

- Modelagem de domínio com relações entre entidades (muitos-para-um, muitos-para-muitos).
- Desenvolvimento de funcionalidades essenciais, como cadastros e fluxos de casos de uso.
- Construção de sistemas completos e robustos para ambientes web.

## 🔧 Funcionalidades Principais

- **Manutenção de Produtos:** CRUD completo de produtos, com possibilidade de filtro por nome (somente para administradores).
- **Gerenciamento de Categorias:** CRUD completo de categorias, com filtro por nome (somente para administradores).
- **Cadastro de Usuários:** CRUD de usuários, incluindo alteração de perfis de acesso (somente para administradores).
- **Catálogo de Produtos:** Listagem paginada de produtos, com opção de filtro por nome (público).
- **Carrinho de Compras:** Inclusão, remoção e alteração de itens no carrinho (público).
- **Pedidos:** Registro de pedidos com status dinâmico e histórico de compras (usuários logados).
- **Login/Autenticação:** Sistema de autenticação baseado em credenciais, com suporte a diferentes perfis de usuário.

## 📊 Modelo Conceitual

O modelo conceitual do sistema define as seguintes entidades e suas relações principais:

- **Usuário:** Inclui atributos como nome, email, telefone, data de nascimento, senha e perfis de acesso (client, admin).
- **Produto:** Inclui nome, descrição, preço e imagem.
- **Categoria:** Agrupamento de produtos.
- **Carrinho de Compras:** Contém itens associados aos produtos e suas respectivas quantidades.
- **Pedido:** Inclui instante do pedido, status e lista de itens associados.
- **Item de Pedido:** Associa um produto a um pedido, armazenando a quantidade e o preço vigente no momento da compra.

## 🔍 Casos de Uso

### 1. Consultar Catálogo

- **Atores:** Usuário anônimo, Cliente, Admin
- **Descrição:** Permite a listagem paginada de produtos, com filtro opcional por nome.
- **Cenário de Sucesso:** O sistema retorna uma listagem com nome, imagem e preço dos produtos ordenados por nome.

### 2. Gerenciar Carrinho

- **Atores:** Usuário anônimo
- **Descrição:** Permite adicionar, remover ou alterar a quantidade de itens no carrinho de compras.
- **Cenário de Sucesso:** O sistema atualiza os dados do carrinho e informa o subtotal.

### 3. Registrar Pedido

- **Atores:** Cliente
- **Descrição:** Salva no sistema os dados do pedido baseado no carrinho de compras informado.
- **Cenário de Sucesso:** O sistema retorna o ID do pedido e o status "Aguardando Pagamento".

### 4. Manter Produtos

- **Atores:** Admin
- **Descrição:** Permite criar, atualizar e deletar produtos no sistema.
- **Validações:**
  - Nome: 3 a 80 caracteres.
  - Preço: Deve ser positivo.
  - Descrição: Mínimo de 10 caracteres.
  - Pelo menos 1 categoria associada.

### 5. Login/Autenticação

- **Atores:** Usuário anônimo
- **Descrição:** Permite autenticação no sistema com token de acesso.
- **Cenário de Sucesso:** O sistema retorna um token JWT válido.

## 🔧 Tecnologias Utilizadas

- **Java 17**
- **Spring Boot**
- **Spring Data JPA**
- **Hibernate**
- **H2 Database** (testes)
- **PostgreSQL** (produção)
- **JWT** para autenticação
- **Maven** como gerenciador de dependências

## 🔢 Requisitos de Instalação

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/PedroHFG/javaspring-professional-dscommerce.git
   ```

2. **Acesse o diretório do projeto:**

   ```bash
   cd javaspring-professional-dscommerce
   ```

3. **Execute o sistema:**

   ```bash
   ./mvnw spring-boot:run
   ```

4. **Acesse o sistema:**
   - Frontend: `http://localhost:8080`
   - H2 Console: `http://localhost:8080/h2-console`

## 🔍 Acesso ao Banco de Dados

### Configuração Padrão do H2 (testes)

- **URL JDBC:** `jdbc:h2:mem:testdb`
- **Usuário:** `sa`
- **Senha:** _(vazia)_

### Configuração do PostgreSQL (produção)

- **URL JDBC:** `jdbc:postgresql://localhost:5432/dscommerce`
- **Usuário:** `postgres`
- **Senha:** `postgres`

## 📖 Licença

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo [LICENSE](./LICENSE) para mais informações.

## 🔗 Contato

Criado por **Seu Nome** - Entre em contato:

- **Email:** pedrohfidg@gmail.com
- **GitHub:** [PedroHFG](https://github.com/PedroHFG)
