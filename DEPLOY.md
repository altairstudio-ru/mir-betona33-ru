# Деплой лендингов mir-betona33.ru

## Текущая структура

- `mir-betona33.ru/` — общая репа (CONTEXT.md, README.md, yandex-direct/, seo/, дизайны лендингов, рабочие файлы).
- `design/Betonnye-izdeliya/` — прототип лендинга «Бетонные изделия» (чистый статический HTML).

## Принцип

Деплоим **только то, что нужно клиенту**. Общую репу целиком на хостинг не отправляем.

## Стратегия: ветка + Vercel

1. **Ветка `design/betonnye-izdeliya`** в общей репе — содержит только файлы лендинга.
2. **Vercel-проект** с `Root Directory = design/Betonnye-izdeliya` (или monorepo-настройка).
3. Каждый push в эту ветку → preview URL вида `mir-betona33-ru-git-design-betonnye-izdeliya-<user>.vercel.app`.
4. Эту ссылку отдаём клиенту.

## Быстрый деплой без настройки (Netlify Drop)

1. Открыть https://app.netlify.com/drop
2. Перетащить папку `design/Betonnye-izdeliya/`
3. Через 30 секунд — публичный URL, готовый для клиента.

## Команды

```bash
# Создать ветку и закоммитить только лендинг
cd /home/andrey/Projects/mir-betona33.ru
git checkout -b design/betonnye-izdeliya
git add design/Betonnye-izdeliya/
git commit -m "design: прототип лендинга 'Бетонные изделия'"
git push -u origin design/betonnye-izdeliya
```

## Чек-лист перед показом клиенту

- [ ] Заменить `[ВСТАВИТЬ ...]` плейсхолдеры на реальные данные
- [ ] Добавить настоящие фото производства вместо серых блоков
- [ ] Подключить реальный обработчик формы заявки
- [ ] Подключить Яндекс.Метрику и цели
- [ ] Проверить мобильную версию
- [ ] Прогнать через PageSpeed Insights (цель: 90+)
