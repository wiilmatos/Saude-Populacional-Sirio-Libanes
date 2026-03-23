# 📊 Desafio Técnico: Análise de Informações Gerenciais em Saúde (Foco BI)

**Autor:** Willian Matos | WM Analytics

## 🎯 Contexto e Objetivo
Este repositório contém a resolução do desafio técnico para a vaga de Analista de Informações Gerenciais em Saúde.  O objetivo principal do projeto é estruturar, organizar e analisar bases de dados (Cadastro Populacional e Histórico de Atendimentos) para apresentar uma visão clara sobre o perfil da população e o seu comportamento de utilização dos serviços de saúde.

## 🛠️ Stack Tecnológico e Arquitetura
Para garantir performance, escalabilidade e rigor analítico, a solução foi dividida em duas etapas principais:

* **Extração e Transformação (Python):** Utilizado para a limpeza dos dados, cruzamento das bases e, principalmente, para a definição estatística avançada do grupo de "High Users".
* **Modelagem e Visualização (Power BI):** Utilizado para a construção do modelo *Star Schema* (Fato e Dimensões), criação de medidas DAX e desenvolvimento do Dashboard interativo.

## 🧠 Metodologia: A Definição de "High Users"
O teste solicitava a identificação de pacientes "High Users" através de um critério lógico. Em vez de adotar um número arbitrário de consultas, a estratégia adotada foi baseada em **distribuição estatística**. 
Através do script em Python, foi calculada a média de atendimentos da carteira somada a dois desvios padrões ($\mu + 2\sigma$). Essa regra de negócio isolou cirurgicamente os verdadeiros *outliers* na ponta da curva de sinistralidade, evitando falsos positivos e garantindo precisão na análise de custos operacionais.

## 📂 Estrutura do Repositório
* `Tratamento_bases.ipynb`: Memória de Cálculo em Python. Contém todo o racional do ETL e o cálculo estatístico para a flag de High Users.
* `Saúde Populacional.pbix`: Arquivo do Power BI com o modelo de dados (relacionamentos), medidas DAX e as visões interativas (Demográfica e Operacional).
* `Insights Saúde Populacional.pdf`: Relatório final contendo as 3 principais descobertas de negócios extraídas dos dados e recomendações de ações táticas.
* `bases/`: Diretório contendo as bases de dados fictícias originais e os dicionários fornecidos.

## 💡 Principais Descobertas (Spoiler)
O cruzamento das bases revelou insights estratégicos para a operação, detalhados no arquivo PDF, incluindo:
1.  **Concentração de Risco:** Alta demanda no contrato corporativo "Monstros S.A." (faixa 41-50 anos).
2.  **Oportunidade Digital:** Forte volume de atendimentos de Fisioterapia Presencial, apontando espaço para migração de triagens para a Telemedicina.
3.  **Gargalo Operacional:** Pico atípico de uso da unidade Corvinal aos Domingos (16h).


*Nota de Governança:* Durante o ETL, foi identificada a ausência da variável "Gênero" na base original, gerando uma oportunidade de melhoria na captura de dados no onboarding.

---
*Para dúvidas ou aprofundamento sobre a modelagem técnica adotada, sinta-se à vontade para entrar em contato.*
