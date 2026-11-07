# Changelog

## 0.2.4 — 2026-11-07
- A busca e a avaliação não abrem mais o link do anúncio no portal: leem só o índice do Ocaum, atualizado todo dia (antes conferiam o link e tiravam da lista o que tinha saído do ar). Um anúncio pode ter saído do ar desde a última coleta: confira no link original.
- A busca fica mais rápida: a conferência de links era cerca de dois terços do tempo dela.
- `ocaum_index_status`: o alvo de atualização da base é 30 h.

## 0.2.3 — 2026-11-07
- Texto alinhado com o que o Ocaum faz: a busca é no índice do Ocaum (anúncios de ZAP, VivaReal, OLX e QuintoAndar, atualizado todo dia), não ao vivo nos portais.
- Limite de uso: 20 chamadas por minuto e 200 por hora, por pessoa (era 40 e 400).
- Categoria do plugin no ChatGPT: Other.
- As versões do pacote do plugin entre a 0.1.0 e a 0.2.3 não foram registradas aqui.

## 0.1.0 — 2026-11-01
- Primeira versão pública: busca de imóveis à venda (ZAP, VivaReal, OLX, QuintoAndar).
- Login por código de e-mail (WorkOS).
- Ferramentas: `ocaum_search_properties`, `ocaum_evaluate_listing`, `ocaum_list_neighborhoods`, `ocaum_index_status`.
- Limite de 40 chamadas por minuto e 400 por hora.
