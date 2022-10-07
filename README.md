# fundamentos-trabalho
Repositório com o trabalho da disciplina "Fundamentos e ética em jornalismo de dados" do Master em jornalismo de dados, automação e data storytelling do Insper

O grupo é integrado por Ananda, José, Luana, Luize e Thaís. 

As bases de dados utilizadas neste trabalho são fornecidas pelo Instituto Brasileiro de Geografia e Estatística (IBGE), como parte da Pesquisa Nacional por Amostra de Domicílios Contínua Trimestral (PNADC/T). A amostragem traz indicadores trimestrais sobre a força de trabalho brasileiras divididas por variáveis básicas para se entender a evolução desse setor como rendimento médio, número de desempregagos, cor, sexo, ocupação entre outras. As amostragens foram atualizadas pelo IBGE no dia 12 de agosto deste ano. Dos diferentes indicadores fornecidos pela pesquisa o grupo escolheu duas bases: 

A primeira base utilizada (6405) diz respeito ao rendimento médio real, habitualmente recebido por mês e efetivamente recebido no mês de referência, do trabalho principal e de todos os trabalhos, por cor ou raça. Os valores estão expressos em reais (R$). 

A segunda (6406) trata da média de horas habitualmente trabalhadas por semana e efetivamente trabalhadas na semana de referência, no trabalho principal e em todos os trabalhos, das pessoas de 14 anos ou mais de idade, por cor ou raça. Os valores estão expressos em horas. 

Uma das limitações encontradas era a falta de cruzamento entre raça e gênero, apesar da pesquisa fornecer as duas informações ambas não estavam com variáveis em comum, o que impossibilitou que se conseguisse afunilar os dados a partir de grupos sociais como mulheres negros, mulheres brancas, homens negros e homens brancos. 

Ao cruzar os dados disponíveis, o grupo buscou entender a diferença do valor médio pago por hora ao trabalhador brasileiro de acordo com sua cor ou raça. Para uma análise de evolução, selecionamos dados do segundo trimestre de 2012 e comparamos aos do segundo trimestre de 2014, 2018 e 2022, os últimos divulgados pelo IBGE. Os anos escolhidos marcam o fim do primeiro governo Dilma e o de Michel Temer, que aprovou em seu mandato uma reforma trabalhista.  
A tabela de valor por hora

Por se tratarem de bases de dados organizadas e com poucas linhas, optamos por trabalhá-la na ferramenta Spreedsheet, do Google. Começamos pelos dados de 2022.

Mantivemos as colunas “Cód”, “Brasil e Unidade da Federação”, “Total”, “Branca”, “Preta” e “Parda” de ambas, que contêm os dados necessários para a análise. 

Para facilitar o entendimento, rebatizamos as colunas:

Na tabela de rendimentos
Brasil e Unidade da Federação = Local
Total = Rend. total
Branca = Rend. brancos
Preta = Rend. pretos
Parda = Rend. pardos

Na tabela de horas
Brasil e Unidade da Federação = Local
Total = Horas total
Branca = Horas brancos
Preta = Horas pretos
Parda = Horas pardos

Utilizamos a função de PROCV (VLOOKUP), tendo como chave a coluna Cód., para inserir os dados de rendimento na planilha de horas. 

A ordem, neste passo, faria pouca diferença. 

Reorganizamos a tabela, para que as colunas de horas fossem seguidas pelas dos rendimentos de cada recorte. 

Depois, inserimos colunas novas à direita das colunas de rendimento para o cálculo de valor de hora, que seguiu a lógica de:

Rendimento/(Horas*4,3). 

Multiplicamos a coluna horas por 4,3 (média de semanas em um mês) para obter a média de horas trabalhadas por mês em cada recorte.

Essas quatro novas colunas foram nomeadas “Valor total”, “Valor brancos”, “Valor pretos” e “Valor pardos”.
Análise
Uma rápida visualização dos dados mostrou que brancos ganham proporcionalmente mais do que pretos e pardos por hora trabalhada.

