# MicroProfile POC com Quarkus

Este projeto é uma prova de conceito (POC) demonstrando o uso das principais especificações do Eclipse MicroProfile utilizando o Quarkus.

## Funcionalidades Demonstradas

- **Configuração**: Uso do MicroProfile Config para mensagens customizadas (`/hello`).
- **Health Check**: Health check customizado com MicroProfile Health (`/q/health/live`).
- **JWT Auth**: Proteção de endpoint usando MicroProfile JWT (`/secure`).
- **Métricas**: Exposição de métricas customizadas com MicroProfile Metrics (`/metrics-demo` e `/q/metrics`).
- **Tolerância a Falhas**: Retry, Timeout e Fallback com MicroProfile Fault Tolerance (`/unstable`).

## Como rodar

1. **Pré-requisitos**: Java 17+ e Maven 3.8+
2. **Clone o repositório**:
   ```sh
   git clone https://github.com/seu-usuario/microprofile-poc.git
   cd microprofile-poc
   ```
3. **Inicie a aplicação em modo dev**:
   ```sh
   mvnw.cmd quarkus:dev
   ```

## Endpoints Disponíveis

| Endpoint         | Descrição                                                      |
| ---------------- | -------------------------------------------------------------- |
| `/hello`         | Mensagem customizada via MicroProfile Config                   |
| `/q/health/live` | Health check customizado                                       |
| `/secure`        | Endpoint protegido por JWT                                     |
| `/metrics-demo`  | Métricas customizadas                                          |
| `/q/metrics`     | Métricas padrão e customizadas                                 |
| `/unstable`      | Demonstração de tolerância a falhas (Retry, Timeout, Fallback) |

## Testando os Endpoints

- **Configuração**:  
  Acesse `http://localhost:8080/hello`.  
  Para customizar a mensagem, altere a propriedade no arquivo `application.properties`:

  ```
  greeting.message=Olá, MicroProfile!
  ```

- **Health Check**:  
  Acesse `http://localhost:8080/q/health/live`.

- **JWT Auth**:  
  Gere um token JWT válido e faça uma requisição para `http://localhost:8080/secure` com o header:

  ```
  Authorization: Bearer <seu-token-jwt>
  ```

- **Métricas**:  
  Acesse `http://localhost:8080/metrics-demo` para métricas customizadas ou `http://localhost:8080/q/metrics` para todas as métricas.

- **Tolerância a Falhas**:  
  Acesse `http://localhost:8080/unstable` para ver o comportamento de retry, timeout e fallback.

## Rodando os Testes

Execute os testes automatizados com:

```sh
mvnw.cmd test
```

## Referências

- [Quarkus](https://quarkus.io/)
- [Eclipse MicroProfile](https://microprofile.io/)
- [Documentação do Quarkus MicroProfile](https://quarkus.io/guides/microprofile-intro)
