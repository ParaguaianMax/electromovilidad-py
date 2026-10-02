# Lacunas de dados

## Atualização 02/10/2026

- **Setembro 2026**: a CADAM ainda não publicou números do mês de setembro. A notícia mais recente (ABC Color, 24/09/2026) traz o acumulado até agosto: 3.633 unidades eletrificadas, 14,7% de 24.700 unidades totais. O bot deve buscar novamente em outubro, quando o dado mensal de setembro deve sair.
- **Unidades mensais de setembro**: não existem. A CADAM publica acumulados (janeiro-junho, janeiro-agosto), não o mês isolado.
- **Modelos em setembro**: nenhum dado paraguaio de setembro encontrado. Os números de modelos (BYD Dolphin Mini 495, etc.) que circulam na imprensa em 01/10/2026 referem-se à Argentina (ACARA), não ao Paraguai — não devem ser misturados.

## Verificação cruzada (02/10/2026)

- **CADAM vs imprensa**: os números da CADAM (4.049 em 2025; 4.098 no 1º semestre 2026; 3.633 até agosto 2026) são reproduzidos fielmente por ABC Color, Surtidores LATAM, MarketData, Forbes e La Nación. Diferença: 0%. Ver arquivo `data/verificacao.csv`.
- **CADAM vs OLACDE**: a OLACDE (Monitor de Mobilidade Elétrica, junho 2026) reporta 4.359 veículos elétricos leves em circulação no Paraguai em março de 2026. Isso é parque circulante (BEV), não importação — não é comparável diretamente com os 4.098 do 1º semestre. A OLACDE não publica série de importações por país.
- **CADAM vs DNRA**: a DNRA não publica emplacamentos por motorização. Não há como cruzar importação vs emplacamento por elétrico/híbrido. A DNRA só tem totais por combustível (gasolina, diésel, etc.) via portal interativo.
- **CADAM vs Aduana (dados abertos)**: a CADAM declara usar dados da Direção Nacional de Aduanas (DNA). Os dados abertos da Aduana (dadosabertos.aduana.gov.py) têm despachos por NCM desde 1997, mas sem campo de motorização — híbrido/elétrico é inferido por NCM (8703.80 = BEV; 8703.60/8703.70 = híbridos) + marca. Não foi possível baixar e agregar automaticamente nesta rodada; o bot deve tentar no próximo ciclo.
- **Conclusão da verificação**: a CADAM é a fonte primária e as demais a reproduzem. Não há fonte independente que contradiga os números. O risco é que todas dependam da mesma base (DNA).

## O que NÃO existe como dado público

1. **Emplacamento por modelo**: a DNRA não publica matrículas por modelo, só por marca/combustível/tipo.
2. **Emplacamento mensal por motorização**: a DNRA publica totais por combustível, mas sem série mensal histórica detalhada acessível via portal.
3. **Motorização na Aduana**: despachos têm marca e NCM, mas não campo elétrico/híbrido. Inferência por NCM (8703.x) + marca.
4. **Preço de venda no Paraguai**: não há fonte oficial; estimativas vêm de concessionárias/imprensa.
5. **Parque circulante elétrico**: OLACDE estimou ~1.200 BEV em 2023; atualização de março 2026: 4.359 BEV leves (OLACDE).

## O que existe mas é esparso

- Modelos específicos: só via imprensa (ABC, HOY, MarketData, Forbes PY).
- Ranking de marcas: CADAM publica percentuais, não unidades absolutas por marca (exceto quando imprensa cita).

## Próximos passos sugeridos

- Contatar CADAM diretamente para unidades absolutas por marca/modelo.
- Verificar se a DNRA tem API ou download em massa além do portal de consulta.
- Cruzar NCM 8703.80 (elétricos) e 8703.60/8703.70 (híbridos) nos dados abertos da Aduana.
- Contatar OLACDE para série histórica de parque circulante elétrico no Paraguai.
