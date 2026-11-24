# Arena da Capivara

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


[![Arena da Capivara](guia/assets/banner.jpg)](https://linnoff88-dev.github.io/

**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

Qual IA desenha a melhor capivara de bicicleta? Pedimos o mesmo SVG a 19 modelos: 10 rodando no prÃ³prio computador (Ollama) e 9 pela assinatura do Claude e do ChatGPT (CLIs `claude` e `codex`). Nenhuma API paga. Um juiz cego comparou os desenhos dois a dois, nas duas ordens.

Inspirado no benchmark do pelicano de bicicleta de Simon Willison.

## ðŸ“– Guia e resultado

- Guia (o que Ã©, como rodar, como montar o seu benchmark): **https://linnoff88-dev.github.io/
- Resultado da rodada 1 (ranking, galeria, cÃ³digo de cada SVG): **https://linnoff88-dev.github.io/

## Rodada 1 (05/10/2026)

| # | Modelo | Onde roda | VitÃ³rias |
|---|---|---|---|
| 1 | Claude Fable 5.1 | assinatura Claude | 97% |
| 2 | GPT-6.1 Sol | assinatura ChatGPT/Codex | 94% |
| 3 | GPT-6 Astra | assinatura ChatGPT/Codex | 91% |
| 4 | Claude Opus 5.5 | assinatura Claude | 82% |
| 5 | **Qwen 3.8 27B** | **no seu PC** | 74% |
| 6 | GPT-5.5 | assinatura ChatGPT/Codex | 71% |
| 7 | Claude Sonnet 5.5 | assinatura Claude | 65% |

Tabela completa (18 modelos com SVG vÃ¡lido; o Command R 35B nÃ£o entregou) na [pÃ¡gina de resultados](https://linnoff88-dev.github.io/ Juiz: Claude Sonnet 5.5, 306 confrontos. Segundo juiz (GPT-6 Luna) concordou em 92% dos 64 que refez. Lado esquerdo venceu 49,7% (sem viÃ©s de posiÃ§Ã£o). Uma tentativa por modelo: Ã© uma foto, nÃ£o uma sentenÃ§a.

## Rodar no seu PC

```bash
pip install cairosvg pillow
git clone https://github.com/linnoff88-dev/arena-capivara && cd arena-capivara
# edite arena/modelos.json com os modelos que vocÃª tem
python3 arena/gerar.py           # pede o desenho a cada modelo
python3 arena/renderizar.py      # SVG -> PNG + confrontos A|B
python3 arena/julgar.py          # juiz cego (Claude Sonnet 5.5 pela assinatura)
python3 arena/julgar.py --juiz codex --modelo gpt-6-luna --amostra 60   # 2Âº juiz
python3 arena/ranking.py --tabela
python3 arena/galeria.py         # resultados/index.html (+ en/ es/)
```

Os confrontos (`resultados/pares/`) nÃ£o vÃ£o para o repositÃ³rio; o `renderizar.py` recria.

Projeto irmÃ£o, da mesma palestra: [TrÃ­ade Letal](https://linnoff88-dev.github.io/ quando um agente de IA pode vazar seus dados.

LicenÃ§a MIT Â· [ARCKHÉ AI](https://ARCKHÉ AI)

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>