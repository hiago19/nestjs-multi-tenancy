# nestjs-multi-tenancy

## Sobre o Projeto

O **nestjs-multi-tenancy** é um projeto desenvolvido para demonstrar como implementar um sistema multi-tenancy usando o framework NestJS. Multi-tenancy é uma arquitetura onde uma única instância de software serve múltiplos clientes (tenants), permitindo o isolamento de dados e configurações para cada tenant.

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

- **src/**: Contém o código-fonte do projeto.
  - **auth/**: Lida com a autenticação e autorização de usuários.
    - **partner-users/**: Controlador para gerenciar usuários parceiros.
    - **roles/**: Implementa a lógica de autorização baseada em roles.
    - **users/**: Controladores, serviços e DTOs para gerenciar usuários.
  - **database/**: Configurações e provedores de banco de dados.
    - **database.module.ts**: Módulo de configuração do banco de dados.
    - **database.providers.ts**: Provedores de conexão com o banco de dados.
  - **events/**: Lida com a criação e gerenciamento de eventos.
    - **dto/**: Contém DTOs para eventos.
    - **events.controller.ts**: Controlador para gerenciar operações relacionadas aos eventos.
    - **events.service.ts**: Serviço para lógica de negócios relacionada aos eventos.
  - **partners/**: Lida com a criação e gerenciamento de parceiros.
    - **dto/**: Contém DTOs para parceiros.
    - **partners.controller.ts**: Controlador para gerenciar operações relacionadas aos parceiros.
    - **partners.service.ts**: Serviço para lógica de negócios relacionada aos parceiros.
  - **prisma/**: Contém o módulo e serviço do Prisma.
  - **tenant/**: Implementa a lógica de multi-tenancy.
    - **tenant.interceptor.ts**: Interceptador para identificar e configurar o tenant.
    - **tenant.service.ts**: Serviço para gerenciar o contexto do tenant.
  - **app.controller.ts**: Controlador principal do aplicativo.
  - **app.module.ts**: Módulo principal do aplicativo.
  - **app.service.ts**: Serviço principal do aplicativo.
  - **main.ts**: Arquivo de entrada principal para iniciar o aplicativo NestJS.
- **config/**: Contém arquivos de configuração para diferentes ambientes.
- **test/**: Contém testes para o aplicativo.
- **docker-compose.yaml**: Arquivo de configuração do Docker para subir o ambiente do MySQL.
- **api.http**: Arquivo para testar as APIs do projeto.
- **package.json**: Arquivo de configuração do npm que lista as dependências e scripts do projeto.
- **.prettierrc**: Arquivo de configuração do Prettier.
- **Prisma/**: Contém a configuração e migrações do Prisma.
  - **schema.prisma**: Define o esquema do banco de dados.
  - **migrations/**: Contém as migrações do banco de dados.

## Tecnologias Utilizadas

- **NestJS**: Framework para construção de aplicações Node.js escaláveis e eficientes.
- **TypeScript**: Linguagem de programação que estende o JavaScript adicionando tipos.
- **Prisma**: ORM para Node.js e TypeScript.
- **MySQL**: Sistema de gerenciamento de banco de dados relacional.
- **Docker**: Plataforma para desenvolvimento, envio e execução de aplicações em contêineres.

## Rodando Localmente

Para executar o projeto localmente, siga as instruções abaixo:

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/hiago19/nestjs-multi-tenancy.git
   ```

2. Navegue até o diretório do projeto:

   ```bash
   cd nestjs-multi-tenancy
   ```

3. Instale as dependências:

   ```bash
   npm install
   ```

4. Suba o banco de dados MySQL com Docker:

   ```bash
   docker compose up
   ```

5. Configure o Prisma:

   ```bash
   npx prisma generate //gera o cliente Prisma
   ```

6. Execute as migrações do banco de dados:

   ```bash
   npx prisma migrate dev
   ```

7. Inicie a aplicação:

   ```bash
   npm run start:dev
   ```

8. Teste as APIs utilizando o arquivo `api.http`:
   - Você pode utilizar uma extensão como "REST Client" no VSCode para enviar requisições HTTP diretamente do arquivo `api.http`.

## Funcionalidades

- Gerenciamento de Tenants: Adicionar, editar e remover tenants.
- Isolamento de Dados: Cada tenant possui seu próprio conjunto de dados, isolado dos demais.
- Configurações Multi-Tenant: Configurações específicas para cada tenant.
- Integração com MySQL: Uso do banco de dados MySQL para armazenamento de dados.
- Uso do Docker: Facilita a configuração e o gerenciamento do ambiente de desenvolvimento.

## Demonstração

Aqui estão algumas capturas de tela do projeto em execução:

1. **Cadastro de Usuarios**:
   ![Cadastro de Usuarios](https://github.com/hiago19/nestjs-multi-tenancy/assets/81202387/a221cb2a-e48c-451b-8ab5-489db49affe3)



2. **Cadastro de Partner**:
   ![Cadastro de Partner](https://github.com/hiago19/nestjs-multi-tenancy/assets/81202387/2ed0ad0d-be62-4cf0-87e6-b193d5f09f9a)



3. **Login**:
   ![Login](https://github.com/hiago19/nestjs-multi-tenancy/assets/81202387/1a9fbb07-e07f-452c-9201-0480800a68ab)



4. **Cadastro de Eventos**:
   ![Cadastro de Eventos](https://github.com/hiago19/nestjs-multi-tenancy/assets/81202387/ac097513-af8d-4da6-9bef-6a29dfe97c13)


