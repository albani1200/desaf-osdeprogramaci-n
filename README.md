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


#  Desafío 2 Transformación de datos y crear nuevas variables
* Crear una nueva columna con las alturas en metros.
* Mostrar el nuevo data frame.

```r
# Crear el data frame de alturas
alturas <- data.frame(
  nombre = c("Laura", "Pedro", "Sara", "Miguel"),
  altura_cm = c(160, 175, 150, 180)
)

# Crear una nueva columna con las alturas en metros
alturas <- alturas %>%
  mutate(altura_m = altura_cm / 100)

print(alturas)

```
### Resultado

| nombre | altura_cm | altura_m |
|--------|-----------|----------|
| Laura  | 160       | 1.60     |
| Pedro  | 175       | 1.75     |
| Sara   | 150       | 1.50     |
| Miguel | 180       | 1.80     |


# Desafío 3 Generación de gráficos de barras
* Crear un gráfico de barras para visualizar las ventas mensuales.

```r
# Instalar el paquete ggplot2 si no lo tienes instalado en r, de acuerdo

# Cargar el paquete ggplot2
library(ggplot2)

# Crear el data frame de ventas
ventas <- data.frame(
  mes = c("Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio"),
  ventas = c(12000, 15000, 13000, 16000, 17500, 14000)
)

# Crear un gráfico de barras para visualizar las ventas mensuales con colores diferentes para cada mes Xd
ggplot(ventas, aes(x = mes, y = ventas, fill = mes)) +
  geom_bar(stat = "identity") +
  labs(title = "Ventas Mensuales",
       x = "Mes",
       y = "Ventas") +
  theme_minimal() +
  scale_fill_brewer(palette = "Set3") # Utilice una paleta de colores para mayor diferencia

```

![ventas](https://github.com/user-attachments/assets/9414cd7c-eff5-40e1-a4a6-2b19d4fa5be2)




