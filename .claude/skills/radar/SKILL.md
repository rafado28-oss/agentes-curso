---
name: radar
description: roda o radar do dia com o time de agentes, na ordem pesquisador, verificador, redator, guarda (e o agente do dono, se existir), e depois grava o dia no repositório com um commit; use quando alguém pedir para rodar o radar ou quando a rotina das 7h disparar.
---

# Rodar o radar do dia

Você coordena o time. Você não pesquisa, não escreve o briefing e não revisa: cada agente faz a sua parte e você confere que a parte foi feita antes de chamar o próximo. As regras do radar estão em `CLAUDE.md` e `RADAR.md`; leia os dois antes de começar.

Esta skill roda de ponta a ponta sem parar para perguntar, porque também dispara sozinha às 7h. A regra "um agente por vez, pare e diga o que testar" do `CLAUDE.md` vale para montar o time, não para rodar o radar. A única parada é o NÃO PUBLIQUE do guarda.

Antes da etapa 1, descubra a data de hoje com `date +%F` no terminal (formato `AAAA-MM-DD`). Passe essa data na tarefa de cada agente; eles não devem adivinhar.

Siga as sete etapas nesta ordem, uma por vez, sem pular nenhuma.

## Etapa 1: pesquisador

Acione o agente `pesquisador` com a tarefa: "Pesquise o radar do dia AAAA-MM-DD e grave `fontes/AAAA-MM-DD.md`."

Quando ele terminar, confira:
- `fontes/AAAA-MM-DD.md` existe.
- Tem pelo menos três itens (linhas começando com `### `).

Se tiver menos de três, ou se o pesquisador disser que não achou nada novo, **siga mesmo assim**: o briefing do dia pode ser "dia fraco". Anote quantos itens ele gravou para a etapa 7. Só pare se o arquivo não existir; nesse caso, acione o pesquisador de novo uma vez, e se ainda assim não existir, pare e diga o que aconteceu.

## Etapa 2: verificador

Acione o agente `verificador` com a tarefa: "Confira os itens de `fontes/AAAA-MM-DD.md` e grave `verificacao/AAAA-MM-DD.md`."

Quando ele terminar, confira:
- `verificacao/AAAA-MM-DD.md` existe.
- Tem a tabela e a seção "Contagem" com os números de CONFERE, NÃO CONFERE e NÃO ABRIU.
- O total conferido bate com o número de itens de `fontes/`.

Anote quantos CONFERE para a etapa 7. Se nenhum item conferiu, siga mesmo assim; o redator vai escrever "dia fraco".

## Etapa 3: redator

Acione o agente `redator` com a tarefa: "Escreva o briefing do dia AAAA-MM-DD em `diario/AAAA-MM-DD.md` e gere `index.html` a partir de `modelo-index.html`."

Quando ele terminar, confira:
- `diario/AAAA-MM-DD.md` existe e começa com as duas linhas que `RADAR.md` pede (manchete do dia e nas suas ferramentas).
- `index.html` existe e não tem nenhum marcador `{{` sobrando.
- Se o redator disse que `modelo-index.html` não existe, siga, mas anote para dizer no fim.

## Etapa 4: o agente do dono, se existir

Liste os arquivos de `.claude/agents/`. Os quatro do time são `pesquisador`, `verificador`, `redator` e `guarda`. Se houver qualquer outro, acione-o, um de cada vez, com a tarefa: "Faça o seu trabalho para o dia AAAA-MM-DD."

Pegue o texto que ele devolver (o resultado dele, não o registro das ferramentas que usou) e acrescente no fim de `diario/AAAA-MM-DD.md` uma seção com o nome do agente, assim:

```
## humorista

texto que ele devolveu
```

Se não houver agente extra, pule esta etapa e anote isso.

## Etapa 5: guarda

Acione o agente `guarda` com a tarefa: "Confira `diario/AAAA-MM-DD.md` e `index.html` do dia AAAA-MM-DD antes de publicar."

Leia a última linha da resposta dele:
- **NÃO PUBLIQUE**: pare aqui. Mostre o relatório completo do guarda. Não faça commit, não faça push, não tente corrigir sozinho. Diga que o radar do dia ficou gravado na pasta mas não foi publicado, e por quê.
- **PODE PUBLICAR**: siga para a etapa 6.

Se a última linha não for nenhuma das duas, trate como NÃO PUBLIQUE.

## Etapa 6: gravar o dia

Só com PODE PUBLICAR. No terminal, na raiz da pasta:

```bash
git add -A
git commit -m "radar de AAAA-MM-DD" -m "Co-Authored-By: Claude Opus 5 <noreply@anthropic.com>"
```

Depois, se houver remoto (`git remote -v` mostra algum), faça `git push`. Se não houver remoto, diga que o dia ficou gravado só localmente.

Se o push falhar, **diga o motivo exato** (a mensagem que o git devolveu) e pare. Não tente contornar: não troque de conta, não crie chave, não mude configuração, não force. O commit local fica feito; o dono resolve o envio.

## Etapa 7: relatório final

Mostre, em poucas linhas:
- A primeira linha do briefing (a manchete do dia).
- Quantos itens o pesquisador achou e quantos conferiram.
- Quantos agentes rodaram (quatro, ou cinco com o agente do dono) e o nome de cada um.
- Se houve commit e push, e se o push falhou, o motivo.
- O que ficou pendente, se houver (modelo da página ausente, dia fraco, agente extra que não devolveu nada).

## Nunca

- Nunca envie nada a ninguém além do commit e do push. Sem e-mail, sem mensagem, sem publicar em rede social.
- Nunca use chave, senha ou token, nem peça um. Se o push pedir login, diga isso e pare.
- Nunca pule uma etapa nem mude a ordem.
- Nunca faça commit com NÃO PUBLIQUE.
- Nunca altere `RADAR.md`, `CLAUDE.md` ou os agentes durante a rodada.
- Nunca apague ou reescreva um dia anterior.
