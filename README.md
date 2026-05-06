# 🛡️ Portfólio de Qualidade: Projeto NaSalinha
  
Este repositório concentra a auditoria completa de qualidade e os artefatos de teste desenvolvidos para o projeto NaSalinha. Como analista de QA, meu objetivo aqui foi atuar como o guardião da experiência do usuário, garantindo a estabilidade do sistema e a integridade dos processos de reserva e gestão.

## 📝 Descrição do Projeto

O NaSalinha é uma aplicação voltada para a gestão e reserva de espaços. O foco deste portfólio é a identificação de falhas (bugs), validação de requisitos e a garantia de que a jornada do usuário seja fluida e livre de erros críticos, tanto no frontend quanto nas comunicações de backend.

## 🛠️ Ferramentas e Tecnologias

Para este desafio, foram selecionadas ferramentas que permitem cobrir diferentes camadas da aplicação:
Teste de API: Insomnia (validar endpoints e regras de negócio).

Ambiente e Infraestrutura: Docker (isolar o ambiente e garantir paridade com a produção).

Teste de E-mail: Mailtrap (validar fluxos de SMTP e notificações sem disparos reais).

Gestão de Mídias: Cloudinary (validar upload, armazenamento e performance de imagens).

Controle de Versão: Git (organizar documentação e versionar scripts de automação).


## 🔍 Estratégia de Testes

A auditoria foi dividida nos seguintes tipos de testes para garantir uma cobertura 360º:

1. Testes de Fumaça (Smoke Tests)
Validação rápida das funcionalidades críticas para garantir que o sistema está estável o suficiente para testes mais profundos (ex: o sistema abre? O login básico funciona?).

2. Testes de API / Integração
Verificação da comunicação entre os serviços.

Validação de Payloads (JSON).

Testes de autenticação e tokens JWT.

Consistência dos dados retornados pelo banco de dados.


3. Testes Funcionais (Caixa Preta)

Baseados nos requisitos do sistema, focando no comportamento visível ao usuário:

Fluxo de reserva de salas.

Cadastro e edição de perfil.

Filtros de busca.

4. Testes de Regressão
Executados após a correção de bugs encontrados para garantir que as novas alterações não quebraram funcionalidades que já estavam operando corretamente.

5. Testes de Usabilidade e UI
Análise da interface para identificar inconsistências visuais, problemas de responsividade e elementos que dificultam a experiência do usuário (UX).


## 🐞 Documentação de Bugs

Todos os bugs encontrados foram documentados seguindo o padrão:

ID/Título: Resumo do problema.

Severidade: (Crítica, Alta, Média, Baixa).

Passos para Reproduzir: Caminho exato para chegar ao erro.

Resultado Esperado vs. Resultado Atual.

Evidências: Screenshots ou logs do terminal/console.
