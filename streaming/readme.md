# Simulação de Pipeline: Ingestão e Processamento de Dados em Tempo Real

## Desafio Proposto

Nesta atividade, você deve implementar um pipeline completo de ingestão, processamento, armazenamento e visualização de dados em tempo real. O dataset utilizado será o Air Quality, e o fluxo de dados segue o padrão definido abaixo:

1. O Producer Kafka lê o dataset Air Quality e envia os dados para o tópico `sensor_raw`.
2. O Consumer Celery processa os dados recebidos:
   - Armazena em Redis como cache em tempo real.
   - Identifica alertas críticos (ex: CO > 10, NO2 > 200) e envia para o RabbitMQ.
   - Armazena os dados brutos e processados no MinIO.
3. O Streamlit lê os dados do Redis e exibe o status dos sensores em tempo real.
4. O MinIO mantém os dados históricos, funcionando como Data Lake.

Suba os contêineres do Kafka, Redis, RabbitMQ, Celery, Minio e Streamlit, garantindo que estejam se comunicando pela rede (ex: `mybridge`) e implemente o desafio!
