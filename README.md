💼 Cadastro de Usuários - API REST

Uma API RESTful completa para gerenciamento de usuários, desenvolvida em Spring Boot como projeto de portfólio. Demonstra habilidades em desenvolvimento back-end com arquitetura em camadas e princípios REST.

📋 Funcionalidades
✅ CRUD Completo - Create, Read, Update e Delete de usuários

✅ Busca por Email - Recuperação específica de usuários

✅ Arquitetura em Camadas - Separation of concerns bem definida

✅ Banco H2 em Memória - Prático para desenvolvimento e testes

🏗️ Estrutura do Projeto
text
cadastro-usuario/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/lcs/cadastro_usuario/
│   │   │       ├── business/           # Lógica de negócio (Service)
│   │   │       ├── controller/         # Endpoints REST (API)
│   │   │       ├── infrastructure/     # Persistência (Entity/Repository)
│   │   │       └── CadastroUsuarioApplication.java  # Classe principal
│   │   └── resources/
│   │       └── application.properties  # Configurações
│   └── test/                          # Testes automatizados
├── pom.xml                           # Dependências Maven
└── mvnw                              # Maven Wrapper
🛠️ Tecnologias Utilizadas
Java 17

Spring Boot 3.x

Spring Data JPA

H2 Database (banco em memória)

Lombok (redução de boilerplate code)

Maven (gerenciamento de dependências)

📡 Endpoints da API
Criar Usuário
http
POST /usuario
Content-Type: application/json

{
  "nome": "João Silva",
  "email": "joao@email.com",
  "senha": "senha123"
}
Buscar Usuário por Email
http
GET /usuario?email=joao@email.com
Atualizar Usuário por ID
http
PUT /usuario?id=1
Content-Type: application/json

{
  "nome": "João Silva Atualizado",
  "email": "joao.novo@email.com"
}
Deletar Usuário por Email
http
DELETE /usuario?email=joao@email.com
🚀 Como Executar
Pré-requisitos
JDK 17+

Maven (opcional, projeto inclui Maven Wrapper)

Execução Local
bash
# Clone o projeto
git clone https://github.com/seu-usuario/cadastro-usuario.git

# Acesse o diretório
cd cadastro-usuario

# Execute com Maven Wrapper
./mvnw spring-boot:run

# Ou com Maven instalado
mvn spring-boot:run
A aplicação estará disponível em: http://localhost:8080

🧪 Testando a API
Criar usuário
bash
curl -X POST http://localhost:8080/usuario \
  -H "Content-Type: application/json" \
  -d '{"nome":"Maria Silva","email":"maria@email.com","senha":"123456"}'
Buscar usuário
bash
curl -X GET "http://localhost:8080/usuario?email=maria@email.com"
Acessar Console H2
text
http://localhost:8080/h2-console
JDBC URL: jdbc:h2:mem:testdb
Usuário: sa
Senha: password
⚙️ Configuração
application.properties
properties
# Servidor
server.port=8080

# Banco H2 (memória)
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password

# H2 Console
spring.h2.console.enabled=true

# JPA
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
🔮 Próximas Melhorias
Implementar autenticação JWT

Adicionar documentação com Swagger/OpenAPI

Criar testes unitários e de integração

Adicionar validações de dados (@Valid)

Implementar tratamento de exceções global

Adicionar paginação em consultas

Configurar Docker container

📊 Exemplo de Resposta
Sucesso (200 OK)
json
{
  "id": 1,
  "nome": "João Silva",
  "email": "joao@email.com"
}
👨‍💻 Autor
Seu Nome

LinkedIn: Seu LinkedIn

GitHub: @seu-usuario

Email: seu.email@exemplo.com

📄 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

Nota: Este projeto foi desenvolvido para fins de portfólio, demonstrando habilidades em desenvolvimento back-end com Spring Boot e boas práticas de arquitetura de software.
