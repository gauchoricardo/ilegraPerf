"ilegraPerf" 

EXECUÇÃO:

Execução via JMETER
Esses são arquivos do JMETER. Gerados e utilizaveis através de interface grafica:
	TesteCarga.jmx
	TestePico.jmx

RELATÓRIO DOS TESTES. 
São arquivos separados para Carga e Pico e os resumos estão em CSV's:
	LogCarga.csv
	LogPico.csv
Com relação aos critérios de aceitação, ambos os testes podem ser considerados REPROVADOS pelos critérios de aceite.

CARGA: No teste de carga temos mais de 20% de erro principalmente por código 429 "Too Many Requests" (Muitas solicitações). 
Isso indica que o cliente excedeu o limite de solicitações definido pelo servidor dentro 
de um determinado período de tempo. Esse código de status é usado para controlar o fluxo de 
solicitações de um cliente para evitar sobrecarregar o servidor. Com tantos erros assim é possivel, porem, inutil avaliar o 90TH percentil. 
Poderiamos calcular o 90th percentil ou até mesmo uma media de tempo de 90% das requisições, mas obviamente, com essa quantidade de erros seria inutil.

PICO: No teste de pico, estipulei um teto de 5000 requests, por poucos segundos, já sabendo da fragilidade do sistema. 
E como eu previa, foram valores irrisórios. Estabeleci um tempo de ramp-up e nem disso passou.

Conclusão: Se tivessemos essa demanda de requests para um cenário real, precisariamos melhorar essas API's


OBS: Poderiamos refazer os testes com outra API se quiserem. 
Posso até criar algumas de exemplo localmente para demonstrar.