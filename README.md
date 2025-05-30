O objetivo do projeto é criar, a partir dos relatórios do [Earth Negotiations Bulletin](https://enb.iisd.org/), um banco de dados descrevendo as interações conflitivas e cooperativas entre países no âmbito das negociações da UNFCCC. 
Parto do banco de dados [Relational Data between Parties to the UN Framework Convention on Climate Change](https://doi.org/10.7910/DVN/IVLEHB), de Paula Castro, que cobre as negociações entre 1995 e 2013. Uso as classificações das interações (variável _relation_) e os trechos dos textos que os anotadores indicaram como relevantes (variável _quote_) como base para treinar um classificador de interações, com o qual poderei expandir o banco de dados.

A execução do projeto é dividida nas seguintes etapas:

1. [Raspagem e limpeza dos relatórios do ENB](/scrape)
2. Treino dos classificadores
    1. [Preparo do banco de dados](/labeled_castro)
    2. Treino de um classificador de relevância, identificando quando um trecho do relatório diz respeito a uma interação entre países
    3. Treino de um classificador de tipo de relação, identificando quando a interação é cooperativa e conflitiva 
4. Aplicação do classificador ao conjunto completo de relatórios, resultando no banco de dados final
5. Avaliação dos resultados

## Estrutura do repositório
**/scrape**: código e resultado da coleta de dados no site do ENB. Atualmente, inclui eventos relacionados à UNFCCC entre 1995 e 2021.

**/labeled_castro**: tratamento do banco de dados de Castro para uso no classificador. Inclui também o script da avaliação e tentativa de construção de banco diretamente com os dados do ENB, usando estratégias de rule-based NLP.

**/classifier_relation**: treinamento e avaliação de classificadores para identificar tipo de relações entre países em textos como os do ENB
