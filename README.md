# Estudo de Caso 1: Cyclistic

## Cenário

Você é um analista de dados júnior que trabalha na equipe de analistas de marketing da Cyclistic, uma empresa de compartilhamento de bicicletas em Chicago. O diretor de marketing acredita que o sucesso futuro da empresa depende da maximização do número de planos anuais contratados. Portanto, sua equipe quer entender como os ciclistas casuais e os membros anuais usam as bicicletas da Cyclistic de forma diferente. A partir desses insights, sua equipe criará uma nova estratégia de marketing para converter passageiros casuais em membros anuais. Mas, primeiro, os executivos da Cyclistic devem aprovar suas recomendações que, portanto, devem ser apoiadas com insights de dados convincentes e visualizações de dados profissionais.

  
__Ideia motivadora__: Aumentar o número de contratações do plano anual entre os membros da Cyclistic

#### Três perguntas nortearão o futuro programa de marketing:

-  Como os membros anuais e os ciclistas casuais usam as bicicletas da Cyclistic de forma diferente?
- Por que os passageiros casuais iriam querer adquirir planos anuais da Cyclistic?
- Como a Cyclistic pode usar a mídia digital para influenciar os passageiros casuais a se tornarem membros? A Lily lhe apresentou a primeira pergunta a ser respondida: Como os membros anuais e os ciclistas casuais usam as bicicletas da Cyclistic de forma diferente?
## Preparação: obtendo o dataset

Etapa para obter e ter o primeiro contato com os dados, durante esta fase foi realizada o agrupamento dos dados em um único conjunto de dados utilizando script em Python, reunindo os dados de todo o ano de 2023.  Este dataset contém mais de 5 milhões de linhas correspondentes a aluguéis realizados durante o ano, com informações sobre o 

- ID do aluguel
- Tipo de bike
- Data e hora de início da corrida
- Data e hora de fim da corrida
- ID estação de início da corrida
- Nome da estação de início
- ID estação de fim da corrida
- Nome da estação de fim
- Latitude e longitude da estação de inicio e fim do passeio
- Tipo de cliente que realizou a corrida (anual ou casual)


Dados disponíveis em: https://divvy-tripdata.s3.amazonaws.com/index.html

__Observação__: os conjuntos de dados têm um nome diferente porque a Cyclistic é uma empresa fictícia. Para os propósitos deste estudo de caso, os conjuntos de dados são adequados e permitem responder às perguntas de negócios. Os dados foram disponibilizados pela _Motivate International Inc_.  

As colunas com as __latitudes__ e __longitudes__ das estações de inicio e fim de cada aluguel foram dispensadas da análise.

## Processamento

Etapa de manipulação e limpeza dos dados. A partir dos dados de inicio e fim dos aluguéis foi criada uma coluna com a duração de cada aluguel que norteou grande parte da limpeza dos dados. Além disso, foi realizada uma verificação para encontrar inconsistências no dataset, como:

- ID de aluguel duplicado (Não foi encontrado nenhuma ocorrência)
- Inconsistência na duração de alugueis (Duração negativa, indicando erro nas datas de inicio e fim da corrida)
- Corridas com tempo de duração desprezíveis (menores ou iguais a 1 minuto)

Também foi feito o ordenamento pelas datas de inicio do aluguel e não pelas IDs (como estava anteriormente)

Ademais, a criação de colunas contendo o número de __dias, horas, minutos e dia da semana__ também foi efetuado, visando facilitar o processo de análise. 

Ao final foi exportado um arquivo `.csv` contendo os dados limpos e manipulados.

## Análise e Visualização dos Dados

O processo de análise dos dados foi orientado pelas perguntas propostas pela equipe de Marketing da _Cyclistic_ que gostaria de entender o perfil de uso entre os clientes anuais e casuais. 

 -- GRAFICO DA SÉRIE TEMPORAL DOS ALGUEIS NO ANO -- 

Ao compararmos o número de aluguéis entre os tipos de clientes ao longo dos dias da semana tempos o seguinte a distribuição: 


-- GRAFICO DA DISTRIBUICAO DE ALGUEIS DURANTE A SEMANA -- 

A partir do histograma é possível observar que clientes casuais tem suas maiores concentrações de alugueis nos finais de semana (Sexta, Sábado e Domingo). Já os membros anuais, também tem uma grande concentração de uso no Sábado, porém tem um perfil de uso maior durante os dias úteis e o menor índice no Domingo.


Considerando o tempo médio de uso das bicicletas entre cada grupo, temos: 

Para aluguéis menores que 1 dia

-- TABELA COM OS MINUTOS --

Já para aluguéis maiores que 1 dia

-- TABELA COM OS DIAS MEDIO DE USO -- 

A partir dessas métricas fica evidente que o uso médio entre os usuários usuais é maior que se comparado ao uso de usuários anuais. O que pode indicar interesse por essa parcela dos clientes a virarem membros fidelizados. 


### Analisando os tipos de bicicletas 

No que se refere ao tipo de bicicleta alugada por consumidores casuais, as bicicletas elétricas aparecem na liderança com 53%, seguidas da bicicleta convencional com 43.1%. Há também uma pequena parcela que utiliza as bicicletas compartilhadas (docked bikes), cerca de 3.9%

-- GRAFICO DE SETORES CASUAL -- 

Neste quesito, existe uma diferença em relação aos usuários anuais, pois entre estes clientes a taxa de aluguel é praticamente a mesma, com uma leve vantagem para bicicletas convencionais.

-- GRAFICO DE SETORES MEMBROS --

### Alugueis entre meses do ano

Olhando para o número de passeios realizados entre os meses do ano, os meses que compreendem a estação do Verão (Hemisfério Norte) são onde ocorrem os maiores índices de aluguéis. É interessante notar que os dados mostram uma crescente pré (Primavera) e uma baixa pós (Outono) o verão, até chegar no período do Inverno onde ocorre uma baixa procura por passeios de bicicletas entre ambos os grupos. 

# Conclusão 

Buscando aumentar a adesão de clientes anuais, é interessante movimentar campanhas de marketing nos meses que compreendem a Primavera e o Verão, tendo em vista que há uma crescente para ambos os grupos analisados. Também é apropriado buscar o público de usuários casuais que alugam bicicletas em períodos maiores que um dia, pois aparentam ter interesse na utilização do sistema da Cyclistic.  Por fim, campanhas de marketing próximas aos fins de semanas aparentam ser promissoras para conversão de novos clientes anuais, tendo em vista que é onde ocorrem os picos de passeios entre usuários casuais. 