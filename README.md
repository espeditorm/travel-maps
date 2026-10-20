# Travel Maps

Mapas de viagem publicados no Firebase Hosting.

- `public/index.html` — Mapa das Ruínas (Atenas, Cairo e Gizé)

## Como funciona

- **Pull request:** cada PR ganha uma prévia temporária no Firebase (link comentado no PR, expira em 7 dias).
- **Merge no `main`:** o site é publicado no endereço oficial (`https://<projeto>.web.app`).

## Configuração (uma vez só)

1. Crie o projeto em https://console.firebase.google.com e ative o **Hosting**.
2. No Firebase: ⚙️ Configurações do projeto → **Contas de serviço** → **Gerar nova chave privada**. Baixa um arquivo `.json`.
3. No GitHub: **Settings → Secrets and variables → Actions**
   - aba **Secrets** → *New repository secret*: nome `FIREBASE_SERVICE_ACCOUNT`, valor = conteúdo inteiro do `.json`.
   - aba **Variables** → *New repository variable*: nome `FIREBASE_PROJECT_ID`, valor = ID do projeto (ex.: `travel-maps-1234`).
4. Para publicar sem esperar um merge: **Actions → Deploy no Firebase → Run workflow**.

Enquanto `FIREBASE_PROJECT_ID` não estiver configurado, os workflows ficam parados (não falham).

## Testar localmente

Abra `public/index.html` no navegador, ou rode `npx firebase-tools serve`.
