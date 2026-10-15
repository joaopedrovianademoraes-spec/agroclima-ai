# AgroClima AI — App Android

Este projeto transforma o PWA do AgroClima AI em um app Android (arquivo .apk) usando Capacitor.
O APK é gerado automaticamente pelo GitHub, então você não precisa instalar Android Studio.

## Como gerar o APK (sem instalar nada no computador)

1. Crie uma conta gratuita em https://github.com (se ainda não tiver).
2. Crie um repositório novo (pode ser privado), por exemplo `agroclima-ai`.
3. Envie TODO o conteúdo desta pasta para o repositório
   (botão "Add file" > "Upload files"; inclua a pasta `.github`, que pode estar oculta no seu computador).
4. Abra a aba **Actions**. O fluxo "Gerar APK" roda sozinho (leva uns 5 a 10 minutos).
   Se não iniciar, clique em "Gerar APK" > "Run workflow".
5. Quando terminar (check verde), abra a execução e baixe **AgroClimaAI-apk** em "Artifacts".
6. Descompacte, passe o `app-debug.apk` para o celular e instale.
   O Android vai pedir para permitir "instalar apps de fontes desconhecidas".

## Como usar
Abra o app, toque em "Usar minha localização" e permita o acesso à localização.
É necessário internet para consultar o Open-Meteo.

## Observações
- O APK gerado é de teste (debug): serve para instalar no seu celular e apresentar o projeto.
  Para publicar na Google Play seria necessário gerar uma versão assinada (release).
- Para mudar nome, ícone ou código: edite os arquivos em `www/` e `capacitor.config.json`
  e envie de novo ao GitHub; o APK é refeito.
- Os critérios de análise são demonstrativos e não substituem bula/rótulo, legislação
  ou responsável técnico.

## Alternativa mais simples (sem APK)
A pasta `www/` também funciona como PWA: hospede em um endereço HTTPS
(GitHub Pages, Netlify etc.), abra no Chrome do celular e use "Instalar aplicativo".
