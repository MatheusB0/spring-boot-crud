# 🌱 Spring Boot CRUD — RestApi

API REST em **Java + Spring Boot** que vai virar um CRUD completo (Create, Read, Update, Delete). Projeto em fase inicial, feito para aprender e praticar boas práticas de back-end, versionamento e organização de repositório.

![Java](https://img.shields.io/badge/Java-21-orange?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.1-6DB33F?logo=springboot&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-wrapper-C71A36?logo=apachemaven&logoColor=white)
![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)

---

## 📌 Status atual

O projeto está na **base inicial**: a estrutura Spring Boot já está montada e configurada, mas as funcionalidades do CRUD ainda estão sendo construídas.

| Item | Situação |
|------|----------|
| Estrutura do projeto (Maven + Spring Boot) | ✅ Pronta |
| Dependências de JPA e Lombok | ✅ Configuradas |
| Entidades / Models | ⏳ A fazer |
| Repositories | ⏳ A fazer |
| Controllers e endpoints REST | ⏳ A fazer |
| Banco de dados | ⏳ A definir |
| Testes | 🟡 Só o teste de contexto |

> ⚠️ **Importante:** como ainda não há driver de banco nem `spring-boot-starter-web` no `pom.xml`, a aplicação ainda não sobe como API. Veja o [Roadmap](#-roadmap) para os próximos passos.

---

## 🛠️ Tecnologias

- **Java 21**
- **Spring Boot 4.1.1**
- **Spring Data JPA** — persistência de dados
- **Lombok** — menos código repetitivo (getters, setters, construtores)
- **Maven** (com Maven Wrapper, não precisa instalar o Maven)

---

## 📂 Estrutura do projeto

```
spring-boot-crud/
├── docs/
│   └── padroes.md                  # Convenções, versionamento, branching e backup
├── src/
│   ├── main/
│   │   ├── java/com/Atv/RestApi/
│   │   │   └── RestApiApplication.java   # Classe principal
│   │   └── resources/
│   │       └── application.properties    # Configurações da aplicação
│   └── test/
│       └── java/com/Atv/RestApi/
│           └── RestApiApplicationTests.java
├── mvnw / mvnw.cmd                 # Maven Wrapper (Linux/Mac e Windows)
└── pom.xml
```

---

## 🚀 Como rodar

### Pré-requisitos

- [JDK 21](https://adoptium.net/) instalado
- Git

### Passo a passo

```bash
# 1. Clone o repositório
git clone https://github.com/MatheusB0/spring-boot-crud.git

# 2. Entre na pasta
cd spring-boot-crud

# 3. Compile o projeto
./mvnw clean package        # Linux / Mac
mvnw.cmd clean package      # Windows

# 4. Execute os testes
./mvnw test
```

Quando o banco de dados e o módulo web forem adicionados, a API poderá ser iniciada com:

```bash
./mvnw spring-boot:run
```

---

## 🗺️ Roadmap

- [ ] Adicionar `spring-boot-starter-web` para expor a API REST
- [ ] Escolher e configurar o banco de dados (H2 para desenvolvimento, PostgreSQL ou MySQL para produção)
- [ ] Criar a primeira entidade com JPA
- [ ] Criar o `Repository` com Spring Data JPA
- [ ] Criar o `Controller` com os endpoints do CRUD
- [ ] Validação de dados (Bean Validation)
- [ ] Tratamento global de erros
- [ ] Testes unitários e de integração
- [ ] Documentação da API com Swagger / OpenAPI

### Endpoints previstos

Quando o CRUD estiver pronto, o padrão será:

| Método | Rota | Descrição |
|--------|------|-----------|
| `POST` | `/recurso` | Cria um novo registro |
| `GET` | `/recurso` | Lista todos os registros |
| `GET` | `/recurso/{id}` | Busca um registro por ID |
| `PUT` | `/recurso/{id}` | Atualiza um registro |
| `DELETE` | `/recurso/{id}` | Remove um registro |

---

## 🤝 Como contribuir

Nosso fluxo de trabalho está documentado em [`docs/padroes.md`](docs/padroes.md). Resumindo:

1. Crie uma branch a partir da principal usando o formato `<tipo>/<descricao-curta>`:
   - `feature/` — nova funcionalidade
   - `fix/` — correção de bug
   - `hotfix/` — correção urgente
   - `refactor/` — reorganização sem mudar comportamento
   - `docs/` — documentação
   - `chore/` — manutenção e dependências
2. Faça suas alterações e commits.
3. Abra um **Pull Request** descrevendo o que mudou e como foi validado.
4. Aguarde a aprovação de pelo menos uma pessoa da equipe.
5. Depois do merge, apague a branch de trabalho.

Exemplos: `feature/autenticacao-usuarios`, `fix/validacao-cadastro`, `docs/instrucoes-instalacao`.

### 🏷️ Versionamento

Usamos [Versionamento Semântico](https://semver.org/lang/pt-BR/) (`MAJOR.MINOR.PATCH`). Enquanto estivermos na versão `0.x.x`, mudanças incompatíveis ainda podem acontecer.

---

## 🔐 Segurança

Nunca suba senhas, tokens ou outras credenciais para o repositório. Se alguma for exposta, revogue ou troque na hora — apagar o arquivo do histórico não invalida a credencial.

---

## 👥 Autores

Feito com ☕ por [MatheusB0](https://github.com/MatheusB0) , [David-fsl](https://github.com/David-fsl) e [victor2104-alt](https://github.com/victor2104-alt).

---


