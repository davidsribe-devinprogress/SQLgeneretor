# SQLgen

Gerador visual de esquemas MySQL e scripts DDL, executado inteiramente no navegador.

## Estrutura

```text
SQLgen/
├── index.html          # Página principal da aplicação
├── README.md           # Documentação e instruções
└── src/
    ├── css/
    │   └── styles.css  # Estilos próprios
    └── js/
        └── app.js      # Estado, interface e geração de SQL
```

## Como executar

Abra `index.html` em um navegador moderno. Não é necessário instalar dependências nem iniciar um servidor. A conexão com a internet é necessária para carregar o Tailwind CSS via CDN.

Os projetos são salvos no `localStorage` do navegador. Use os botões de importação e exportação para transferir ou fazer backup de esquemas em JSON.

## Produtividade

- Desfazer/refazer: botões no cabeçalho ou atalhos `Ctrl+Z`, `Ctrl+Y` e `Ctrl+Shift+Z`.
- Modelos: Blog, Loja virtual e CRM, com tabelas e relações iniciais.
- Duplicação: copie tabelas ou colunas para reaproveitar definições.
- Diagrama: visão das tabelas e chaves estrangeiras.
- Migrações: importe um `.sql` com declarações `CREATE TABLE`; o SQLgen compara a referência com o projeto atual e gera um arquivo de alterações.
- Proteção: copiar e baixar DDL ficam desativados enquanto houver problemas de validação.

A importação SQL cobre `CREATE TABLE`, colunas, chaves primárias, índices `UNIQUE` de uma coluna e FKs para chaves primárias. Revise migrações antes de executar, especialmente operações de remoção ou alterações de tipo. O histórico é mantido em memória durante a sessão atual.
