# Arena del Capibara

[![Arena del Capibara](guia/assets/banner-es.jpg)](https://linnoff88-dev.github.io/

**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

Â¿QuÃ© IA dibuja el mejor capibara en bicicleta? Le pedimos el mismo SVG a 19 modelos: 10 corriendo en la propia computadora (Ollama) y 9 por la suscripciÃ³n de Claude y ChatGPT (las CLIs `claude` y `codex`). Ninguna API paga. Un juez ciego comparÃ³ los dibujos de dos en dos, en los dos Ã³rdenes.

Inspirado en el benchmark del pelÃ­cano en bicicleta de Simon Willison.

## ðŸ“– GuÃ­a y resultados

- GuÃ­a (quÃ© es, cÃ³mo correrlo, cÃ³mo armar tu propio benchmark): **https://linnoff88-dev.github.io/
- Resultados de la ronda 1 (ranking, galerÃ­a, cÃ³digo de cada SVG): **https://linnoff88-dev.github.io/

## Ronda 1 (05/10/2026)

| # | Modelo | DÃ³nde corre | Victorias |
|---|---|---|---|
| 1 | Claude Fable 5.1 | suscripciÃ³n Claude | 97% |
| 2 | GPT-6.1 Sol | suscripciÃ³n ChatGPT/Codex | 94% |
| 3 | GPT-6 Astra | suscripciÃ³n ChatGPT/Codex | 91% |
| 4 | Claude Opus 5.5 | suscripciÃ³n Claude | 82% |
| 5 | **Qwen 3.8 27B** | **en tu PC** | 74% |
| 6 | GPT-5.5 | suscripciÃ³n ChatGPT/Codex | 71% |
| 7 | Claude Sonnet 5.5 | suscripciÃ³n Claude | 65% |

Tabla completa (18 modelos con SVG vÃ¡lido; Command R 35B no entregÃ³) en la [pÃ¡gina de resultados](https://linnoff88-dev.github.io/ Juez: Claude Sonnet 5.5, 306 enfrentamientos. Un segundo juez (GPT-6 Luna) coincidiÃ³ en el 92% de los 64 que rehÃ­zo. El lado izquierdo ganÃ³ el 49,7% (sin sesgo de posiciÃ³n). Un intento por modelo: es una foto, no una sentencia. El pedido y la pregunta del juez estÃ¡n en portuguÃ©s.

## Correrlo en tu PC

```bash
pip install cairosvg pillow
git clone https://github.com/linnoff88-dev/arena-capivara && cd arena-capivara
# edita arena/modelos.json con los modelos que tienes
python3 arena/gerar.py           # pide el dibujo a cada modelo
python3 arena/renderizar.py      # SVG -> PNG + enfrentamientos A|B
python3 arena/julgar.py          # juez ciego (Claude Sonnet 5.5 por la suscripciÃ³n)
python3 arena/julgar.py --juiz codex --modelo gpt-6-luna --amostra 60   # segundo juez
python3 arena/ranking.py --tabela
python3 arena/galeria.py         # resultados/index.html (+ en/ es/)
```

Las imÃ¡genes de los enfrentamientos (`resultados/pares/`) no estÃ¡n en el repositorio; `renderizar.py` las recrea.

Proyecto hermano, de la misma charla: [TrÃ­ada Letal](https://linnoff88-dev.github.io/ cuando un agente de IA puede filtrar tus datos.

Licencia MIT Â· [ARCKHÉ AI](https://ARCKHÉ AI)
