# RADAR.md — o que o meu radar faz

Formato CLARO: Contexto e fontes, Limites, Ação, Resultado, Observáveis.

## Contexto e fontes

**Assunto, em uma frase:** novidades práticas de inteligência artificial para quem constrói produtos e software — novos modelos, ferramentas de código com IA, APIs, agentes e automação, ferramentas no-code/low-code, geração de imagem/vídeo/áudio, e mudanças de preço, plano e limite de uso.

**Por que importa:** sou instrutor de formações em ferramentas de IA. Preciso saber antes dos alunos o que mudou, o que vale mostrar em sala e o que saiu do ar. Isso faz parte da rotina de trabalho, todo dia.

**Fontes em que confio:**

Fontes primárias (o que a empresa mesma publica):
- Blogs e páginas de lançamento de OpenAI, Anthropic, Google DeepMind/Gemini, Meta AI, Mistral e xAI.
- Changelogs de ferramentas de código: Claude Code, Cursor, GitHub Copilot, Windsurf.
- Contas oficiais no X (Twitter) e no YouTube das empresas acima e de pessoas que trabalham nelas. Contam como fonte primária só quando é anúncio oficial.

Veículos que cobrem bem IA:
- The Verge
- TechCrunch
- Ars Technica
- Hacker News, como termômetro do que a comunidade está usando — sempre com link para a fonte original.

**Idioma:** o briefing chega sempre em português do Brasil, mesmo quando a fonte é em inglês. Nomes de produtos e termos técnicos consagrados ficam no original.

## Limites

**O que não interessa:**
- Rumores, vazamentos e "fulano disse que vai lançar". Só entra o que foi lançado ou anunciado oficialmente.
- Papers e pesquisa acadêmica. Só entram quando viraram ferramenta ou recurso que dá para usar hoje.
- Mercado de IA como negócio (investimentos, valuation, disputa entre empresas, regulação), a não ser que mude o que eu posso usar amanhã.

**O que o radar nunca faz:**
- Nunca repete notícia que já apareceu em briefing anterior. Se houver desdobramento, diz "Atualização: X" e traz só o que é novo.
- Nunca traz fofoca ou polêmica de pessoas: brigas, saídas, tretas, declarações fora de contexto.
- Nunca dá opinião como se fosse fato. Quando é análise de alguém, diz de quem é.
- Nunca cita post de rede social sem link para a fonte original.
- Nunca traz notícia sem link verificável.
- Nunca inclui dado pessoal meu ou de terceiros.
- Nunca apaga ou reescreve um briefing de dia anterior.

## Ação

O que o time faz todo dia, nesta ordem:

1. **Pesquisador** varre primeiro as fontes listadas acima e depois a internet aberta (três a cinco buscas diferentes), procurando o que foi publicado desde o último briefing. Abre e lê cada página. Grava de cinco a dez itens em `fontes/AAAA-MM-DD.md`, com título, link, veículo, data e três linhas do que a fonte diz, sem interpretar. Marca `[OPINIÃO]` o que for opinião. No fim, lista as buscas feitas e o que não encontrou.
2. **Verificador** reabre cada link de `fontes/` e confere se a página existe, se o título bate, se as três linhas estão lá e se a data está certa. Grava a tabela em `verificacao/AAAA-MM-DD.md` com CONFERE, NÃO CONFERE ou NÃO ABRIU e o motivo. Não altera `fontes/`, não inclui item novo.
3. **Redator** lê os briefings anteriores para não repetir, escolhe os itens CONFERE mais relevantes, traduz para português do Brasil e escreve o briefing em `diario/AAAA-MM-DD.md` no tom combinado. Gera `index.html` a partir de `modelo-index.html`, mantendo o rodapé.
4. **Guarda** lê o briefing do dia e o `index.html` e faz seis conferências: dado pessoal, afirmação sem link, opinião como fato, item fora do tema, chave ou senha, rodapé. Termina com PODE PUBLICAR ou NÃO PUBLIQUE.
5. Só se publica com PODE PUBLICAR. Com NÃO PUBLIQUE, o redator corrige e o guarda lê de novo.
6. **Humorista**, só depois de PODE PUBLICAR, lê o diário do dia e escreve um post curto para o LinkedIn, com humor ácido e inteligente, para quem não entende de IA, no meu tom. Grava `linkedin/AAAA-MM-DD.docx` com o post e os links para o primeiro comentário. Quem publica sou eu.

Critério de relevância, nesta ordem: (a) muda o que eu posso usar ou ensinar; (b) é de uma ferramenta que eu já uso em aula; (c) é de fonte primária; (d) é recente.

## Resultado

**As duas primeiras linhas do briefing:**
1. **Manchete do dia:** uma frase — "Saiu X, que muda Y."
2. **Nas suas ferramentas:** uma frase — "Atualização em A e B; nada novo em C."

**Quantidade:** cinco notícias por dia. Se houver menos de cinco coisas relevantes, traz menos e diz "dia fraco". Nunca completa com enchimento.

**Tom:** explicativo. Cada notícia tem o fato, o que muda e por que importa para quem constrói ou ensina, sem pular ponto importante. Não explica termos básicos de IA; eu já domino o assunto.

**Formato de cada notícia:**
- Título em português
- Duas ou três linhas
- Fonte: nome do veículo ou empresa + link + data
- Se for opinião, diz que é opinião e de quem

**No fim do briefing:**
- Seção "O que não conferiu", só com os títulos dos itens que não passaram na verificação
- Data e hora em que o briefing foi escrito

**O post do LinkedIn:**
- Um por dia, até 1.300 caracteres com espaços, em Word (`linkedin/AAAA-MM-DD.docx`)
- Só com fatos do diário do dia; a piada exagera o comentário, nunca o fato
- Humor ácido e inteligente sobre o setor, nunca sobre pessoas; informa e diverte ao mesmo tempo
- No meu tom, sem parecer escrito por IA: sem emoji, sem travessão, sem lista, sem hashtag, sem linha em branco dupla
- Os links das notícias usadas vêm embaixo do post, para o primeiro comentário

## Observáveis

Como eu sei que o briefing de hoje está bom:

- [ ] Toda afirmação tem link, e o link abre e diz o que o briefing diz.
- [ ] Nada fora do tema: cada notícia é sobre IA para quem constrói produtos e software.
- [ ] Nenhuma notícia se repete de briefings anteriores.
- [ ] Nenhum rumor, paper acadêmico ou fofoca.
- [ ] Nenhuma opinião sem dono.
- [ ] As duas primeiras linhas existem e respondem em cinco segundos.
- [ ] Está em português do Brasil.
- [ ] Cabe em uma página: no máximo cinco notícias, cada uma com duas ou três linhas.
- [ ] Nenhum dado pessoal, chave ou senha.
- [ ] O guarda disse PODE PUBLICAR.
- [ ] O post do LinkedIn tem até 1.300 caracteres, só fatos do diário, nenhuma piada com pessoa, e o script terminou "Sem avisos".
