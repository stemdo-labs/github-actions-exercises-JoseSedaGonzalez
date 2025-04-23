# Triggers (Dispatch) - Ejercicio 

## 1. Configura un workflow para que se ejecute manualmente usando el evento workflow_dispatch.

## 2. Define un input llamado _"message"_ que permita al usuario ingresar un mensaje personalizado.

## 3. El workflow debe ser capaz de imprimir ese mensaje.

````yml
# .github/workflows/manual_dispatch.yml

name: Manual Dispatch Example

on:
  workflow_dispatch:
    inputs:
      message:
        description: 'Mensaje personalizado para mostrar'
        required: true
        default: '¡Hola desde GitHub Actions!'

jobs:
  print-message:
    runs-on: labs-runner

    steps:
      - name: Mostrar el mensaje ingresado
        run: echo "Mensaje recibido ${{ github.event.inputs.message }}"
````
