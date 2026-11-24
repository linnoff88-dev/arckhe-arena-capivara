# Goal â€” Arena da Capivara + TrÃ­ade Letal (05/10/2026)

Pedido do Nei: "faz os 3 e publica no portal" a partir da palestra do Simon Willison (pelicano de bicicleta).
Modelos: sÃ³ locais (Ollama) + Claude (claude -p) + Codex (codex exec), pela assinatura. Nenhuma API externa.

Entregas:
1. Kit `linnoff88-dev/arena-capivara`: gerar SVG "capivara andando de bicicleta" em ~19 modelos, renderizar, julgar em pares (2 ordens), ranking.
2. Guia PT/EN/ES em `guia/` com o mÃ©todo "monte seu benchmark" embutido + pÃ¡gina de resultados em `resultados/`.
3. Kit `linnoff88-dev/triade-letal`: checklist + script de inventÃ¡rio de MCP/tools + guia PT/EN/ES.
4. Os dois no portal (atualiza-portal).
Short: NÃƒO publicar; protÃ³tipo sÃ³ se sobrar, pendÃªncia dita ao Nei.

## CritÃ©rio de pronto (nÃ­vel 3)
- `ls ~/projetos/arena-capivara/resultados/svgs/*.svg | wc -l` â†’ â‰¥ 15
- `python3 arena/ranking.py --tabela` â†’ imprime tabela com â‰¥ 15 modelos e taxa de vitÃ³ria
- `jq length resultados/julgamentos.jsonl` equivalente: `wc -l resultados/julgamentos.jsonl` â†’ â‰¥ 2Ã— pares vÃ¡lidos Ã— 0,9
- concordÃ¢ncia juiz Claude Ã— Codex publicada na pÃ¡gina de resultados
- `curl -s -o /dev/null -w '%{http_code}' https://linnoff88-dev.github.io/ â†’ 200 (idem /guia/en/, /guia/es/, /resultados/)
- `curl -s ... https://linnoff88-dev.github.io/ â†’ 200 (idem en/es)
- `python3 ~/projetos/triade-letal/inventario.py --demo` â†’ sai 0 e imprime tabela
- portal: `git -C ~/projetos/portal log origin/main --oneline -5` contÃ©m commit de arena-capivara e triade-letal
