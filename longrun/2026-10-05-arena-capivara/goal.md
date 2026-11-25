ï»¿# Goal ê¢â¬â Arena da Capivara + TrêÂ­ade Letal (05/10/2026)

Pedido do Nei: "faz os 3 e publica no portal" a partir da palestra do Simon Willison (pelicano de bicicleta).
Modelos: sêÂ³ locais (Ollama) + Claude (claude -p) + Codex (codex exec), pela assinatura. Nenhuma API externa.

Entregas:
1. Kit `linnoff88-dev/arena-capivara`: gerar SVG "capivara andando de bicicleta" em ~19 modelos, renderizar, julgar em pares (2 ordens), ranking.
2. Guia PT/EN/ES em `guia/` com o mêÂ©todo "monte seu benchmark" embutido + pêÂ¡gina de resultados em `resultados/`.
3. Kit `linnoff88-dev/triade-letal`: checklist + script de inventêÂ¡rio de MCP/tools + guia PT/EN/ES.
4. Os dois no portal (atualiza-portal).
Short: NêÆO publicar; protêÂ³tipo sêÂ³ se sobrar, pendêÂªncia dita ao Nei.

## CritêÂ©rio de pronto (nêÂ­vel 3)
- `ls ~/projetos/arena-capivara/resultados/svgs/*.svg | wc -l` ê¢â â ê¢â°Â¥ 15
- `python3 arena/ranking.py --tabela` ê¢â â imprime tabela com ê¢â°Â¥ 15 modelos e taxa de vitêÂ³ria
- `jq length resultados/julgamentos.jsonl` equivalente: `wc -l resultados/julgamentos.jsonl` ê¢â â ê¢â°Â¥ 2êâ pares vêÂ¡lidos êâ 0,9
- concordêÂ¢ncia juiz Claude êâ Codex publicada na pêÂ¡gina de resultados
- `curl -s -o /dev/null -w '%{http_code}' https://linnoff88-dev.github.io/ ê¢â â 200 (idem /guia/en/, /guia/es/, /resultados/)
- `curl -s ... https://linnoff88-dev.github.io/ ê¢â â 200 (idem en/es)
- `python3 ~/projetos/triade-letal/inventario.py --demo` ê¢â â sai 0 e imprime tabela
- portal: `git -C ~/projetos/portal log origin/main --oneline -5` contêÂ©m commit de arena-capivara e triade-letal
