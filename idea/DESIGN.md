# Economax Design Direction

## 1. Resumo

O Economax deve parecer o sistema operacional financeiro da casa: um lugar calmo, privado e compartilhado para entender o dinheiro de hoje, antecipar o que vem pela frente e transformar planos de vida em projetos possíveis.

O produto não deve parecer um banco, uma planilha ou um painel corporativo. A experiência precisa combinar:

- clareza emocional do YNAB;
- visão consolidada de casa do Monarch Money;
- acabamento premium do Copilot Money;
- projeção prática de caixa do Quicken Simplifi;
- foco em economia imediata do Rocket Money;
- linguagem local e natural do Organizze.

## 2. Princípio de produto

**Promessa:** "Entenda o dinheiro de hoje. Planeje a vida de amanhã."

**Personalidade:** acolhedora, inteligente, discreta, prática, otimista e sem julgamento.

**Modelo mental:**

```text
Hoje                 Próximos meses             Projetos de vida
saldo e decisões  -> contas e previsões      -> metas e cenários
```

### O que a primeira versão precisa provar

1. Duas pessoas conseguem registrar e entender a vida financeira da casa sem depender de planilha.
2. O painel mostra rapidamente se o mês está confortável, apertado ou em risco.
3. Um projeto como "Tokyo 2027" transforma uma intenção em meta, estimativa, parcelas e progresso.
4. A privacidade de desejos e presentes é compreensível e confiável.

## 3. Direção visual

### Conceito: Calm Glass House

Liquid glass, mas com calor humano. O vidro aparece como uma camada de foco e profundidade, não como decoração em todos os componentes. Use fundos sólidos suaves, painéis translúcidos em áreas de destaque, bordas finas e sombras difusas.

**Referências visuais próprias:**

- [Moodboard Economax](./assets/economax-moodboard.png)
- [Atmosfera glass](./assets/economax-glass-atmosphere.png)

**Referências de produto do benchmark:**

- [YNAB](./assets/ynab.png): narrativa e onboarding;
- [Monarch Money](./assets/monarch.png): dashboard de família;
- [Copilot Money](./assets/copilot.png): acabamento premium;
- [Quicken Simplifi](./assets/simplifi.png): projeção de caixa;
- [Rocket Money](./assets/rocketmoney.png): recorrências e economia;
- [Organizze](./assets/organizze.png): contexto brasileiro.

### Evitar

- roxo, azul neon ou estética cripto;
- excesso de blur que prejudique leitura;
- cartões brancos empilhados sem hierarquia;
- gráficos decorativos sem decisão associada;
- tom de culpa, alerta constante ou gamificação infantil;
- telas que parecem um ERP ou aplicativo bancário genérico.

## 4. Paleta de cores

### Tokens principais

| Token | Hex | Uso |
|---|---|---|
| `ink-950` | `#102A30` | títulos, navegação profunda, alto contraste |
| `petrol-900` | `#123C45` | fundo principal, hero, marca |
| `petrol-700` | `#1B6670` | ações secundárias, links, gráficos |
| `teal-500` | `#4EA8A0` | indicadores positivos e destaque de dados |
| `mint-200` | `#B8E6C1` | superfícies de progresso e sucesso suave |
| `lime-300` | `#CBEF72` | CTA principal, metas, progresso ativo |
| `ivory-50` | `#FBFAF6` | fundo claro e leitura |
| `ivory-100` | `#F5F1E8` | superfície quente, empty states |
| `mist-200` | `#DCE9E7` | bordas, divisores e controles inativos |
| `graphite-500` | `#5A6B6F` | textos auxiliares |
| `coral-400` | `#F58B7B` | atenção, vencimento próximo, excesso |
| `red-600` | `#C94F58` | erro, atraso, risco confirmado |

### Regras de uso

- A base da interface é `ivory-50`, não branco puro.
- Use `petrol-900` em navegação lateral, hero de onboarding e estados de privacidade.
- Use `lime-300` somente para ações primárias e metas; não usar como cor de texto longo.
- Use `coral-400` como sinal contextual, nunca para pintar toda a tela de alerta.
- Em modo escuro opcional, inverter superfícies para `petrol-900` e preservar `ivory-50` para números principais.

### Gradientes

```css
--gradient-hero: linear-gradient(135deg, #123C45 0%, #1B6670 58%, #4EA8A0 100%);
--gradient-goal: linear-gradient(135deg, #CBEF72 0%, #B8E6C1 100%);
--gradient-surface: linear-gradient(135deg, rgba(255,255,255,.72), rgba(220,233,231,.42));
```

## 5. Tipografia

