---
name: 06-lista-negra-e-governanca
description: Define regras de segurança operacional na prospecção B2B, incluindo lista negra definitiva, bloqueio geográfico/nicho, filtro de bots, limites de disparo e autópsia pós-perda. Use antes de iniciar buscas, disparos ou revisar conversas perdidas.
---

# Lista Negra e Governança de Prospecção

Operação grande não escala queimando número nem insistindo em quem pediu para sair. Esta skill protege a reputação da marca, o chip de WhatsApp e a qualidade do funil.

## 1. Protocolo de Lista Negra (Bloqueio Definitivo)
Um contato entra **imediatamente e para sempre** na lista negra quando:
- Pede para sair (*"me tira da lista"*, *"para de mandar mensagem"*, *"não quero mais contato"*).
- Diz um "não" claro e definitivo (*"não tenho interesse"*, *"já temos quem faça e não vamos mudar"*).
- Bloqueia, denuncia ou demonstra irritação explícita com a abordagem.
- É marcado manualmente pelo operador como contato proibido.

**Regra de execução:**
- Antes de **qualquer** disparo frio ou follow-up, valide se o número ou ID está na lista negra.
- Nunca tente abordar o mesmo contato por outro número, outro canal ou outra variação de texto depois que ele entrou na lista negra.

## 2. Filtros de Operação (Preencher Antes de Rodar)
Configure os parâmetros abaixo para a sua realidade antes de iniciar os disparos:

```yaml
nicho_alvo: "[Ex: Advogados, Médicos Especialistas, Arquitetos, Consultores B2B]"
nichos_proibidos: "[Ex: Negócios de ticket baixo que não comportam a oferta]"
regiao_bloqueada: "[Ex: Cidade sede + raio de 50 km, se aplicável]"
limite_diario_novos: 20
limite_por_hora: 2
janela_horario: "08:00-19:59"
```

## 3. Higiene de Fila e Filtro de Bots
- **Número sem WhatsApp:** se o retorno técnico indicar que o telefone não tem WhatsApp, marque como inválido e não tente reenviar no mesmo número.
- **Respostas automáticas:** mensagens de saudação automática, menu de URA (*"Digite 1 para..."*) ou aviso de ausência **não** significam que um humano respondeu. Não avance o funil nem responda como se fosse conversa iniciada.
- **Anti-rajada:** respeite o limite por hora e o intervalo entre requisições de busca/envio para evitar bloqueio de API (HTTP 429) e banimento de linha.

## 4. Autópsia Pós-Conversa (Melhoria Contínua)
Toda conversa relevante encerrada ou lead perdido deve passar por uma revisão de 3 perguntas:
1. **Onde travou?** (abertura, diagnóstico, envio de prévia, preço ou objeção).
2. **O que gerou atrito ou silêncio?** (mensagem longa demais, oferta cedo demais, pergunta fechada).
3. **Qual ajuste entra no playbook?** Atualize as respostas das skills `01` a `05` sempre que uma nova objeção aparecer ou uma abordagem converter melhor.
