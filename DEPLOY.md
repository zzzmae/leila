# Инструкция по деплою на Netlify

## Вариант 1: Автоматический деплой через Git

1. **Отправьте код в репозиторий**

   ```bash
   git add .
   git commit -m "Ready for deploy"
   git push
   ```

2. **Подключите репозиторий к Netlify**

   - Зайдите на [app.netlify.com](https://app.netlify.com)
   - Нажмите "Add new site" → "Import an existing project"
   - Авторизуйтесь через GitHub/GitLab
   - Выберите ваш репозиторий
   - Netlify автоматически обнаружит файл `netlify.toml`

3. **Настройки (уже настроены в netlify.toml):**

   - Build command: `npm run build`
   - Publish directory: `dist/hearts-app`
   - Node version: 20

4. **Нажмите "Deploy site"**

## Вариант 2: Ручной деплой через Netlify CLI

1. **Установите Netlify CLI**

   ```bash
   npm install -g netlify-cli
   ```

2. **Войдите в аккаунт**

   ```bash
   netlify login
   ```

3. **Деплой**
   ```bash
   netlify deploy --prod
   ```

## Проверка локального билда

Перед деплоем можно проверить билд локально:

```bash
npm run build
```

Результат будет в папке `dist/hearts-app`

## Важные файлы

- `netlify.toml` - конфигурация для Netlify
- `.nvmrc` - версия Node.js
- `README.md` - описание проекта

## После деплоя

Netlify автоматически выдаст вам URL вида `https://your-site-name.netlify.app`

Вы можете настроить кастомный домен в настройках сайта на Netlify.
