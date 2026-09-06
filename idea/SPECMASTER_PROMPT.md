# Prompt de inicialização do SpecMaster

Use este arquivo como prompt de entrada para iniciar o workflow completo do SpecMaster no Economax.

## Prompt

```text
Inicialize o workflow completo do SpecMaster para o projeto Economax, seguindo a sequência constitution -> specify -> clarify -> plan -> tasks -> analyze -> implement -> validate.

Leia primeiro e trate como fontes de verdade:

1. idea/context.md: ideia central e requisitos explícitos do produto;
2. idea/DESIGN.md: direção visual, arquitetura de informação, jornadas prioritárias, dados de demonstração e critérios visuais;
3. o código e os arquivos existentes no repositório: somente para descobrir fatos reais da base.

Não invente requisitos, integrações, regras de negócio, endpoints, modelos, SLAs, bibliotecas ou decisões de arquitetura que não estejam nas fontes. Classifique cada informação como EXPLICIT, INFERRED, DISCOVERED_FROM_CODEBASE ou UNRESOLVED. Tudo que for UNRESOLVED deve aparecer em Open Questions e ser levado para uma única rodada consolidada de clarify.

## Objetivo do produto

Construir uma ferramenta local de gestão financeira doméstica chamada Economax. Ela deve funcionar em rede local para James e Josi organizarem entradas, gastos, prejuízos, lucros, dívidas, cartões, financiamentos, despesas físicas, recorrências, previsibilidade e projetos de vida.

O produto deve responder três perguntas:

- O que está acontecendo com o dinheiro hoje?
- O que provavelmente acontecerá nos próximos meses?
- Qual plano de vida conseguimos realizar e quanto precisamos reservar?

## Escopo funcional explícito

1. Gestão financeira doméstica
   - registrar fontes de renda fixa, ocasional, bônus e renda extra;
   - registrar dívidas fixas e variáveis, gastos ocasionais, cartões, financiamentos e dívidas físicas;
   - acompanhar contas, categorias, recorrências e comprovantes;
   - permitir que os dois membros da casa registrem e consultem informações compartilhadas.

2. Projeções
   - mostrar previsibilidade para semanas, meses e anos;
   - exibir saldo realizado, saldo previsto, compromissos futuros e cenários;
   - explicar premissas das projeções e permitir ajustes.

3. Projetos financeiros
   - criar um projeto com nome, objetivo, prazo e target;
   - exemplo: Tokyo 2027;
   - decompor o target em estimativas, contribuições, prazo e progresso;
   - permitir uso futuro de LLM local para estimativas baseadas em contexto;
   - sempre deixar as premissas da estimativa editáveis e visíveis.

4. Projetos de aniversário e datas comemorativas
   - cada pessoa pode manter uma lista privada de desejos;
   - cada desejo possui item, grau de desejo, faixa de preço e prioridade;
   - a outra pessoa não pode acessar a lista original;
   - o sistema pode retornar somente sugestões autorizadas, ranqueadas por desejo e compatibilidade com orçamento;
   - o conteúdo privado deve ser criptografado de modo que nem um usuário com acesso de desenvolvimento consiga lê-lo diretamente.

5. Jornadas de entrada
   - todas as jornadas de input devem usar wizard com steps, revisão final e feedback de conclusão;
   - permitir imagem de comprovante quando aplicável;
   - apresentar validação, estados vazios, erro, sucesso e impacto da operação no mês.

## Direção de experiência e interface

Use idea/DESIGN.md como referência visual vinculante para o protótipo e como orientação de produto para as primeiras especificações.

O conceito é Calm Glass House: liquid glass com moderação, sensação premium e acolhedora, linguagem brasileira, confiança e privacidade. Evitar estética bancária genérica, planilha, ERP, cripto, roxo e excesso de neon.

A primeira experiência deve priorizar estas telas e jornadas:

1. onboarding da casa em wizard;
2. visão geral com saúde do mês, saldo livre, fluxo previsto, próximos compromissos, projetos e lançamentos;
3. adicionar lançamento em wizard com comprovante;
4. projeções em cenários base, conservador e projeto;
5. projeto Tokyo 2027;
6. desejos privados e sugestões de presentes;
7. detalhes de conta e cartão com parcelas e impacto futuro.

Use português do Brasil, moeda BRL e os dados de demonstração do DESIGN.md apenas como dados de protótipo, não como requisitos de domínio.

## Direção técnica explicitamente declarada

- frontend: React;
- backend: NestJS;
- persistência: MongoDB;
- cache de sessão: Redis;
- desenvolvimento local com Docker para infraestrutura;
- entrega planejada em Kubernetes local;
- disponibilização planejada via Service e VirtualService para rede local.

Não escolha bibliotecas, provedores, topologias, estratégias de autenticação ou contratos de API sem evidência no contexto, no código ou sem registrar a decisão como INFERRED/UNRESOLVED.

## Restrições de segurança e privacidade

- o produto é local e acessível pela rede local;
- dados financeiros devem ter separação clara entre visão compartilhada e visão pessoal;
- desejos e presentes são dados sensíveis e devem ser tratados como privados por padrão;
- qualquer proposta de criptografia, gerenciamento de chaves, recuperação ou autorização deve ser detalhada na especificação e encaminhada para clarify quando houver decisão de produto ou ameaça não definida;
- não afirmar que a privacidade está garantida apenas pela existência de uma tela de cadeado.

## Entregáveis esperados do workflow

1. constitution com princípios de produto, privacidade, qualidade e operação local;
2. especificação do MVP com critérios de aceitação rastreáveis;
3. perguntas de clarify agrupadas em uma única rodada;
4. plano técnico coerente com a stack declarada;
5. tarefas ordenadas por dependências, começando por um slice vertical pequeno e demonstrável;
6. análise obrigatória antes da implementação, reparando spec/plan/tasks quando necessário;
7. implementação somente de tarefas analisadas;
8. validação contra critérios de aceitação e gates detectados no repositório;
9. traceability ligando cada requisito explícito à especificação, plano, tarefas e testes;
10. relatório final com decisões, perguntas resolvidas, riscos, lacunas e próximos passos.

## Priorização inicial sugerida

Trate como hipótese inicial de MVP, sujeita a validação no workflow:

1. casa, membros e permissões básicas;
2. contas, categorias e lançamentos;
3. wizard de lançamento com comprovante;
4. dashboard do mês;
5. projeção de caixa de curto prazo;
6. projeto com meta, prazo e contribuições;
7. desejos privados e sugestões de presentes;
8. Open Finance, LLM local e Kubernetes de entrega como trilhas posteriores ou decisões a confirmar, salvo evidência contrária no repositório.

Não transforme esta priorização em compromisso irrevogável sem marcar a classificação e validar as dependências.

## Critérios de condução

- faça discovery read-only antes de alterar arquivos;
- se o Spec Kit não estiver inicializado, ofereça a inicialização conforme o protocolo;
- registre a estratégia Git uma única vez; este projeto está atualmente na branch master;
- não pule clarify, analyze ou validate;
- não implemente enquanto houver finding bloqueador ou SPEC_DRIFT;
- registre decisões de arquitetura e privacidade como decisões rastreáveis;
- ao final, entregue status SUCCESS, PARTIAL, BLOCKED ou FAILED conforme os gates reais, sem mascarar lacunas.
```

## Como iniciar

No diretório raiz do repositório, usar o equivalente da instalação local:

```text
$spec-master idea/SPECMASTER_PROMPT.md
```

Se a instalação estiver configurada como comando, também pode ser usado:

```text
/spec-master idea/SPECMASTER_PROMPT.md
```

O arquivo `idea/context.md` continua sendo a referência original da ideia. O `idea/DESIGN.md` concentra a direção visual e as decisões de experiência que devem acompanhar a especificação.
