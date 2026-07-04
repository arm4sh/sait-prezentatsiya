# AutoExam — onepager

Статический лендинг единой платформы приёма теоретического и практического экзаменов
(«от теории до прав»). Один HTML-файл + папка с изображениями, без сборки и сервера.

## Структура

```
autoexam-site/
├── index.html        # страница целиком (стили и скрипты внутри)
├── assets/           # фотографии из презентации
│   ├── hero.jpg
│   ├── office.jpg
│   ├── instructor.jpg
│   ├── car_dash.jpg
│   ├── phone1.jpg
│   └── phone2.jpg
├── .gitignore
└── README.md
```

Все пути к картинкам относительные (`assets/...`), поэтому сайт работает и в подпапке
(например `логин.github.io/autoexam/`), и на своём домене.

## Публикация на GitHub Pages

1. Создай пустой репозиторий на github.com (кнопка **New**), например `autoexam`.
2. Из этой папки выполни:

   ```bash
   git init
   git add .
   git commit -m "AutoExam onepager"
   git branch -M main
   git remote add origin https://github.com/<логин>/autoexam.git
   git push -u origin main
   ```

3. В репозитории: **Settings → Pages → Build and deployment → Deploy from a branch**,
   ветка `main`, папка `/ (root)`, **Save**.
4. Через 1–2 минуты сайт будет по адресу `https://<логин>.github.io/autoexam/`.

Обновление: правишь файлы → `git add .` → `git commit -m "..."` → `git push`.
Pages пересоберёт страницу автоматически.

## Видео

Блок под видео в разделе «Как это выглядит в деле» помечен `id="video-placeholder"`,
рядом в `index.html` лежит комментарий с примером.

- **Лучше:** залить ролик на YouTube/Vimeo и встроить `<iframe>` — легко и быстро грузится.
- **mp4 в Git не класть** (репозиторий распухнет, есть лимиты на размер файла).
  Если нужен локальный файл — используй Git LFS. `.gitignore` уже исключает `*.mp4`.

## Альтернативные хостинги

Тот же репозиторий можно подключить к **Netlify** или **Cloudflare Pages**
через «Import from Git» — тогда каждый `git push` публикует новую версию,
а каждый pull request получает превью-ссылку.
