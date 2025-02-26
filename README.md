# Minimal API CRUD - Person

## Descrição
Este é um projeto de uma **Minimal API** desenvolvida em **C# com .NET**, implementando um CRUD (Create, Read, Update, Delete) para gerenciar pessoas (**Person**). A API utiliza **Entity Framework Core** para interagir com um banco de dados **SQL Server**.

## Tecnologias Utilizadas
- **.NET 9**
- **C#**
- **Entity Framework Core**
- **SQL Server**
- **Docker** (Opcional)
- **Swagger (Swashbuckle)**

## Configuração do Projeto
### 1. Clonar o Repositório
```bash
git clone https://github.com/seu-usuario/minimal-api-person.git
cd minimal-api-person
```

### 2. Configurar o Banco de Dados
Caso esteja usando **Docker**, suba um contêiner com SQL Server:
```bash
docker run -d --name sql_server_person -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=StrongPwd123' -p 1433:1433 mcr.microsoft.com/mssql/server:2019-latest
```
Caso esteja usando um SQL Server local, ajuste a string de conexão no `appsettings.json`.

### 3. Executar as Migrações do Banco
```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

### 4. Executar a API
```bash
dotnet run
```
A API estará rodando em `http://localhost:5000` ou `https://localhost:7000`.

## Endpoints
A API possui os seguintes endpoints:

| Método | Endpoint | Descrição |
|---------|---------|-------------|
| **GET** | `/persons` | Lista todas as pessoas |
| **GET** | `/persons/{id}` | Retorna uma pessoa por ID |
| **POST** | `/persons` | Cria uma nova pessoa |
| **PUT** | `/persons/{id}` | Atualiza uma pessoa |
| **DELETE** | `/persons/{id}` | Deleta uma pessoa |

## Testando no Swagger
Após iniciar a API, acesse o Swagger em:
```
http://localhost:5000/swagger
```
Isso permitirá testar os endpoints diretamente pela interface interativa.

