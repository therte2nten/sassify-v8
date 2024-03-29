## v8.1.2
- Вынес в отдельный файл карты из Default Values
- Перенес некоторые переменные в сеткицю `setting--*`
- Обновил версию пакета до 8.1.2
- Добавил некоторую документацию проекта (#18)

## v8.1.1
- Реализация сетки Bootstrap 4 (#16)
- Удалил старую реализацию сетки из Bootstrap 3
- Добавил функцию `color-common` (#15)
- Доработал вывод ошибок в функции `map-deep-get`

## v8.1.0
-  Обновил версию пакета до 8.1.0
-  Добавил Bootstrap Grid в проект (#8)
-  Небольшие правки в README.md
-  Сменил двойные кавычки на одинарные (#7)

## v8.0.0
-  Добавил миксин `justify-content`
-  Добавил миксин `align-self`
-  Добавил миксин `align-items`
-  Добавил миксин `align-content`
-  Удалил всё для устаревшего Internet Explorer
-  Удалил все префиксы для устаревшего Internet Explorer
-  Добавил возможность поддержки браузера IE в миксине `flex-wrap`
-  Доработал миксин `flex-direction`
-  Добавил миксин `flexbox`
-  Добавил пример кода в документацию миксина `flex-wrap`
-  Добавил миксин `flex-wrap`
-  Добавил миксин `flex-shrink`
-  Добавил миксин `flex-grow`
-  Добавил миксин `flex-flow`
-  Добавил миксин `flex-direction`
-  Добавил миксин `flex-basis`
-  Добавил миксин `flex`
-  Добавил миксин `media`
-  Добавил миксин `brakepoint`
-  Добавил миксин `centering`
-  Навел порядок в названиях групп @SassDoc
-  Добавил миксин `selection`
-  Поменял пути до миксина `size`
-  Добавил миксин `text-shorten`
-  Добавил миксин `box-sizing`
-  Добавил миксин `calc`
-  Добавил миксин `box-shadow-store`
-  Переименовал Helper в Store
-  Добавил карту `$helper--css-shadows`
-  Добавил миксин `box-shadow-v2`
-  Добавил миксин `box-shadow`
-  Добавил миксин `media-prefers-contrast`
-  Добавил миксин `transform-style`
-  Добавил миксин `transform-origin`
-  Добавил миксин `transform`
-  Добавил миксин `transition-timing-function`
-  Добавил миксин `transition-property`
-  Добавил миксин `transition-duration`
-  Добавил ТЗ (#4)
-  Обвновил версию Sass до 1.62.1
-  Добавил миксин `transition-delay`
-  Добавил миксин `transition`
-  Добавил миксин `backdrop-filter`
-  Небольшие доработки миксина `check`
-  Немного доработал миксин `check`
-  Добавил миксин `check`
-  Правки в нейминге цветовых палитр
-  Удалил файл палитры цветов Windows Phone 8
-  Добавил карты (`map`) со списком Microsoft Windows Colors Palette
-  Добавил карты (`map`) со списком Apple HIG Colors
-  Добавил карты (`map`) со списком Material Design Colors
-  Добавил переменную `$helper--input-type`
-  Провел реструктуризацию проекта (#3)
-  К переменным `prefixes--*` добавил пояснения префиксов
-  Добавил миксин `border-radius`
-  Добавил миксин `opacity`
-  Добавил миксин `set-initial`
-  Добавил миксин `keyframes`
-  Добавил миксин `position-relative`
-  Добавил миксин `position-fixed`
-  Добавил миксин `position-absolute`
-  Добавил миксин `position-sticky`
-  Добавил миксин `position`
-  Обновил версию `sass` до 1.62.0
-  Переименовал функцию `is-int` в `is-number`
-  Добавил миксин `tab-size`
-  Добавил миксин `visually-hidden`
-  Добавил функцию `list-prepend` от @KittyGiraudel
-  Добавил проверку типа в функцию `list-last-index`
-  Добавил функцию `list-last-index` от @KittyGiraudel
-  Переименовал функцию `first-in-list` в `list-first-item`
-  Переименовал функцию `last-in-list` в `list-last-item`
-  Немного доработал README.md
-  Обновил версию пакета до 7.0.2
-  Доработал скрипты в package.json
-  Перенес список игнорируемых файлов в отдельный файл
-  Добавил ключ `--access public` к скрипту `npm:publish` в package.json
-  Добавил ненужные папки в игнор для @npm
-  Отрефакторил код и доработал комментарии @sassdoc
-  Добавил миксин `user-select`
-  Добавил миксин `custom-properties-use`
-  Добавил миксин `custom-properties`
-  Добавил миксин `prefixer`
-  Удалил модуль `first-in-list` из миксина `size` за ненадобностью
-  Добавил миксин `size`
-  Небольшие доработки документации @sassdoc
-  Добавил папку _docs/_ в файл игнора
-  Добавил `sassdoc` в `devDependencies`
-  Добавил скрипт для генерации @SassDoc
-  Поправил комментарии для @sassdoc
-  Доработка .gitignore
-  Реализация Strict Mode ("жесткий режим") / #2
-  Добавил проверку типа параметра в `is-string-start-with`
-  Добавил проверку типа параметра в `is-string-end-with`
-  Добавил проверку типа параметра в `is-string-contains`
-  Добавил проверку типа параметра в `first-in-list`
-  Добавил проверку типа параметра в `last-in-list`
-  Добавил проверку типа параметра в `string-replace`
-  Добавил проверку типа параметра в `number-invert`
-  Немного доработал функцию `invalid-value-message`
-  Добавил начальную реализацию Strict Mode
-  Добавил миксин `amcss` от @W3cplus
-  Добавил миксины BEM от Marcmintel
-  Добавил функцию `selector-to-string` от Marcmintel
-  Меняю названия функций `is-end-with` и `is-start-with`
-  Добавил функцию `is-string-contains` от @sindresorhus
-  Добавил функцию `is-end-with` от @sindresorhus
-  Добавил функцию `is-start-with` от @sindresorhus
-  Привел в порядок комментарии к коду
-  Обновил npm-зависимость `sass` до `1.60.0`
-  Добавил к `$default-values--set-initial_initials` правило `!default`
-  Добавил функцию `set-initial` от @takamoso
-  Добавил функцию `is-list-contains`
-  Изменил назв. переменной `url-encode-characters`
-  Добавил функцию `strip-unit` от @sindresorhus
-  Добавил функцию `url-encode` от @sindresorhus
-  Добавил функцию `string-replace` от @sindresorhus
-  Добавил в проект @editorconfig
-  Добавил функцию `number-invert` от @sindresorhus
-  Добавил функцию `is-time` от @selfishprimate
-  Добавил функцию `is-string` от @takamoso
-  Добавил функцию `is-map` от @takamoso
-  Добавил функцию `is-list` от @takamoso
-  Добавил функцию `is-int` от @pentzzsolt
-  Добавил функцию-алиас `is-bool` для `is-boolean`
-  Добавил функцию `is-boolean` от @takamoso
-  Добавил функцию `map-deep-get` от @KittyGiraudel
-  Добавил комментарии к коду функции `map-deep-set`
-  Добавил функцию `map-deep-set` от @KittyGiraudel
-  Добавил функцию `last-in-list` от @sindresorhus
-  Добавил функцию `first-in-list` от @sindresorhus
-  Добавил функцию `color-tint` от @KittyGiraudel
-  Добавил функцию `color-shade` от @KittyGiraudel
-  Удалил доку ARCH.md (временно)
-  Добавил некоторые SCSS-файлы
-  Добавил документ ARCH.md
-  Добавил настройки для Visual Studio Code
-  Добавил лого проекта и пару настроек для VSCode
-  Добавил основной SCSS-файл
-  Добавил файл лицензии (MIT)
-  Добавил файл CODEOWNERS
-  Добавил некоторые доки для комьюнити
-  Указал `engine-strict=true` в .npmrc
-  Добавил файл .gitignore
-  Добавил README.md
-  `npm init`