Use **Manrope** para títulos e números e **DM Sans** para texto de interface. As duas são amigáveis, contemporâneas e têm boa leitura em português.

| Estilo | Fonte | Tamanho desktop | Peso |
|---|---|---:|---:|
| Display | Manrope | 48-64 px | 700 |
| H1 | Manrope | 36 px | 700 |
| H2 | Manrope | 24 px | 700 |
| H3 | Manrope | 18 px | 700 |
| Corpo | DM Sans | 15-16 px | 400 |
| Label | DM Sans | 12-13 px | 600 |
| Número financeiro | Manrope | 28-44 px | 700 |

Use frases curtas, verbos de ação e moeda sempre com contexto. Exemplo: **"R$ 4.280 livres este mês"**, não apenas **"R$ 4.280"**.

## 6. Tokens de interface

```text
Grid desktop: 12 colunas, gutter 24 px, margem 32 px
Grid tablet: 8 colunas, gutter 16 px, margem 24 px
Grid mobile: 4 colunas, gutter 12 px, margem 16 px

Raio pequeno: 12 px
Raio padrão: 20 px
Raio destaque: 28 px
Raio pill: 999 px

Borda glass: 1 px rgba(255,255,255,.48)
Sombra glass: 0 18px 50px rgba(18,60,69,.10)
Sombra elevada: 0 22px 70px rgba(18,60,69,.16)
Blur glass: 18-28 px
```

## 7. Arquitetura de informação

Navegação principal no desktop:

1. Visão geral
2. Lançamentos
3. Contas e cartões
4. Orçamento
5. Projeções
6. Projetos
7. Desejos privados
8. Configurações

No mobile, usar barra inferior com cinco destinos: **Visão geral, Lançamentos, Adicionar, Projetos, Mais**.

### Contexto de casa

No topo, sempre mostrar o contexto atual: **Casa Lopes**, avatar dos dois membros, período selecionado e estado de sincronização local. A troca entre visão pessoal e visão da casa deve ser explícita.

## 8. Telas prioritárias para o protótipo

### Tela 1: onboarding da casa

Hero calmo com o texto: **"Organizem o dinheiro da casa sem perder o que importa."**

Mostrar três benefícios: visão compartilhada, projeção do futuro e privacidade dos desejos. Pedir nome da casa, membros, moeda e primeiro objetivo. O wizard deve ter 4 passos visíveis no topo, com avanço suave e possibilidade de voltar.

### Tela 2: visão geral

Desktop com sidebar estreita e canvas amplo. Hero do dashboard:

- saudação e período: "Boa noite, vocês";
- saldo consolidado;
- frase de leitura: "O mês está confortável até o dia 31";
- CTA `Adicionar lançamento` em lime;
- botão discreto `Perguntar ao Economax`.

Blocos na ordem:

1. **Saúde do mês:** entradas, gastos, comprometido, livre;
2. **Fluxo até o fim do mês:** gráfico de linha/área com realizado e previsto;
3. **Próximos compromissos:** contas, cartões, financiamentos e recorrências;
4. **Projetos em andamento:** Tokyo 2027, reserva e outros;
5. **Últimos lançamentos:** lista com categoria, membro, conta e comprovante.

### Tela 3: adicionar lançamento em wizard

O botão central deve abrir uma jornada de 4 passos:

1. tipo: entrada, gasto, transferência ou dívida;
2. valor, data, conta/cartão e recorrência;
3. categoria, projeto e responsável;
4. comprovante, observação e revisão.

Permitir anexar imagem do comprovante com preview, compressão e indicador de privacidade. Ao concluir, exibir confirmação curta com o impacto no mês.

### Tela 4: projeções

Tela dedicada a responder **"quanto teremos disponível e quando?"**. Ter um seletor de cenário: base, conservador e projeto. Mostrar 3, 6 e 12 meses em abas.

O gráfico deve separar:

- linha sólida: realizado;
- linha pontilhada: previsto;
- faixa sombreada: intervalo provável;
- marcadores: contas grandes, parcelas e metas.

Ao tocar em um mês, abrir o resumo de entradas, gastos, saldo final e risco. Nunca usar vermelho sem explicar a causa e a ação sugerida.

### Tela 5: projeto "Tokyo 2027"

Hero com imagem abstrata de destino, meta total, data e progresso. Mostrar:

- valor estimado pela casa;
- valor já reservado;
- contribuição mensal sugerida;
- cenários de custo baixo, provável e alto;
- itens do projeto, responsáveis e prazo;
- botão `Recalcular com contexto`.

