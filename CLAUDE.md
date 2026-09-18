# CLAUDE.md — memória do projeto Meu Radar

Este arquivo é a memória deste projeto. O Claude lê este arquivo sozinho toda vez que abre esta pasta, antes de fazer qualquer coisa. Tudo o que está aqui vale para todas as conversas, sem eu precisar repetir.

## 1. O que é este projeto

- É um radar: um time de agentes que pesquisa a internet todo dia sobre um assunto meu e me entrega um briefing. Feito na Formação Claude, do Chat ao Code.
- Quem usa sou eu. Sou instrutor de formações em ferramentas de IA, e acompanhar o mercado faz parte da minha rotina.
- **O assunto:** novidades práticas de inteligência artificial para quem constrói produtos e software — novos modelos, ferramentas de código com IA, APIs, agentes e automação, ferramentas no-code/low-code, geração de imagem/vídeo/áudio, e mudanças de preço, plano e limite de uso.
- **Por que importa:** preciso saber antes dos alunos o que mudou, o que vale mostrar em sala e o que saiu do ar.
- **O que entra:** o que foi lançado ou anunciado oficialmente.
- **O que não entra:** rumores, vazamentos, papers acadêmicos (a não ser que já tenham virado ferramenta usável) e mercado de IA como negócio (investimentos, valuation, regulação), a não ser que mude o que eu posso usar amanhã.
- A definição completa do radar, em formato CLARO, está em `RADAR.md`. Em caso de dúvida, `RADAR.md` manda.

## 2. Regras técnicas que não se discutem

Estas regras são fixas. Não se propõe alternativa, não se troca por algo "melhor", não se pergunta "e se".

### Onde ficam os arquivos

- `CLAUDE.md` e `RADAR.md` ficam na raiz desta pasta.
- Os briefings ficam na subpasta `briefings/`, um arquivo por dia, com o nome `AAAA-MM-DD.md` (exemplo: `briefings/2026-09-18.md`).
- Os agentes do time ficam em `.claude/agents/`. São três: `pesquisador`, `editor` e `revisor`.
- Nada desta pasta é publicado na internet.

### Fontes

- Fontes primárias: blogs e páginas de lançamento de OpenAI, Anthropic, Google DeepMind/Gemini, Meta AI, Mistral e xAI; changelogs de Claude Code, Cursor, GitHub Copilot e Windsurf; contas oficiais no X e no YouTube dessas empresas e de quem trabalha nelas, só quando é anúncio oficial.
- Veículos: The Verge, TechCrunch, Ars Technica, Hacker News (só como termômetro, sempre com link para a fonte original).
- Post de terceiros em rede social só entra se tiver link para a fonte original.
- Fonte nova só entra nesta lista se eu aprovar.

### Idioma

- O briefing é sempre em português do Brasil, mesmo quando a fonte é em inglês.
- Nomes de produtos e termos técnicos consagrados ficam no original (ex.: "Claude Code", "MCP", "prompt caching").

### O time e a ordem do trabalho

1. **Pesquisador**: varre as fontes procurando o que foi publicado desde o último briefing. Para cada item, guarda título, link, data e resumo do fato. Não escolhe, não opina.
2. **Editor**: lê os briefings anteriores em `briefings/` para não repetir, escolhe as cinco mais relevantes, traduz e escreve no tom combinado.
3. **Revisor**: confere cada afirmação contra o link, aplica os Observáveis de `RADAR.md` e devolve ao Editor o que não passar. Só grava o que passou.
- Critério de relevância, nesta ordem: (a) muda o que eu posso usar ou ensinar; (b) é de ferramenta que já uso em aula; (c) é de fonte primária; (d) é recente.

### Formato do briefing

- Linha 1 — **Manchete do dia:** uma frase, "Saiu X, que muda Y."
- Linha 2 — **Nas suas ferramentas:** uma frase, "Atualização em A e B; nada novo em C."
- Depois, até cinco notícias. Cada uma com: título em português; resumo de três a cinco linhas que não pula ponto importante; "Por que importa" em uma frase; fonte com nome + link + data.
- Tom explicativo. Não explica termos básicos de IA.
- Se houver menos de cinco coisas relevantes, traz menos e diz "dia fraco". Nunca completa com enchimento.
- Cabe em uma página.

## 3. O que este radar nunca faz

- Nunca repete notícia de briefing anterior. Desdobramento entra como "atualização de X", só com o que é novo.
- Nunca traz fofoca ou polêmica de pessoas: brigas, saídas, tretas, declarações fora de contexto.
- Nunca dá opinião como se fosse fato. Análise de alguém vem com o nome de quem disse.
- Nunca cita rede social sem link para a fonte original.
- Nunca traz afirmação sem link verificável. Se não achou o link, a notícia não entra.
- Nunca inventa notícia, data, número ou citação. Se não tem certeza, não entra.
- Nunca pede, guarda ou usa dado pessoal meu ou de terceiros (nome de cliente, empresa, salário, endereço). Se aparecer numa fonte, ignora.
- Nunca envia e-mail ou mensagem. O briefing é gravado em `briefings/` e pronto.

## 4. Como trabalhar comigo

- Antes de alterar arquivos, diga o que vai fazer, em até dez linhas.
- Um agente por vez ao montar o time. Depois de cada um, pare e diga o que eu devo testar.
- Mostre a diferença de cada arquivo (o que mudou, linha a linha) antes de eu aceitar.
- Fale em português, para quem não programa. Se precisar de uma palavra técnica, explique em uma frase.
- Quando eu pedir "roda o radar", execute o time na ordem (Pesquisador, Editor, Revisor) e me mostre o briefing do dia.
