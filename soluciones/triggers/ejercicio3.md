# Triggers - Ejercicio 3

## Configura un workflow para que se ejecute cuando se cree una nueva Issue

````yml
# .github/workflows/issue_created.yml

name: Issue Created
# Este es el nombre visible del workflow en la pestaña "Actions".

on:
  issues:
    types: [opened]  # Este trigger se activa solo cuando se abre (opened) una nueva Issue.

jobs:
  notify-issue:
    runs-on: labs-runner  # Usa un runner estándar de GitHub que nos proporcionan.

    steps:
      - name: Mostrar mensaje en consola
        run: echo "Se ha creado una nueva Issue en el repositorio"
        # Este paso imprime un mensaje simple como prueba del trigger.

````