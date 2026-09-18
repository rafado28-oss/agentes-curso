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

- `CLAUDE.md`, `RADAR.md`, `README.md`, `modelo-index.html` e `index.html` ficam na raiz desta pasta.
- As anotações brutas do pesquisador ficam em `fontes/AAAA-MM-DD.md`, um arquivo por dia.
- A conferência do verificador fica em `verificacao/AAAA-MM-DD.md`, um arquivo por dia.
- O briefing fica em `diario/AAAA-MM-DD.md`, um arquivo por dia (exemplo: `diario/2026-09-18.md`).
- `index.html` é a página do briefing do dia, gerada a partir de `modelo-index.html`. O modelo não muda; só o `index.html` é regravado.
- O post do LinkedIn fica em `linkedin/AAAA-MM-DD.docx` (e o texto de trabalho em `linkedin/AAAA-MM-DD.txt`), um por dia.
- Os posts meus que servem de referência de tom ficam em `estilo/exemplos.md`. Só eu escrevo nesse arquivo.
- Scripts de apoio ficam em `ferramentas/`. Hoje há um: `post_para_docx.py`, que transforma o texto do post em Word e confere as regras dele.
- Os agentes do time ficam em `.claude/agents/`. São cinco: `pesquisador`, `verificador`, `redator`, `guarda` e `humorista`.
- O que vai para a internet (GitHub Pages) é o `index.html`, que aponta para os arquivos de `diario/`. O repositório inteiro é público, então nenhum arquivo desta pasta pode ter dado pessoal, chave ou senha.

### Fontes

- Fontes primárias: blogs e páginas de lançamento de OpenAI, Anthropic, Google DeepMind/Gemini, Meta AI, Mistral e xAI; changelogs de Claude Code, Cursor, GitHub Copilot e Windsurf; contas oficiais no X e no YouTube dessas empresas e de quem trabalha nelas, só quando é anúncio oficial.
- Veículos: The Verge, TechCrunch, Ars Technica, Hacker News (só como termômetro, sempre com link para a fonte original).
- Post de terceiros em rede social só entra se tiver link para a fonte original.
- Fonte nova só entra nesta lista se eu aprovar.

### Idioma

- O briefing é sempre em português do Brasil, mesmo quando a fonte é em inglês.
- Nomes de produtos e termos técnicos consagrados ficam no original (ex.: "Claude Code", "MCP", "prompt caching").

### O time e a ordem do trabalho

1. **Pesquisador** (monitor): varre as fontes preferidas e depois a internet aberta, lê cada página e grava de cinco a dez itens em `fontes/AAAA-MM-DD.md`, com título, link, veículo, data e três linhas do que a fonte diz, sem interpretar. Marca `[OPINIÃO]` o que for opinião. Não escolhe, não opina.
2. **Verificador** (auditor): reabre cada link de `fontes/` e confere se a página existe, se o título bate, se as três linhas estão lá e se a data está certa. Grava a tabela em `verificacao/AAAA-MM-DD.md` com CONFERE, NÃO CONFERE ou NÃO ABRIU. Não altera `fontes/`, não inclui item novo.
3. **Redator** (consolidador): lê os diários anteriores para não repetir, escolhe os itens CONFERE mais relevantes, traduz e escreve o briefing em `diario/AAAA-MM-DD.md` no tom combinado. Gera `index.html` a partir de `modelo-index.html`.
4. **Humorista** (consolidador): depois do redator e antes do guarda, lê o diário do dia e escreve um post curto para o LinkedIn (até 1.300 caracteres), com humor ácido e inteligente, para quem não entende de IA, no meu tom. Grava `linkedin/AAAA-MM-DD.docx` com o post e os links para o primeiro comentário; o texto do post também entra no fim do diário, numa seção `## humorista`, para o guarda revisar. Não publica.
5. **Guarda** (auditor): lê o diário do dia e o `index.html` e faz seis conferências: dado pessoal, afirmação sem link, opinião como fato, item fora do tema, chave ou senha, rodapé. Termina com PODE PUBLICAR ou NÃO PUBLIQUE. Só lê.
- A ordem de execução é a da skill `radar`: pesquisador, verificador, redator, humorista, guarda. Só se publica com PODE PUBLICAR. Com NÃO PUBLIQUE, nada é gravado no repositório até eu resolver.
- Critério de relevância, nesta ordem: (a) muda o que eu posso usar ou ensinar; (b) é de ferramenta que já uso em aula; (c) é de fonte primária; (d) é recente.

