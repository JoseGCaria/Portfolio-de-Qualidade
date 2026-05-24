# Bug Report: Seasons-01 - Módulo de Temporadas

**Título:** Falha na validação de criação de temporadas duplicadas e períodos inconsistentes
**Data do Teste:** 24/05/2026

---

## 1. Descrição
O sistema não possui uma regra de validação para impedir a criação de temporadas com nomes duplicados ou intervalos de tempo que conflitem entre si. Como visto nas evidências, o sistema processa com sucesso (`201 Created`) a criação de temporadas com o mesmo nome ("Temporada de Verão 2026") e não bloqueia a persistência de datas que podem ser logicamente inválidas ou conflitantes, ferindo a integridade dos períodos ativos.

## 2. Severidade
- [ ] **Crítico:** Trava o sistema ou compromete a segurança.
- [x] **Maior:** Causa erro de lógica na regra de negócio (Dados duplicados e inconsistência de períodos).
- [ ] **Menor:** Erros visuais ou de interface.

## 3. Passos para Reproduzir
1. Acessar o endpoint `POST /api/seasons` no Insomnia.
2. Enviar uma requisição para criar uma temporada com nome e datas específicas.
3. Repetir a mesma requisição (ou com datas similares) sem alteração de nome ou conflito de datas.
4. Observar que a API retorna `201 Created` para ambas as requisições.

## 4. Resultado Esperado
O sistema deve:
- Impedir a criação de temporadas com nomes idênticos em um mesmo ciclo.
- Validar se a data de início é anterior à data de fim.
- Impedir sobreposição de datas entre temporadas diferentes.
Caso qualquer uma dessas regras seja violada, deve retornar `400 Bad Request` ou `409 Conflict`.

## 5. Resultado Atual
A API aceita a criação de múltiplas temporadas com as mesmas informações e não valida a lógica dos períodos, permitindo a duplicação indevida no banco de dados.

## 6. Ambiente de Teste
* **Dispositivo:** Computador local
* **Ferramenta de API:** Insomnia
* **Servidor:** Docker

## 7. Evidências
* **Evidência 1:** [Criação da primeira temporada](./Evidencias_Seasons/Primera_Seas.png)
* **Evidência 2:** [Criação de temporada duplicada/conflitante](./Evidencias_Seasons/Segunda_Seas_Repetida.png)