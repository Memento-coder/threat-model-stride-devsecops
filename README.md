# Threat Modeling com STRIDE – DevSecOps

## 1. Objetivo

Este documento apresenta a modelagem de ameaças de uma aplicação web utilizando a metodologia STRIDE, com foco na identificação sistemática de riscos de segurança ao longo da arquitetura do sistema.

---

## 2. Arquitetura do Sistema

O sistema modelado segue a seguinte estrutura:

Usuário → Aplicação Web → API → Banco de Dados

### Componentes:
- Usuário: cliente que interage via navegador
- Aplicação Web: camada de interface
- API: camada de lógica de negócio
- Banco de Dados: armazenamento persistente

---

## 3. Metodologia STRIDE

A metodologia STRIDE classifica ameaças em seis categorias:

- Spoofing
- Tampering
- Repudiation
- Information Disclosure
- Denial of Service
- Elevation of Privilege

---

## 4. Análise de Ameaças por Componente

### 4.1 Usuário → Aplicação Web

| Categoria       | Ameaça                     | Descrição                         | Mitigação               |
|-----------------|----------------------------|-----------------------------------|-------------------------|
| Spoofing        | Roubo de credenciais       | Ataque de phishing ou brute force | MFA, autenticação forte |
| Tampering       | Manipulação de requisições | Alteração de parâmetros HTTP      | Validação de entrada    |
| Repudiation     | Negação de ações           | Usuário nega operações realizadas | Logs auditáveis         |
| Info Disclosure | Vazamento de sessão        | Sequestro de sessão               | HTTPS, cookies seguros  |
| DoS             | Flood de requisições       | Sobrecarga da aplicação           | Rate limiting           |
| EoP             | Escalada de privilégio     | Acesso indevido a funções         | Controle de acesso      |

---

### 4.2 Aplicação Web → API

| Categoria       | Ameaça                     | Descrição               | Mitigação           |
|-----------------|----------------------------|-------------------------|---------------------|
| Spoofing        | Falsificação de requisição | Token inválido          | JWT seguro          |
| Tampering       | Alteração de payload       | Manipulação de dados    | Assinatura de dados |
| Repudiation     | Falta de rastreabilidade   | Ações não registradas   | Logging             |
| Info Disclosure | Exposição de dados         | API sem proteção        | Criptografia        |
| DoS             | Ataque à API               | Alto volume de chamadas | Throttling          |
| EoP             | Acesso indevido            | Falha de autorização    | RBAC                |

---

### 4.3 API → Banco de Dados

| Categoria       | Ameaça                | Descrição                | Mitigação            |
|-----------------|-----------------------|--------------------------|----------------------|
| Spoofing        | Credenciais expostas  | Conexão não segura       | Secrets management   |
| Tampering       | SQL Injection         | Inserção maliciosa       | Prepared statements  |
| Repudiation     | Falta de logs         | Ações não auditadas      | Auditoria DB         |
| Info Disclosure | Vazamento de dados    | Dados sensíveis expostos | Criptografia         |
| DoS             | Queries pesadas       | Sobrecarga do banco      | Limitação de queries |
| EoP             | Acesso admin indevido | Privilégios elevados     | Least privilege      |

---

## 5. Considerações

A aplicação da metodologia STRIDE permite identificar vulnerabilidades em diferentes camadas do sistema, promovendo uma abordagem proativa de segurança alinhada com os princípios do DevSecOps.

A integração da modelagem de ameaças no ciclo de desenvolvimento contribui para a redução de riscos e aumento da maturidade de segurança da aplicação.

---

## 6. Repositório

https://github.com/Memento-coder/threat-model-stride-devsecops

---

## 7. Arquitetura
!04.png