O assistente local pode perguntar duração, estilo da viagem, número de pessoas e moeda. A resposta deve sempre mostrar premissas editáveis, nunca apresentar estimativa como verdade.

### Tela 6: desejos privados

Tela com linguagem de privacidade: **"Aqui, cada um guarda seus desejos. O outro vê apenas o que pode escolher presentear."**

Separar em dois modos:

- **Minha lista:** item, foto, grau de desejo de 1 a 10, faixa de preço, observação e prioridade;
- **Sugestões para presentear:** somente itens autorizados para recomendação, ordenados por desejo e compatibilidade com orçamento.

O protótipo deve mostrar um cadeado visível, estado de dados protegidos e nenhuma prévia indevida da lista privada da outra pessoa.

### Tela 7: detalhes de conta/cartão

Exibir saldo, limite, fatura atual, próximas parcelas, recorrências e lançamentos. Cartão deve ser visualizado como objeto doméstico útil, não como anúncio. Mostrar o impacto futuro das compras parceladas.

### Tela 8: empty states e risco

Criar pelo menos três estados:

- casa recém-criada: convite para importar ou adicionar primeira conta;
- sem projetos: convite para transformar um plano em projeto;
- mês apertado: linguagem objetiva, acolhedora e acionável, com maior conta causadora e opções de ajuste.

## 9. Componentes essenciais

- `GlassPanel`: painel translúcido com borda e contraste acessível;
- `MoneySummary`: número, legenda, variação e contexto temporal;
- `CashflowChart`: realizado, previsto, intervalo e marcadores;
- `UpcomingList`: contas agrupadas por data e impacto;
- `TransactionRow`: ícone de categoria, descrição, membro, valor, status e anexo;
- `GoalCard`: meta, prazo, progresso e contribuição sugerida;
- `PrivacyBadge`: estado de proteção e escopo de visibilidade;
- `WizardStepper`: etapas, validação e revisão final;
- `ScenarioToggle`: base, conservador e projeto;
- `HouseholdSwitcher`: visão da casa e visão pessoal;
- `AssistantPrompt`: perguntas em português natural com respostas explicáveis.

## 10. Motion e interação

- Entrada de página: fade + deslocamento vertical de 12 px, 450 ms;
- Cards do dashboard: stagger de 60 ms, no máximo 5 cards;
- Wizard: transição horizontal curta de 280 ms;
- Gráfico: desenhar linhas em 600 ms, sem animação infinita;
- Glass: brilho sutil ao passar o mouse, sem parallax exagerado;
- Feedback de salvar: check lime, micro movimento de escala e texto confirmando impacto.

Respeitar `prefers-reduced-motion`. Nenhuma informação pode depender apenas de animação ou cor.

## 11. Responsividade

Desktop deve priorizar leitura em 1440 px. Tablet mantém sidebar recolhida e cards em duas colunas. Mobile transforma o dashboard em uma sequência editorial: resumo, fluxo, próximos compromissos, projetos e lançamentos.

No mobile, o wizard é tela cheia, o teclado não deve cobrir campos e o CTA `Adicionar` deve ficar sempre acessível. Gráficos devem permitir rolagem horizontal controlada ou reduzir a quantidade de pontos sem perder a leitura.

## 12. Acessibilidade e confiança

- contraste mínimo WCAG AA;
- foco visível em teclado;
- labels persistentes em valores monetários;
- estados de erro próximos ao campo;
- datas no formato brasileiro e moeda em BRL;
- linguagem sem culpa: trocar "você estourou" por "este gasto alterou a previsão";
- explicação de cada previsão: dados considerados, período e grau de confiança;
- privacidade visível em todos os fluxos de desejos e presentes.

## 13. Dados de demonstração

Usar dados plausíveis e domésticos para deixar o protótipo vivo:

```text
Casa: Lopes
Membros: James e Josi
Período: Setembro de 2026
Saldo consolidado: R$ 18.420,80
Entradas previstas: R$ 12.800,00
Comprometido: R$ 7.430,00
Livre até o fim do mês: R$ 5.370,80

Projeto: Tokyo 2027
Meta: R$ 28.000,00
Reservado: R$ 8.640,00
Contribuição sugerida: R$ 1.420,00/mês

Próximos compromissos:
- Aluguel, 10/09, R$ 2.400,00
- Fatura Nubank, 12/09, R$ 1.860,40
- Internet, 15/09, R$ 119,90
- Parcela notebook, 20/09, R$ 480,00
```

## 14. Prompt mestre para o Stitch

Copie o bloco abaixo como instrução principal. Depois, anexe as imagens em `idea/assets/` como referências visuais.