### Formato do briefing

- Linha 1 — **Manchete do dia:** uma frase, "Saiu X, que muda Y."
- Linha 2 — **Nas suas ferramentas:** uma frase, "Atualização em A e B; nada novo em C."
- Depois, até cinco notícias. Cada uma com: título em português; duas ou três linhas com o fato, o que muda e por que importa, sem pular ponto importante; fonte com nome + link + data.
- Opinião só entra atribuída: "Segundo Fulano, da Empresa X".
- No fim, a seção "O que não conferiu", só com os títulos dos itens que não passaram na verificação, e a data e hora em que o briefing foi escrito.
- Tom explicativo. Não explica termos básicos de IA.
- Se houver menos de cinco coisas relevantes, traz menos e diz "dia fraco". Nunca completa com enchimento.
- Cabe em uma página.

### Formato do post do LinkedIn

- Um post por dia, até 1.300 caracteres com espaços, três a cinco parágrafos curtos, uma linha em branco entre eles.
- Todo fato do post está no diário do dia. A piada pode exagerar o comentário, nunca o fato.
- Humor ácido e inteligente sobre o setor, nunca sobre pessoas. Informa e diverte ao mesmo tempo.
- No meu tom: direto, informal, primeira pessoa, frases curtas. Nada que pareça escrito por IA: sem emoji, sem travessão, sem lista, sem hashtag, sem linha em branco dupla, sem as frases feitas.
- Os links das notícias usadas vão no `.docx`, embaixo do post, para eu colar no primeiro comentário.

## 3. O que este radar nunca faz

- Nunca repete notícia de briefing anterior. Desdobramento entra como "Atualização: X", só com o que é novo.
- Nunca traz fofoca ou polêmica de pessoas: brigas, saídas, tretas, declarações fora de contexto.
- Nunca dá opinião como se fosse fato. Análise de alguém vem com o nome de quem disse.
- Nunca cita rede social sem link para a fonte original.
- Nunca traz afirmação sem link verificável. Se não achou o link, a notícia não entra.
- Nunca inventa notícia, data, número ou citação. Se não tem certeza, não entra.
- Nunca pede, guarda ou usa dado pessoal meu ou de terceiros (nome de cliente, empresa, salário, endereço). Se aparecer numa fonte, ignora.
- Nunca apaga ou reescreve um diário de dia anterior.
- Nunca faz piada com pessoa, nem com nome, nem por descrição. Empresa e produto podem.
- Nunca envia e-mail ou mensagem, nem publica no LinkedIn. O briefing é gravado em `diario/`, vira `index.html`, o post fica em `linkedin/` e pronto. Quem posta sou eu.

## 4. Como trabalhar comigo

- Antes de alterar arquivos, diga o que vai fazer, em até dez linhas.
- Um agente por vez ao montar o time. Depois de cada um, pare e diga o que eu devo testar.
- Mostre a diferença de cada arquivo (o que mudou, linha a linha) antes de eu aceitar.
- Fale em português, para quem não programa. Se precisar de uma palavra técnica, explique em uma frase.
- Quando eu pedir "roda o radar" (ou usar `/radar`), use a skill `radar` em `.claude/skills/radar/SKILL.md`. Ela roda o time na ordem, grava o dia com um commit se o guarda aprovar, e me mostra a manchete, a contagem e a decisão do guarda.
