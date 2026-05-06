#  Portfólio de Qualidade: Projeto NaSalinha
  
Este repositório concentra a auditoria completa de qualidade e os artefatos de teste desenvolvidos para o projeto NaSalinha. Como analista de QA, meu objetivo aqui foi atuar como o guardião da experiência do usuário, garantindo a estabilidade do sistema e a integridade dos processos de reserva e gestão.
 
##  Descrição do Projeto

O NaSalinha é uma aplicação voltada para a gestão e reserva de espaços. O foco deste portfólio é a identificação de falhas (bugs), validação de requisitos e a garantia de que a jornada do usuário seja fluida e livre de erros críticos, tanto no frontend quanto nas comunicações de backend.

##  Ferramentas e Tecnologias

Para este desafio, foram selecionadas ferramentas que permitem cobrir diferentes camadas da aplicação:
Teste de API: Insomnia (validar endpoints e regras de negócio).

Ambiente e Infraestrutura: Docker (isolar o ambiente e garantir paridade com a produção).

Teste de E-mail: Mailtrap (validar fluxos de SMTP e notificações sem disparos reais).

Gestão de Mídias: Cloudinary (validar upload, armazenamento e performance de imagens).

Controle de Versão: Git (organizar documentação e versionar scripts de automação).


##  Estratégia de Testes

Utilizei uma abordagem de pirâmide de testes adaptada para garantir uma cobertura de qualidade em todas as frentes da aplicação NaSalinha:

Nível de Teste  |  Foco Principal  |  Ferramenta Chave  |  Impacto no Projeto

 Smoke Tests  |  Estabilidade básica da aplicação  |  Manual / Navegador  |  "Garante que o sistema está ""vivo"""
 
 API & Integração  |  Comunicação e Regras de Negócio  |  Insomnia  |  Evita quebras silenciosas no backend
 
 Funcionais (Caixa Preta)  |  Jornada e experiência do utilizador  |  Manual / Sistema  |  Garante que o fluxo de reserva funciona
 
 Regressão  |  Estabilidade após novas alterações  |  Manual / Git  |  Impede o retorno de bugs antigos
 
 Usabilidade & UI  |  Interface e Responsividade  |  DevTools / Navegador  |  Garante acessibilidade e fluidez visual


##  Documentação de Bugs

Todos os bugs encontrados foram documentados seguindo o padrão:

ID/Título: Resumo do problema.

Severidade: (Crítica, Alta, Média, Baixa).

Passos para Reproduzir: Caminho exato para chegar ao erro.

Resultado Esperado vs. Resultado Atual.

Evidências: Screenshots ou logs do terminal/console.