```text
Crie um protótipo responsivo de alta fidelidade para o Economax, uma ferramenta local de gestão financeira doméstica para James e Josi.

O produto é o sistema operacional financeiro da casa: ajuda a entender o dinheiro de hoje, prever os próximos meses e transformar planos em projetos. Não pareça um banco, uma planilha ou um ERP. A sensação deve ser calma, premium, acolhedora, inteligente e confiável.

Direção visual: Calm Glass House. Use liquid glass com moderação: painéis translúcidos, blur de 18-28 px, bordas finas claras e sombras difusas sobre fundo marfim azulado. Fundo principal #FBFAF6. Use azul-petróleo #123C45 para navegação e áreas de confiança, teal #1B6670 para dados, lima #CBEF72 para CTAs e progresso, verde menta #B8E6C1 para sucesso e coral #F58B7B apenas para atenção. Não use roxo, neon, crypto, excesso de preto ou cards brancos empilhados.

Tipografia: Manrope para títulos e números, DM Sans para textos de interface. Números financeiros grandes e legíveis. Use português do Brasil e BRL.

Crie as seguintes telas conectadas:
1. onboarding da casa em wizard de 4 passos;
2. dashboard Visão geral com saldo, saúde do mês, cash flow previsto, próximos compromissos, projetos e lançamentos;
3. wizard Adicionar lançamento com tipo, valor, conta, categoria, projeto, comprovante e revisão;
4. Projeções com cenários base, conservador e projeto, horizonte de 3, 6 e 12 meses, realizado versus previsto;
5. Projeto Tokyo 2027 com meta, progresso, estimativa, cenários e contribuição mensal;
6. Desejos privados com cadeado, lista pessoal e sugestões que o outro pode escolher sem revelar a lista original;
7. detalhes de conta/cartão com fatura, parcelas e impacto futuro.

Use a casa "Lopes", membros James e Josi, período Setembro de 2026 e os dados de demonstração fornecidos no design document. Mostre estados de carregamento, vazio, sucesso, risco de caixa e validação de formulário.

Todas as entradas devem usar jornadas wizard com stepper visível e revisão final. Toda previsão deve explicar suas premissas. Toda área privada deve mostrar claramente o escopo de visibilidade.

Desktop: sidebar, canvas de 12 colunas, dashboard em cards assimétricos e bastante respiro. Mobile: barra inferior com Visão geral, Lançamentos, Adicionar, Projetos e Mais; wizard em tela cheia. Adicione transições suaves e respeite reduced motion.

Priorize hierarquia, legibilidade e sensação de confiança. O usuário deve entender em cinco segundos: quanto há disponível, o que vem pela frente e qual projeto está avançando.
```

## 15. Prompts de telas para refinar no Stitch

### Dashboard

```text
Refine a tela Visão geral para parecer um cockpit calmo da casa. O primeiro bloco deve responder quanto temos livre e se o mês está confortável. Em seguida mostre cash flow até o fim do mês, compromissos por data e projetos. Use composição assimétrica premium, cards glass apenas nos blocos importantes, dados plausíveis e CTA Adicionar lançamento.
```

### Projeções

```text
Refine Projeções como uma ferramenta de decisão, não como um relatório. Mostre realizado em linha sólida, previsto em linha pontilhada, intervalo provável em faixa suave e eventos financeiros como marcadores. Ao selecionar um mês, mostrar saldo final, principais entradas, principais saídas e a ação sugerida.
```

### Privacidade

```text
Refine Desejos privados com tom íntimo e seguro. A tela deve explicar que cada pessoa pode cadastrar desejos sem que a outra veja a lista original. Mostrar cadeado, estado protegido, grau de desejo, faixa de preço e uma área separada de sugestões autorizadas. Nunca exibir dados privados como placeholder ou tooltip.
```

## 16. Critério de aceite visual

O protótipo estará no caminho certo quando:

- parecer uma ferramenta da casa, não um app bancário;
- a cor lima aparecer como intenção e progresso, não como decoração;
- a projeção de caixa for legível sem abrir outra tela;
- o dashboard tiver uma narrativa de hoje, próximas semanas e futuro;
- o wizard tornar o registro de uma despesa simples e seguro;
- a privacidade de presentes estiver clara antes de qualquer interação;
- desktop e mobile preservarem a mesma personalidade.

## 17. Próxima etapa sugerida

Depois do primeiro protótipo no Stitch, validar apenas três jornadas antes de expandir: adicionar lançamento, entender a projeção do mês e criar um projeto. Essas três jornadas comprovam o núcleo do Economax e evitam investir cedo demais em telas periféricas.
