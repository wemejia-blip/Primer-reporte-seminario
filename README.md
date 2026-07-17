# Bootstrap en Regresión Lineal — Peso Vehicular vs Consumo (Auto MPG)

Scripts en R que compara y análiza los resultados MCO vs Bootstrap por pares, y exploran empiricamente la estabilidad asintótica del Bootstrap (Bickel & Freedman, 1981).

## Contenido

**01_simulaciones.R**
- 01.1 Simulación con supuestos clásicos cumplidos (n=50, B=1000)
- 01.2 Simulación con heterocedasticidad (n=50, B=1000)

**02_prueba_supuestos.R**
- 02.1 Exploración Auto MPG (mpg vs weight)
- 02.2 Caso 1: log(mpg) ~ weight — Shapiro-Wilk y Breusch-Pagan
- 02.3 Caso 2: mpg ~ log(weight) — Shapiro-Wilk y Breusch-Pagan

**03_bootstrap_auto_mpg.R**
- 03.1 Bootstrap Caso 1: log(mpg) ~ weight
- 03.2 Bootstrap Caso 2: mpg ~ log(weight)
- 03.3 Evaluación predictiva (partición 70/30: RMSE, MAE, R²)

**04_estabilidad_asintotica.R**
- 04.1 Distancia KS — población simulada homocedástica
- 04.2 Distancia KS — población simulada heterocedástica
- 04.3 Distancia KS — datos reales Auto MPG (Caso 1 y Caso 2)

## Ejecución

```r
install.packages("lmtest")
```

Colocar `auto-mpg.csv` en el directorio de trabajo y correr los scripts en el orden listado arriba.

## Requisitos

R (≥ 4.0), paquete `lmtest`.





## 📊 Contenido de los scripts

| Script | Descripción | Salidas principales |
|--------|-------------|---------------------|
| **01_simulaciones.R** | Simulación Monte Carlo para comparar MCO vs Bootstrap | Tablas de errores estándar, cobertura de IC |
| └─ 01.1 | Supuestos clásicos cumplidos (n=50, B=1000) | |
| └─ 01.2 | Con heterocedasticidad (n=50, B=1000) | |
| **02_prueba_supuestos.R** | Exploración y verificación de supuestos en Auto MPG | Pruebas Shapiro-Wilk y Breusch-Pagan |
| └─ 02.1 | Exploración inicial (mpg vs weight) | |
| └─ 02.2 | Caso 1: log(mpg) ~ weight | |
| └─ 02.3 | Caso 2: mpg ~ log(weight) | |
| **03_bootstrap_auto_mpg.R** | Bootstrap por pares en datos reales | Errores estándar, IC bootstrap, métricas predictivas |
| └─ 03.1 | Bootstrap Caso 1 | |
| └─ 03.2 | Bootstrap Caso 2 | |
| └─ 03.3 | Evaluación predictiva (70/30) | RMSE, MAE, R² |
| **04_estabilidad_asintotica.R** | Análisis de convergencia del Bootstrap | Distancias KS para diferentes tamaños de muestra |
| └─ 04.1 | Población homocedástica | |
| └─ 04.2 | Población heterocedástica | |
| └─ 04.3 | Datos reales Auto MPG | |







