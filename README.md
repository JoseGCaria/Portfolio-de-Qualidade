# Relatório Final de Qualidade - Projeto NaSalinha

## 1. Descrição do Projeto
Este projeto tem como objetivo a validação de um sistema de gestão de check-ins e autenticação (JWT). O foco da documentação é garantir a conformidade com as regras de negócio e a segurança do fluxo de usuários.

## 2. Ferramentas Utilizadas
* **Gerenciamento de API:** Insomnia (testes funcionais e de endpoint).
* **Ambiente:** Docker (containers para backend e banco de dados).
* **Documentação:** Markdown (.md).
* **Controle de Qualidade:** Metodologia de testes manuais baseada em requisitos (RF/RNF).

## 3. Relatório de Testes Final

### 3.1. Métricas de Execução por Área
Esta tabela resume a execução dos casos de teste dividida por módulos do projeto.

| Módulo (Pasta) | Casos Planejados | Pass (Sucesso) | Fail (Falha) | Status Geral |
| :--- | :---: | :---: | :---: | :--- |
| **Módulo(JWT)** | 15 | 13 | 2 |leve|
| **Check-in** | 9 | 2 | 5 | Grave |
| **Módulo_de_Pontuação_Ranking** | 9 | 6 | 3 |leve|
| **Seasons** | 17 | 16 | 1 | leve |
| **Caso_teste(AD_HOC)** | 3 | 0 | 3 | Bugs extras |
| **TOTAL** | **53** | **39** | **14** | **73,58% Aprovado** |

> *Nota: Os casos de teste com status "Fail" estão detalhados como Issues no repositório.*

## 4. Resumo dos Testes Realizados
* **Módulo de Autenticação:** Validação de fluxo de registro, login e controle de acesso JWT.
* **Módulo de Check-in:** Testes de upload, restrição de duplicidade, fluxo de moderação e permissões de edição.
* **Infraestrutura:** Validação da gestão de ciclo de vida de arquivos (limpeza em diretórios).

## 5. Estratégia de Regressão
Para garantir que futuras correções não impactem o sistema, adotamos um plano de **Smoke Test**:
* **Fluxo Prioritário:** Cadastro e Autenticação.
* **Ação:** Sempre que uma correção for aplicada, o fluxo de login e criação de check-in deve ser executado para confirmar a integridade.

---
*Documentação de QA: 24/05/2026*
