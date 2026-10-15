# agroclima-ainame: Gerar APK

on:
  push:
    branches: [main, master]
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - uses: actions/setup-node@v4
        with:
          node-version: 22

      - uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: 21

      - name: Instalar dependências
        run: npm install

      - name: Criar projeto Android
        run: npx cap add android

      - name: Gerar ícones do app
        continue-on-error: true
        run: npx capacitor-assets generate --android

      - name: Sincronizar arquivos web
        run: npx cap sync android

      - name: Compilar APK
        working-directory: android
        run: ./gradlew assembleDebug

      - name: Enviar APK
        uses: actions/upload-artifact@v4
        with:
          name: AgroClimaAI-apk
          path: android/app/build/outputs/apk/debug/app-debug.apk