Para quantificar, inserimos dois conjuntos com três colunas:

BRA_PRE = Diferença do valor da hora trabalhada por brancos e pretos, expressa em reais (R$)
BRA_PAR = Diferença do valor da hora trabalhada por brancos e pardos, expressa em reais (R$)
PRE_PAR = Diferença do valor da hora trabalhada por pretos e pardos , expressa em reais (R$)

BRA_PRE% = Diferença percentual da hora trabalhada por brancos e pretos
BRA_PAR% = Diferença percentual da hora trabalhada por brancos e pardos
PRE_PAR% = Diferença percentual da hora trabalhada por pretos e pardos

Na sequência, repetimos esse processo de cruzamento, organização e criação de colunas com os números do segundo trimestre de 2012, 2014 e 2018 para obter um comparativo de 10 anos. 

Em uma terceira tabela, batizada de “evolucao”, colocamos lado a tabela a diferença percentual em cada recorte e ano. Inserimos colunas com o cálculo de diferença em pontos percentuais.

BRA_PRE12 = Diferença em % entre a hora de brancos e pretos em 2012
BRA_PRE22 = Diferença em % entre a hora de brancos e pretos em 2022
EVO_BRA_PRE = Aumento ou redução (em pontos percentuais) da diferença percentual entre o valor pago pela hora trabalhada por brancos e pretos, entre 2012 e 2022

BRA_PAR12 = Diferença em % entre a hora de brancos e pardos em 2012
BRA_PAR22 = Diferença em % entre a hora de brancos e pretos em 2022
EVO_BRA_PAR = Aumento ou redução (em pontos percentuais) da diferença percentual entre o valor pago pela hora trabalhada por brancos e pardos, entre 2012 e 2022

PRE_PAR12 = Diferença em % entre a hora de pretos e pardos em 2012
PRE_PAR22 = Diferença em % entre a hora de pretos e pardos em 2022
EVO_PRE_PAR = Aumento ou redução (em pontos percentuais) da diferença percentual entre o valor pago pela hora trabalhada por pretos e pardos, entre 2012 e 2022

Os resultados podem ser conferidos aqui.

Ciclo vicioso 

A hora de trabalhado do brasileiro nunca valeu tão pouco, em dez anos, a remuneração dos assalariados do país diminuiu apesar das alterações na legislação trabalhista. 

Nos últimos dez anos, o valor da hora de trabalho voltou ao patamar de 2012, uma lógica de remuneração em que, independente do ano de amostragem, apenas a população branca continua recebendo uma acima da média nacional. Em 2012, a média paga para um trabalhador brasiliero era de R$16,05 mas, se o trabalhador fosse branco a margem mudava para R$20,20 enquanto, enquanto isso, assalariados pretos e pardos recebiam menos de R$ 12 reais por hora trabalhada. Apesar do boom de aumento que ocorreu em 2014, quando a média salarial chegou próximo ao dobro de 2012, os anos seguintes continuaram repetindo a lógica de baixa remuneração salarial no país, em especial para população negra. 


A tabela de ocupados e desocupados
A fim de entender se a disparidade entre raças se estende também para a população desocupada, baixamos a planilha de 6402 - Pessoas de 14 anos ou mais de idade, total, na força de trabalho, ocupadas, desocupadas, fora da força de trabalho, e respectivas taxas e níveis, por cor ou raça.

Dentro dela, selecionamos três tabelas: Pessoas na força de trabalho, Pessoas ocupadas e Pessoas desocupadas. Na busca por trimestre, selecionamos os 2º trimestres de 2012 e 2022. 

Mantivemos as colunas “Brasil e Unidade da federação”, “Total”, “Branca”, “Preta” e “Parda”.

Para a análise, juntamos as tabelas de Força de Trabalho e Pessoas desocupadas, usando a coluna Local como chave. Então, criamos três novas colunas:

