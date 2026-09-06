# Economex - Gestao economica domiciliar local


Preciso construir uma ferramenta de gestao financeira domestica local, onde consifo concentar a organizacao dos meus gastos, entradas, prejuizos, lucros, dividas, previsibilidade para os proximos meses, anos, etc.
O principio da ferramenta eh rodar local, em rede, onde eu e a josi conseguimos acessar e registrar nossos gastos e entradas, conseguimos registrar nossas dividas, cartoes, dividas fisicas, financiaemtos, etc.
A interface deve ser amigavel, construida sob a inspiracao maxima do conceito de liquid glass, com conceitos do admin panel moderno, responsivo e com animacoes de transicao e tudo mais.

Como principais features, vamos ter a gestao financeira, poderemos cadastrar fontes de renda, como tipo fixa, ocasional, bonus, renda extra. A partir disso criar dividas fixas e variaveis e gastos ocasionais. E quero tambem uma feature de projeto, por exemplo criar novo proejto (imagine tokio 2027), onde vamos definir um target e com isso podemos usar llms locais para realizar o valor estimado dependendo do contexto e gerar um target para nosso projeto.

Quero tambem a feature de projeto de aniversario/data comemorativa, onde podemos definir uma lista pre definida de presentes, onde eu nao tenho acesso a da josi nem ela a minha para poder planejar a compra de um presenta que eu ou ela espera, considerando nosso orcamento e tudo mais, e isso deve ser feito hankeado, ou seja, imagina a minha lista de desejos eh: megazord (grau 10), psp (grau 8) e nintendo 3ds (grau 7) ele deve retornar pra josi os presentes que ela pode escolher me dar de acordo com o grau de desejo, e isso deve ser possivel calibrar via cadastro e edicao do proprio desejo.
Quero que todas as jornadas de input sejam baseado em steps wizard, com direito a imagem de comprovante, e tudo mais, isso para todas as jornadas. Ah e detalhe, nem eu com acesso dev posso conseguir ver os presentes que a josi pensa em me dar, por isso eh importante criptografar com chave generica para eu nao conseguir ver nem se tentar.


O principio vai ser rodar local, com react, nestjs para backend, mongo para banco, redis pra cache de sessao. O principio vai ser rodar via kubernetes local, ou seja, devemos deixa-lo disponivel via kubernetes local, mas o seu desenvolvimento vai local, com docker subindo o que for de infraestrutura e somente na entrega vamos ter o deploy no kubenetes, disponibilizando virtual service e service para usar via rede local.