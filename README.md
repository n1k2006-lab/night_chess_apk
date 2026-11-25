# Ночные Шахматы Pro — сборка Android APK через GitHub Actions

Готовый проект на базе **Capacitor** для автоматической сборки Android APK в GitHub Actions.

## Как собрать APK (через Termux или ПК)

1. Распакуйте архив в папку проекта и зайдите в неё:
   ```bash
   unzip night_chess_apk.zip -d night-chess-pro
   cd night-chess-pro
   ```

2. Инициализируйте репозиторий и отправьте на GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial Night Chess Pro APK build"
   git branch -M main
   git remote add origin https://github.com/ВАШ_ЛОГИН/ВАШ_РЕПОЗИТОРИЙ.git
   git push -u origin main
   ```

3. Откройте репозиторий на GitHub → вкладка **Actions** → дождитесь завершения воркфлоу **Build Android APK** (около 3–4 минут) → скачайте артефакт **NightChessPro-debug-apk** с готовым `app-debug.apk`.

## Особенности сборки
- В процессе сборки GitHub Actions автоматически скачивает `stockfish.js` прямо внутрь `www/stockfish.js`, поэтому **настоящий Stockfish работает в APK полностью офлайн без интернета**!
- Если по какой-то причине воркер не запустится на старом Android WebView, приложение автоматически переключится на встроенный шахматный движок.
