# Casos de teste e resultados observados

**Legenda:** PASS = verificação estática do código/schema; BLOCKED = teste dinâmico não executado. A atividade exige resultado real: não transforme casos bloqueados em aprovados sem executar e guardar evidência no seu computador.

| ID | Caso | Resultado | Evidência/observação |
|---|---|---|---|
| T01 | Inspeção do schema: tabela usuarios existe | PASS | Confirmado em db/oficina_db.sql |
| T02 | Inspeção do schema: tabela clientes existe | PASS | Confirmado em db/oficina_db.sql |
| T03 | Inspeção do schema: tabela veiculos existe | PASS | Confirmado em db/oficina_db.sql |
| T04 | Inspeção do schema: tabela agendamentos existe | PASS | Confirmado em db/oficina_db.sql |
| T05 | Verificar UNIQUE em usuarios.login | PASS | Definido no schema |
| T06 | Verificar UNIQUE em veiculos.placa | PASS | Definido no schema |
| T07 | Verificar FK veículos → clientes | PASS | Definida no schema e PRAGMA ligado na conexão |
| T08 | Verificar FK agendamentos → veículos | PASS | Definida no schema e PRAGMA ligado na conexão |
| T09 | Verificar bcrypt na autenticação | PASS | bcrypt.compareSync(senha, usuario.senha) no server.js |
| T10 | Verificar proteção de rota sem sessão | PASS | exigirLogin retorna HTTP 401 pelo código |
| T11 | Verificar validação de CPF com 11 dígitos | PASS | validarCliente verifica comprimento após remover não dígitos |
| T12 | Verificar normalização/regex de placa | PASS | Código remove espaços/hífens, converte maiúsculas e aplica regex |
| T13 | Verificar validação de data real | PASS | dataValida valida formato e round-trip ISO |
| T14 | Requisição HTTP sem sessão a GET /api/me | BLOCKED | Servidor não iniciou: dependência express ausente (MODULE_NOT_FOUND) após npm install indisponível/incompleto |
| T15 | Login válido admin/admin123 por HTTP | BLOCKED | Servidor não iniciou; não afirmar sucesso sem teste real |
| T16 | Login inválido retorna 401 por HTTP | BLOCKED | Servidor não iniciou; requer ambiente com dependências instaladas |
| T17 | Cadastro de cliente válido retorna 201 | BLOCKED | Servidor não iniciou; requer teste HTTP |
| T18 | CPF duplicado retorna 400 | BLOCKED | Servidor não iniciou; requer teste HTTP |
| T19 | Cadastro de veículo com placa duplicada retorna 400 | BLOCKED | Servidor não iniciou; requer teste HTTP |
| T20 | Cadastro de agendamento com data inválida retorna 400 | BLOCKED | Servidor não iniciou; requer teste HTTP |
