---
name: 06-lista-negra-e-governanca
description: Define as ordens obrigatórias de governança para qualquer operação de prospecção: Lista Negra de Jargões (30+ termos banidos), Lista Negra definitiva de contatos (opt-out cross-channel), filtros configuráveis de nicho e região, higiene contra bots e autópsia pós-perda. Use antes de escrever ou enviar qualquer mensagem e após toda conversa encerrada.
---

# 06. Lista Negra e Governança de Operação

Esta skill é o **freio de segurança e qualidade** da operação inteira. Nenhuma mensagem sai sem passar pelas checagens abaixo.

---

## ORDEM DIRETA 1: Lista Negra de Jargões (Bloqueio Obrigatório)

**Instrução ao Agente:**
ANTES de entregar qualquer rascunho ou enviar qualquer mensagem no WhatsApp, LinkedIn, E-mail ou Direct, varra o texto inteiro contra a lista abaixo. Se encontrar **qualquer** termo desta lista (ou variação próxima), **bloqueie e reescreva** usando linguagem direta de conversa real.

### Palavras e Expressões Banidas
- **Clichês corporativos:** `alavancar`, `transformação digital`, `sinergia`, `ecossistema`, `disruptivo`, `escalar resultados`, `virada de chave`, `próximo nível`, `solução inovadora`, `solução completa`, `parceria estratégica`, `maximizar`, `potencializar`, `otimização 360`.
- **Clichês de cold mail / SDR robô:** `espero que este e-mail o encontre bem`, `gostaria de apresentar`, `sem compromisso algum, apenas 15 minutinhos na sua agenda`, `somos líderes no mercado`, `atendemos grandes players`, `oportunidade imperdível`, `vi seu perfil e fiquei impressionado`.
- **Pressão falsa:** `últimas vagas`, `só hoje`, `promoção relâmpago`, `não perca essa chance`.
- **Formatação artificial:** travessão longo (`—`) no meio de frases de WhatsApp/Direct, excesso de emojis ou listas com marcadores em mensagem curta.

### Tabela de Substituição Rápida

| Em vez de escrever (Banido) | Escreva assim (Linguagem Real) |
| :--- | :--- |
| *"alavancar suas vendas"* | *"trazer mais cliente pronto para fechar"* |
| *"transformação digital da sua empresa"* | *"organizar como o cliente te encontra e fala com você"* |
| *"solução inovadora e escalável"* | *"estrutura simples que funciona no dia a dia"* |
| *"espero que esteja bem, gostaria de apresentar..."* | *"vi [FATO] aí na [EMPRESA] e notei um ponto rápido..."* |
| *"15 minutinhos na sua agenda"* | *"posso te mandar em 3 linhas por aqui mesmo?"* |

---

## ORDEM DIRETA 2: Lista Negra de Contatos (Opt-Out Definitivo)

Um contato entra **imediatamente e para sempre** na lista negra quando ocorrer qualquer um destes casos:
1. Pediu para sair (*"me tira da lista"*, *"para de mandar mensagem"*, *"não me procure mais"*).
2. Deu um **"não" definitivo** (*"não tenho interesse"*, *"já temos e não vamos trocar"*).
3. Demonstrou irritação, ameaçou bloqueio ou denunciou spam.
4. É **concorrente direto**, **cliente ativo** ou foi **bloqueado manualmente** pelo dono da operação.

**Regras de Bloqueio:**
- **Bloqueio cross-channel:** se pediu para sair no WhatsApp, fica bloqueado também no LinkedIn, E-mail e Direct. Nunca contorne o bloqueio por outro número ou outra conta.
- **Checagem obrigatória pré-envio:** antes de cada disparo novo ou follow-up, confirme que o telefone, e-mail, domínio e perfil não constam na lista negra.

---

## ORDEM DIRETA 3: Parâmetros Configuráveis da Operação

Preencha este bloco ao plugar as skills na sua operação:

```yaml
minha_oferta: "[O que você vende em 1 frase simples]"
ticket_medio: "[Faixa de valor]"
canais_ativos: ["WhatsApp", "LinkedIn", "Email", "Direct"]
nichos_alvo: "[Quem tem dor real e dinheiro para pagar]"
nichos_proibidos: "[Perfis que não fecham ou não têm margem]"
regiao_bloqueada: "[Cidades ou estados onde você não prospecta]"
limite_diario_por_canal:
  whatsapp: 20
  linkedin: 20
  email: 30
  direct: 15
janela_horario: "08:00-19:59"
```

---

## ORDEM DIRETA 4: Higiene de Fila e Filtro de Bots
- **Inválidos / Bounces:** número sem WhatsApp ou e-mail que deu bounce volta como inválido e sai da fila na hora (nunca retente em loop).
- **Filtro de Bots:** mensagem automática de recepção, menu numérico (*"Digite 1..."*), resposta de ausência (*Out of Office*) não conta como resposta humana. Não dispare etapa de diagnóstico para bot.
- **Anti-rajada:** mantenha intervalo entre disparos e buscas para evitar erro 429 ou bloqueio de conta/chip.

---

## ORDEM DIRETA 5: Autópsia Pós-Perda (Evolução Contínua)
Sempre que uma conversa esfriar ou terminar em perda, registre em 4 linhas antes de seguir:
1. **Canal e Etapa:** onde o lead parou (abertura, pesquisa, diagnóstico, exemplo, preço ou objeção)?
2. **Gatilho de Atrito:** qual frase sua gerou silêncio ou recusa?
3. **Falha de Filtro:** esse lead deveria ter sido barrado antes (nicho errado, sem decisor, sem dor)?
4. **Ação no Playbook:** qual ajuste entra nas skills `01` a `05` para não repetir o erro?
