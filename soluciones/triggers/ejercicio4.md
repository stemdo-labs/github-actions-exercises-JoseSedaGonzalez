# Triggers - Ejercicio 4

## Configura un workflow para que se ejecute todos los días a las 12:00 UTC y que imprima "Scheduled job executed!" en la consola

````yml
# .github/workflows/scheduled_job.yml

name: Daily Scheduled Job

on:
  schedule:
    - cron: '0 12 * * *'  # Ejecuta el workflow todos los días a las 12:00 UTC

jobs:
  scheduled-job:
    runs-on: labs-runner  # Utiliza un runner personalizado llamado 'labs-runner'
    # Asegúrate de que 'labs-runner' esté registrado y disponible en tu cuenta o repositorio.

    steps:
      - name: Saludo por consola
        run: echo "Scheduled job executed!"  # Imprime el mensaje en la consola

````