%_desocupada/força_branca_2022: divisão da coluna  Branca_desocupada_2022 pela Branca_força_2022
%_desocupada/força_preta_2022: divisão da coluna  Preta_desocupada_2022 pela  Preta_força_2022
%_desocupada/força_parda_2022: divisão da coluna  Parda_desocupada_2022 pela  Parda_força_2022

Repetimos o processo para os dados de 2012, criando as seguintes colunas:
%_desocupada/força_branca_2012
%_desocupada/força_preta_2012
%_desocupada/força_parda_2012


Os resultados podem ser conferidos aqui

Análise

Por meio da análise da tabela “Pessoas desocupadas”, vemos que, em números absolutos, os pardos têm o maior contingente de desocupados nos dois anos de comparação.

Já pelo cruzamento das tabelas “Pessoas da força de trabalho” e “Pessoas desocupadas” referentes a 2022, percebemos que, proporcionalmente à força de trabalho, a população preta é a que tem mais desocupados (11,29%), seguida da parda (10,80%) e da branca (7,31%).

Com os dados de 2012, a ordem se repetiu, apenas de os índices de desocupação terem sido menores para todas as categorias: preta (9,65%), parda (8,76%) e branca (6,20%). A partir desses dados, vemos que a proporção de pessoas desempregadas aumentou nos últimos 10 anos, e que ela continuou pior para pessoas pretas e pardas.

Perguntas que fizemos à base

Quanto vale a hora de um trabalhador brasileiro e em cada Estado? 
Quanto vale a hora de um trabalhador brasileiro e em cada Estado por raça?
Brancos ganham mais do que pretos e pardos? Em quantos e quais Estados?
Em qual Estado a diferença é maior ou menor por raça?
Pardos ganham mais do que pretos? Em quantos e quais Estados?
Nos Estados em que brancos ganham mais, a taxa de subutilização/desocupação é mais comum entre pretos e pardos do que entre brancos?
Qual a comparação entre a hora de trabalho no segundo trimestre de 2022 e o mesmo período de 2012? Houve evolução na década?
Algumas respostas
Hoje, a hora do trabalhador brasileiro vale em média R$ 12,40. Brancos ganham R$ 15,75 por hora; pretos, R$ 9,93; e pardos, R$ 10,50;
Brancos ganham consideravelmente mais do que pretos e pardos em todos os Estados e em ambos os períodos analisados;
Atualmente, a diferença no valor da hora trabalhada por brancos e pretos é maior no Distrito Federal, onde pretos recebem 51,1% a menos, e menor em Pernambuco, onde pretos ganham 19,4% a menos;
No caso dos pardos, a maior discrepância ocorre no Rio de Janeiro, onde eles ganham 42,1% a menos que os brancos. A menor diferença é observada em Rondônia (14,8% a menos);
Pardos ganham mais do que pretos na média brasileira e de 20 Estados, e recebem menos no Acre, Amazonas, Paraíba, Paraná, Pernambuco, Piauí e Sergipe;
Em 10 anos, de governos mais à esquerda e mais à direita, a diferença salarial entre brancos e negros (pretos e pardos) pouco diminuiu;
Na média brasileira, houve uma redução de 2,6 pontos percentuais no abismo entre brancos e pretos. Entre brancos e pardos, uma queda de 2,7 ponto percentual. Entre pretos e pardos, o índice ficou praticamente estável, com uma retração de 0,1 ponto percentual.
Além da remuneração, pretos e pardos também têm piores índices de ocupação. Na média do país, os pretos têm a maior porcentagem de desocupação em relação à força de trabalho. E, ao longo das décadas, o cenário só piorou. Em 2012, a desocupação entre pretos era de 9,65%. Em 2022, saltou para 11,29%.
Numericamente, os pardos representam mais da metade (50,9%) do total de desocupados do país. Em 2012, a parcela era praticamente a mesma (50,7%).




