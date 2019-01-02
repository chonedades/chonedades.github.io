---
use_math: true
layout: post
title: Confissão de Viadage
---

_This blog post has a somewhat different target public: instead of focusing on the Machine Learning practician, it targets the Cognitive Science student who often uses Regression in his everyday statistics without understanding well how it works. Of course, there is a lot more to say than what is written here, but hopefully it will be a good basis upon which to build._

The
[Psycholinguistics group of the University of Kaiserslautern](https://www.sowi.uni-kl.de/psycholinguistics/home/),
where I am currently a PhD student, offered a course on Computational
Linguistics this last Summer Semester, where I had the opportunity
to give three classes. I ended up writing a lot of material on Linear Regression
(and some other stuff) that I believe would be beneficial not only for the
students of the class, but for anyone else interested in the topic. So, well,
this is the idea of this blog post...

In the class, we used Python to (try to) make things more "palpable" to the
students. I intend to do the exact same here. In fact, I am using
`jupyter notebook` for the first time along with this blog (if you are reading
this published, it is because it all went well). My goal with the Python codes
below is to make the ideas implementable also by the interested reader. If you
can't read Python, you should still be able to understand what is going on by
just ignoring (most of) the code. Notice that most of the code blocks is
organized in two parts: (1) the part that has code, which is normally colorful,
highlighting the important Python words; and (2) the part that has the output,
which is normally just grey. Sometimes the code will also output an image
(which is actually the interesting thing to look at).

Still... for those interested in the Python, the following code loads the
libraries I am using throughout this blog post:








Começarei o texto já enunciando o que o título clarifica: isso mesmo, sou viado. Não vou usar o eufemismo “homossexual”, nem o politicamente correto (e, portanto, pelo menos rejeitável da minha parte) “gay”. Não vou fazer mil e uma voltas para dizer que “tenho interesse de natureza sexual por homens”, ou tentar contar uma história que deixe o meu ponto implícito. Não. Eu sou viado mesmo. Bixa, boiola, marica, baitola, morde-fronha. Infelizmente, parece que eu tenho que me justificar por isso... e esse texto tem o objetivo de esclarecer um conjunto de pseudo-implicações que o fato declarado no título levanta. Essas pseudo-implicações são o fruto de preconceitos inclusive freqüentemente inconscientes na mente das pessoas à minha volta. Esse texto contém histórias não-fictícias. Nele, eu enfatizo causos que tentam demonstrar alguns desses preconceitos. Talvez ele “me exponha”, ou mesmo “exponha” gente à minha volta; mas eu o julgo necessário, e o escrevo na esperança de que pelo menos alguns entre os que eu conheço o leiam e compreendam.
Antes de seguir em frente, eu quero contrapôr uma idéia que de tempos em tempos eu volto a escutar de alguém diferente, como se isso fosse convincente às mentes em geral ou contivesse alguma verdade (de fato, não contém): a de que “ninguém precisa saber a minha orientação sexual”. Se eu fosse hétero e a minha orientação sexual pudesse ser assumida pelos outros de forma confiável, então certamente eu não precisaria dizê-la para ninguém: o mundo seguiria funcionando da forma como ele sempre funcionou. Mas para o viado, as coisas não funcionam de forma tão tranqüila. Como todo ser humano, eu também quero encontrar um par, um alguém com quem eu possa passar o resto da minha vida. Nesse par eu procuro basicamente um homem, mais ou menos similarmente ao que uma mulher busca em um homem. Homens héteros, porém, estão aí, a miúdos, livres, em todo lugar, disponíveis, fáceis de encontrar. Um homem gay, por outro lado, precisa ser amostrado de uma população que, além de limitada, se faz secreta, justamente por medo, e por idealizações como a que eu me propus a contrapôr nesse parágrafo. Assim, para que eu descubra se um certo homem faz parte da minha população (ou seja, é viado), eu tenho de realmente perguntar a ele se ele é viado. Mas a sociedade é tal que, caso ele seja hétero, fazê-lo conta como uma afronta a sua masculinidade (mais sobre isso abaixo), uma ofensa, e requer uma resposta à altura da ofensa. Essa resposta tem frequentemente o perigo de ser a violência (especialmente se eu não conheço a pessoa). Com medo de perguntar, fica complicado descobrir quem está na minha população. É claro, porém, que toda essa história depende de mais uma premissa que foi deixada implícita até agora: a de que eu esteja disposto a que descubram que eu sou viado. Mas isso tampouco é verdade para uma grande porção dos homossexuais. Tome-se o meu exemplo: somente aos 28 anos estou saindo do armário publicamente (apesar de já haver saído para uma grande parte das pessoas com quem eu convivo anteriormente). Quando essa premissa é satisfeita, algumas coisas ficam um pouco mais fáceis (com sorte, alguém que saiba que eu sou viado não se sentiria com medo de me abordar)… e é isso que eu estou fazendo através desse texto.
Eu já até consigo enxergar algumas pessoas comentando: “sabe o John, filho da Lurdinha, dos gêmeos, irmão do Jean?”, “sei…”, “virou viado”. As pessoas parece que saem do seu caminho natural só para falar desse tipo de coisa. Só para mencionar sobre alguém que foi “descoberto” viado. Alguém poderia pensar que o fenômeno é exclusivo das camadas sociais menos avantajadas da sociedade, esperadamente menos educadas. Lamentavelmente, não é o caso: ainda hoje lembro de um almoço com alguns colegas da UFRGS (supostamente a instituição de ensino onde estudam os melhores alunos do estado) em que um colega, tendo descoberto através do orkut que um professor era homossexual, levantou o assunto na mesa. A resposta de um outro ainda quase se escuta na minha mente: “perdi o respeito agora”.
Por causa desse tipo de comentário, eu tive por muito tempo extremo medo de falar às pessoas sobre isso (é verdade, porém, que, em paralelo, existia uma motivação religiosa -- vide abaixo). De fato, eu sempre tomei muito cuidado para não “me denunciar”, e naturalmente construí um conjunto de rituais que me pareciam garantir certa segurança (mais sobre isso abaixo). Dos poucos a quem eu me assumi, eu frequentemente (mas é verdade que nem sempre) escutei um conjunto de clichês que viriam a repetir-se incansavelmente advindos de todos os que, não compreendendo completamente a situação, já tinham uma opinião formada: (i) que eu nunca tinha tentado com uma mulher, e, portanto, se eu tentasse eu ía ver que não tinha como não querer; ou a variante (ii) que eu não tinha como saber se eu não gostava, se eu nunca tinha tentado com uma mulher; ou ainda (iii) que não é natural: que o certo é homem com mulher (e similares, do tipo “se todo mundo for assim, a nossa espécie vai terminar”, ou a versão mais branda “isso é claramente deletério do ponto de vista evolucionário”). Essas respostas sempre foram problemáticas, e mais me atrapalharam do que ajudaram: dizer às pessoas tinha sempre o potencial de me fazer entrar numa discussão que só me faria me sentir pior, em que as pessoas me diriam que eu estaria “errado”, que eu queria algo “ruim”. Houve gente que chegou a comparar homossexualismo com pedofilia! (e ainda há, infelizmente.)
Já hoje em dia eu espero um outro motif, pelo menos advindo de um conjunto menos esclarecido de pessoas à minha volta: que o motivo pelo qual eu “virei viado” é que eu fui viver na Europa. É que na Europa eu teria virado fresco, porque por lá todo mundo é cheio de fru-fru. E, afinal, já que todo fresco é viado, então eu devo ter virado viado -- como se, de repente, a “frescura” tivesse feito com que eu passasse magicamente a me sentir atraído por homens. Enquanto eu não espero essas idéias de todo mundo, elas explicitam aí uma pressuposição problemática que sim se observa na mente de uma maioria: a infeliz associação entre femininidade e homossexualismo. Até agora, relacionada a esse assunto, a experiência mais marcante que eu tive foi quando eu disse à minha cunhada que eu sou viado: na discussão subsequente, ela passou a me chamar de “amiga”, como se eu de repente tivesse trocado de gênero, como se a minha identidade não fosse mais a mesma, como se ser viado me pudesse na categoria “mulher”. Ironicamente, enquanto homossexual, eu de facto provavelmente seja muito mais “macho” do que um conjunto considerável de héteros com que eu tive a oportunidade de conviver[^footnote1].


[^footnote1]: Essa afirmação, porém, é problemática, porque não explicita que conjunto é esse, e não define o que ser “macho” significa; uma versão mais branda dela poderia ser afirmar que todo mundo conhece alguns héteros um pouco mais “femininos” que eu, assumindo que “feminino” seja realmente o oposto de “macho” -- uma suposição que eu to disposto a aceitar.

faewfawefwea
