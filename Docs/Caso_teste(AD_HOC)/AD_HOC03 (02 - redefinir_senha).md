# Bug Report: AD_HOC-03 - Módulo de Autenticação e Acesso (JWT)

**Título:** Falha na persistência da nova senha no fluxo de recuperação (Bypass de atualização)
**Data do Teste:** 21/05/2026

---

## 1. Descrição
O módulo de recuperação de senha apresenta uma falha crítica de persistência. Após o usuário solicitar a redefinição e submeter a nova senha via endpoint `POST /api/auth/reset-password` (que retorna `200 OK` conforme evidência), a aplicação não atualiza o registro do usuário no banco de dados. Como resultado, a tentativa de login com a nova senha falha, resultando em "Credenciais inválidas" na interface, indicando que a senha antiga (ou nenhuma senha) foi aplicada.

## 2. Severidade
- [ ] **Crítico:** Trava o sistema ou compromete a segurança.
- [x] **Maior:** Causa erro de lógica na regra de negócio (Bloqueio total de acesso via recuperação).
- [ ] **Minório:** Erros visuais ou de interface.

## 3. Passos para Reproduzir
1. Acessar o endpoint `POST /api/auth/forgot-password` e enviar o e-mail do usuário cadastrado.
2. Obter o token de recuperação (ou usar um token válido gerado).
3. Acessar o endpoint `POST /api/auth/reset-password` passando o `token`, a `newPassword` e a `passwordConfirmation`.
4. Observar que a API retorna `200 OK` com a mensagem "Senha redefinida com sucesso".
5. Tentar realizar o login na interface (frontend) utilizando a nova senha definida.

## 4. Resultado Esperado
O sistema deve atualizar a senha do usuário no banco de dados após a validação do token e permitir o login bem-sucedido na interface utilizando a nova credencial definida.

## 5. Resultado Atual
A API simula o sucesso da operação (`200 OK`), mas a senha não é efetivamente alterada no banco de dados, impedindo o usuário de logar e mantendo o estado de "Credenciais inválidas".

## 6. Ambiente de Teste
* **Dispositivo:** Computador local
* **Ferramenta de API:** Insomnia
* **Frontend:** `http://localhost:3000/login`
* **Servidor:** Docker

## 7. Evidências
* **Fluxo de Solicitação:** [Sucesso no envio da recuperação](./Evidencia_Extras/Envio_redefinir.png)
* **Fluxo de Redefinição:** [Sucesso reportado pela API no Reset](./Evidencia_Extras/Redefinir_senha.png)
* **Falha no Login:** [Erro de credenciais na interface após redefinição](./Evidencia_Extras/Novo_Login.png)