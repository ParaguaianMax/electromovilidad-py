# Lacunas de dados

## Atualizacao 02/10/2026

- **Setembro 2026**: a CADAM ainda nao publicou numeros do mes de setembro. A noticia mais recente (ABC Color, 24/09/2026) traz o acumulado ate agosto: 3.633 unidades eletrificadas, 14,7% de 24.700 unidades totais. O bot deve buscar novamente em outubro, quando o dado mensal de setembro deve sair.
- **Unidades mensais de setembro**: nao existem. A CADAM publica acumulados (janeiro-fevereiro, janeiro-maio, janeiro-junho, janeiro-agosto), nao o mes isolado.
- **Modelos em setembro**: nenhum dado paraguaio de setembro encontrado. Os numeros de modelos (BYD Dolphin Mini 495, etc.) que circulam na imprensa em 01/10/2026 referem-se a Argentina (ACARA), nao ao Paraguai — nao devem ser misturados.
- **Conflito maio vs junho vs agosto 2026 (nao resolvido)**: a propria CADAM, nota de 16/06/2026, afirma 5.877 unidades em janeiro-maio (+396,8% vs 1.183), HEV 50,0%, PHEV 33,4%, BEV 16,7%, sem unidades por segmento. ABC Color (13/08/2026) e Surtidores (14/08/2026), tambem citando CADAM, afirmam 4.098 em janeiro-junho. Acumulado de junho nao pode ser menor que o de maio se o universo for o mesmo. O 5.877 foi gravado em importaciones.csv com a fonte CADAM e a advertencia de conflito; nao foi descartado nem usado para calcular segmentos. O absoluto de agosto (3.633) e derivado de 14,7% x 24.700 e tambem fica abaixo do semestre.
- **Janeiro-fevereiro 2026 (CADAM 06/04/2026)**: HEV 514 (54,2%), PHEV 302 (31,9%), BEV 132 (13,9%), +138,8% vs o mesmo periodo de 2025. Total nao foi publicado; a soma 948 nao foi gravada. Lynk & Co lidera PHEV sem percentual.
- **Origem das marcas em 2025 (CADAM 27/01/2026), sem unidades**: PHEV China ~75%, Alemanha 11%, Reino Unido 8%. HEV Japao 66%, Coreia 17%, China 14%. BEV China ~50%, Suecia 18%, Japao 12%, Alemanha 10%, EUA ~6%.
- **Marcas 1S 2026 sem percentual**: Jetour e Chery citadas atras de BYD em PHEV (ABC 13/08/2026). Oferta citada: cerca de 50 marcas e mais de 200 modelos. Preco de entrada de eletricos compactos citado como US$ 12.000 a 15.000, sem modelo nomeado. SUV e picapes ~82% do importado geral, nao so do eletrificado.
- **Onibus**: 70 eletricos anunciados pelo MOPC para a area metropolitana (Ultima Hora; nota CADAM 15/06/2026). Nao e estatistica de importacao. Parte (30) foi doacao de Taiwan, chegada em fevereiro de 2026.
- **BYD Ti7 (Ultima Hora 02/10/2026, brand voice)**: lancamento PHEV local, sem preco nem unidades.

## Verificacao cruzada (02/10/2026)

- **CADAM vs imprensa**: fechamento 2025 (4.049; HEV 2.086 / PHEV 1.105 / BEV 858; 10,5%) e reproduzido por ABC, La Nacion, Forbes e Motorpy. O 1o semestre 2026 da ABC (4.098) e reproduzido por Surtidores. A nota CADAM de maio (5.877) e a excecao e conflita com o semestre. Ver arquivo `data/verificacao.csv` se existir.
- **CADAM vs OLACDE**: a OLACDE (Monitor, junho 2026, base ALADDA), citada pelo ABC em 06/07/2026, reporta 4.359 veiculos eletricos leves em circulacao no Paraguai em marco de 2026 e vendas de leves eletrificados de 434 no T1 2026 vs 469 no T1 2025 (-7%). O PDF da OLACDE define o parque regional como PHEV e BEV. Nao e comparavel diretamente com os 4.098 de importacao CADAM do semestre (que incluem HEV). A tabela nacional nao foi localizada no PDF; o 4.359 fica como fonte secundaria.
- **CADAM vs DNRA**: a DNRA nao publica emplacamentos por motorizacao. Nao ha como cruzar importacao vs emplacamento por eletrico/hibrido. A DNRA so tem totais por combustivel (gasolina, diesel, etc.) via portal interativo. Ultima Hora de 02/10/2026 trata de parque e combustiveis, sem quebra eletrica.
- **CADAM vs Aduana (dados abertos)**: a CADAM declara usar dados da Direcao Nacional de Aduanas (DNA). Os dados abertos da Aduana (dadosabertos.aduana.gov.py) tem despachos por NCM desde 1997, mas sem campo de motorizacao — hibrido/eletrico e inferido por NCM (8703.80 = BEV; 8703.60/8703.70 = hibridos) + marca. Nao foi possivel baixar e agregar automaticamente nesta rodada; o bot deve tentar no proximo ciclo.
- **Conclusao da verificacao**: a CADAM e a fonte primaria. Ha contradicao interna entre a nota CADAM de maio (5.877) e o semestre atribuido a CADAM pela ABC (4.098). O risco estrutural e que todas dependam da mesma base (DNA) e que comunicados sucessivos nao sejam reconciliados.

## O que NAO existe como dado publico

1. **Emplacamento por modelo**: a DNRA nao publica matriculas por modelo, so por marca/combustivel/tipo.
2. **Emplacamento mensal por motorizacao**: a DNRA publica totais por combustivel, mas sem serie mensal historica detalhada acessivel via portal.
3. **Motorizacao na Aduana**: despachos tem marca e NCM, mas nao campo eletrico/hibrido. Inferencia por NCM (8703.x) + marca.
4. **Preco de venda no Paraguai**: nao ha fonte oficial; estimativas vem de concessionarias/imprensa. Excecao desta passagem: lista oficial Jetour (jetour.com.py). BYD Ti7 e Sealion 7 sem preco.
5. **Parque circulante eletrico**: OLACDE estimou ~1.200 BEV em 2023; atualizacao citada de marco 2026: 4.359 leves (ABC/OLACDE), sem desagregar BEV e PHEV.
6. **Unidades absolutas por marca**: CADAM publica percentuais. Nao foram calculadas unidades a partir de percentuais arredondados.

## O que existe mas e esparso

- Modelos especificos: so via imprensa (ABC, HOY, MarketData, Forbes PY) ou site de marca. Unidades por modelo continuam raras (unico numero mantido: Volvo EX30, 127).
- Ranking de marcas: CADAM publica percentuais, nao unidades absolutas por marca (exceto quando imprensa cita).

## Proximos passos sugeridos

- Contatar CADAM diretamente para unidades absolutas por marca/modelo e para reconciliar 5.877 (maio) vs 4.098 (junho) vs 14,7% (agosto).
- Verificar se a DNRA tem API ou download em massa alem do portal de consulta.
- Cruzar NCM 8703.80 (eletricos) e 8703.60/8703.70 (hibridos) nos dados abertos da Aduana.
- Contatar OLACDE para serie historica de parque circulante eletrico no Paraguai.
- Repetir a busca em outubro pelo acumulado de setembro.
