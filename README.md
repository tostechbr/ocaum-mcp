<p align="center"><img src="docs/logo.svg" width="128" height="128" alt="Ocaum"></p>

<h1 align="center">Ocaum</h1>

<p align="center"><b>Seu próximo imóvel, numa conversa.</b><br>A busca de imóveis dos portais, dentro da sua IA.</p>

<p align="center">
  <img alt="MCP" src="https://img.shields.io/badge/MCP-servidor_remoto-1d1d1f">
  <img alt="Versão" src="https://img.shields.io/badge/vers%C3%A3o-0.1.0-3f7d20">
  <img alt="Cobertura" src="https://img.shields.io/badge/venda-S%C3%A3o_Paulo-1d1d1f">
  <img alt="Base" src="https://img.shields.io/badge/base-atualizada_todo_dia-3f7d20">
</p>

<p align="center">
  <img src="docs/demo.gif" width="720" alt="Uma pergunta no chat vira 3 anúncios reais de Moema, com preço e selo 🟢🟡🔴">
  <br>
  <sub>Busca real feita no Ocaum, com a base de 08/10: 566 imóveis, 4 portais, selo de preço em cada um.</sub>
</p>

O Ocaum fala [MCP](https://modelcontextprotocol.io), o padrão aberto que Claude, ChatGPT, Cursor, VS Code e Codex adotam. Você conecta uma URL, faz login e pergunta.

## Por que o Ocaum

Os portais te dão filtros. Você tem perguntas: "2 quartos perto do metrô, com vaga, que aceite pet, e não esteja caro". O Ocaum deixa a sua IA responder isso direto, em linguagem natural, com dados dos 4 maiores portais de São Paulo.

## Sem × com o Ocaum

| ❌ Sem | ✅ Com |
|---|---|
| Abrir ZAP, VivaReal, OLX e QuintoAndar um por um | Uma pergunta busca nos 4 de uma vez |
| Anúncio que já saiu do ar, descoberto só ao clicar | O Ocaum abre cada link antes de responder e descarta o que sumiu |
| "Esse preço está bom?" sem referência | 🟢 abaixo · 🟡 dentro · 🔴 acima do mercado, comparado a imóveis parecidos do bairro |
| Mesmo imóvel repetido em vários portais | Resultado único, com o link de cada anúncio |

## Conectar (2 minutos)

Uma URL só, em qualquer cliente MCP com suporte a servidor remoto e login OAuth.

URL do servidor: `https://mcp.ocaum.com/mcp`

**Claude (claude.ai ou Desktop)**
1. Configurações → Conectores → **Adicionar conector personalizado**.
2. Cole a URL acima e clique em **Conectar**.
3. Faça o login: digite seu e-mail e o código de 6 dígitos que chega nele.

**ChatGPT** (modo desenvolvedor)
1. Crie um conector novo com a mesma URL e autenticação **OAuth**.
2. Faça o login com e-mail e código.

**Claude Code**
```sh
claude mcp add --transport http ocaum https://mcp.ocaum.com/mcp
```
Depois rode `/mcp` e escolha **Authenticate**.

**Qualquer outro cliente MCP** (Cursor, VS Code, Windsurf, Gemini CLI, Codex…)

Adicione um servidor MCP remoto (HTTP) com a URL acima e faça o login quando o cliente pedir. O nome do menu muda de cliente pra cliente, mas o passo é sempre esse.

Conectou em outro? Conte numa [issue](../../issues) e a gente coloca aqui o passo a passo.

## Teste rápido

Cole no chat:

> 2 quartos à venda em Pinheiros até 1 milhão, com elevador

O assistente chama `ocaum_search_properties` e responde com os anúncios e o link de cada um. Se funcionou, está pronto.

## Perguntas que funcionam

- "Apartamento de 2 quartos com vaga na Vila Mariana até 900 mil, que aceite pet."
- "Esse anúncio está caro? https://…" (cole o link do ZAP, VivaReal, OLX ou QuintoAndar)
- "Quais bairros têm 'Pinheros'?" (acerta a grafia)
- "Quando foi a última atualização da base?"

## Ferramentas

| Ferramenta | O que faz |
|---|---|
| `ocaum_search_properties` | Busca venda nos 4 portais (ZAP, VivaReal, OLX e QuintoAndar): preço, quartos, vagas, área, condomínio, pet, mobiliado, comodidades e preferências em texto ("perto do metrô"). Ordena por relevância, preço ou R$/m². |
| `ocaum_evaluate_listing` | Recebe o link de um anúncio e diz se está caro (🟢🟡🔴), com os 5 parecidos do bairro. |
| `ocaum_list_neighborhoods` | Acerta a grafia de bairro. |
| `ocaum_index_status` | Quantos anúncios ativos há por portal e há quantas horas foram atualizados. |

## Cobertura e limites

- **Venda em São Paulo**, nos portais ZAP/VivaReal, OLX e QuintoAndar.
- **Base atualizada todo dia, à meia-noite.** O `ocaum_index_status` mostra a idade de cada portal.
- **Dado que o portal não informa não aparece.** Ausente não quer dizer "não tem".
- **O selo 🟢🟡🔴 é uma aproximação**, não um laudo de avaliação.
- **Limite de uso:** 40 chamadas por minuto e 400 por hora, por pessoa. Busca de páginas fundas conta mais.
- **Servidor ocupado:** a resposta diz em quantos segundos tentar de novo.

## Problemas comuns

- **Não chegou o código:** olhe o spam e as promoções, depois peça outro. O e-mail sai de `access@workos-mail.com`.
- **Erro 401 depois do login:** remova o conector e adicione de novo.
- **O assistente não usa a ferramenta:** peça "use o Ocaum para buscar…".

## Privacidade

O login é feito pela WorkOS. Guardamos suas buscas e o seu identificador de usuário para melhorar o produto e aplicar o limite de uso.

## Quem faz

Feito por **Tiago Oliveira** ([@tostechbr](https://github.com/tostechbr) · [LinkedIn](https://www.linkedin.com/in/tiagolivesan/)), engenheiro de AI/ML.

Quer testar, dar feedback ou conversar sobre o projeto? Abra uma [issue](../../issues).

## Mais

[Changelog](CHANGELOG.md) · [Como contribuir](CONTRIBUTING.md) · [Segurança e privacidade](SECURITY.md)
