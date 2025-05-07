# redundancia_Azure

Sobre o processo de criação de dados no Data Lake a partir de uma fonte externa, é importante observar algumas coisas:

1) Deve-se pensar sobre como os dados serão gravados no final: CSV, Parquet, Avro... para se definir a arquitetura a seguir
2) É necessário que o armazenamento (storage) já esteja configurado para o projeto. Deve-se criar três conteineres: bronze, silver e gold, relativo a fase de cópia (bronze), fase de transformação (silver) e por último a fase de consolidação (Gold) que nem sempre ocorrerá.
3) É necessário configurar o Linked Service para definir a origem (source) dos dados e seu destino.
4) Por último os Pipelines devem ser criados e serão estes os responsáveis pela extração, transformação e carga dos dados nos conteineres

É importante escolher o tipo de armazenamento mais adequado (escolher o menor possível que atenda os requisitos) e o tipo de processamento que atinja os resultados.
Observar os custos é tão importante quanto escolher bem uma arquitetura de trabalho que atenda ao projeto, ou o mesmo pode ser inviablizado.

A figura abaixo ajuda a dar uma noção geral do processo:

![image](https://github.com/user-attachments/assets/8c59665f-7784-4106-9b0c-9e7ef58d550a)
