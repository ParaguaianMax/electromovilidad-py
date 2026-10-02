# Electromovilidad Paraguay

Datos de importación y emplacamiento de vehículos eléctricos e híbridos en Paraguay.

## Fuentes

- **CADAM** (Cámara de Distribuidores de Automotores y Maquinarias): importaciones mensuales por segmento (HEV, PHEV, BEV) y ranking de marcas.
- **DNRA** (Dirección Nacional del Registro de Automotores, dnra.gov.py): estadísticas de inscripciones por tipo de vehículo, combustible, marca y localidad.
- **Aduana** (datosabiertos.aduana.gov.py): despachos de importación desde 1997, con marca y posición arancelaria.

## Archivos

- `data/importaciones.csv` — importaciones mensuales por segmento y marca.
- `data/emplacamientos.csv` — matriculaciones nuevas por combustible/marca (cuando disponible).
- `data/modelos.csv` — lista de modelos identificados por segmento, con origen y categoría.
- `data/lacunas.md` — registro de lo que no se pudo obtener de forma automática.

## Metodología

1. Importación: números de la CADAM (mensual/acumulado anual).
2. Emplacamiento: portal de estadísticas de la DNRA filtrado por combustible (eléctrico/híbrido) y marca.
3. Modelos: cruce de imprensa + ranking CADAM + datos de aduana por NCM.
4. Categorización: tamaño (pequeño/medio/grande), tipo de carrocería (SUV/sedán/pickup), precio estimado.

## Actualización

Automação mensual (día 10, 08:00, America/Asuncion) que busca datos novos e atualiza os CSVs.

## Lacunas conhecidas

- A DNRA não publica série histórica mensal de emplacamentos por motorização; só totais por combustível.
- A Aduana não tem campo de motorização; híbrido/elétrico é inferido por NCM + marca.
- Modelos específicos vêm de imprensa, não de fonte oficial.
