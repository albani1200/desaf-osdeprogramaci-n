# Desafío 1 Filtrar y manipular data frames 
> Filtrar todas las especies que viven en un lago
> Ordenar los resultados por tamaño (de mayor a menor)

```r

# Cargar el paquete dplyr
library(dplyr)

# Crear el data frame
especies <- data.frame(
  especie = c("Ajolote", "Rana", "Serpiente", "Tortuga"),
  habitat = c("Lago", "Río", "Bosque", "Lago"),
  tamano = c(30, 10, 150, 50),
  peso = c(150, 25, 1000, 500)
)

# Filtrar las especies que viven en un lago y ordenar por tamaño (de mayor a menor)
especies_lago <- especies %>%
  filter(habitat == "Lago") %>%
  arrange(desc(tamano))

print(especies_lago)
```
### Resultado

| especie | habitat | tamano | peso |
|---------|---------|--------|------|
| Tortuga | Lago    | 50     | 500  |
| Ajolote | Lago    | 30     | 150  |

