# Engenharia reversa — Oficina AutoCerta

## Objetivo
Documentar o sistema web recebido sem documentação: clientes, veículos e agendamentos de uma oficina mecânica.

## Executar
Requer Node.js **22.13 ou superior**. Dentro de `sistema_comentado/`:
```bash
npm install
npm start
```
Acesse http://localhost:3000. Credenciais de teste estão no `LEIA-ME.txt` original. O banco SQLite é inicializado a partir de `db/oficina_db.sql` quando `db/oficina_db.sqlite` ainda não existe.

## Documentação
- `docs/documentacao.pdf`: relatório consolidado.
- `docs/der.png`: diagrama entidade-relacionamento.
- `docs/evidencias/`: resultados e limitações da execução realizada neste ambiente.

## Estado de validação
Foi possível inspecionar o código e o banco SQLite incluído. A tentativa de executar o servidor neste ambiente falhou porque `express` não ficou disponível após a tentativa de `npm install` (erro `MODULE_NOT_FOUND`). Por isso, testes que dependem de HTTP são registrados como **BLOQUEADOS**, não como aprovados. Repita-os após `npm install` em um ambiente com acesso ao registro npm e registre capturas reais.

## GitHub / commits
O ZIP preparado não contém histórico Git. Crie o repositório com o nome `nome-sobrenome-engenharia-reversa` e faça commits próprios em pelo menos 3 dias diferentes. Não fabrique datas nem conte commits gerados artificialmente como trabalho realizado em dias distintos.
