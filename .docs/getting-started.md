# Начало работы
Sassify &mdash; это npm-пакет, а значит для установки Sassify в свой проект у Вас должен быть установлена среда исполнения [Node.js](https://nodejs.org/en), а вместе с ним должен быть установлен совместимый пакетный менеджер - [npm](https://www.npmjs.com/), [yarn](https://classic.yarnpkg.com/lang/en/docs/install/), [pnpm](https://pnpm.io/) или любой другой.

Проверить наличие Node.js на вашем компьютере можно командой `node -v` в терминале:

```sh
=> node -v
v16.18.1
```

> Если у Вас вывод консоли отличен от моего - ничего страшного. Главное, что Node.js установлен.

Таким же образом можно проверить наличие пакетного менеджера. Покажу на примере npm, т.к. он идет в комплекте с Node.js:

```sh
=> npm -v
8.19.2
```

Теперь, когда мы убедилить в наличии установленного Node.js и пакетного менеджера для него, попробуем добавить пакет Sassify в наш проект.

## Добавляем пакет Sassify в наш проект
1. Переходим в папку проекта:

	```sh
	therteenten-pc :: ~/Проекты » mkdir MyTestProject
	therteenten-pc :: ~/Проекты » cd MyTestProject
	```

2. Инициализируем npm в корне папки проекта:

	```sh
	therteenten-pc :: ~/Проекты/MyTestProject » npm init -y
	Wrote to /home/therteenten/Проекты/MyTestProject/package.json:

	{
		"name": "mytestproject",
		"version": "1.0.0",
		"description": "",
		"main": "index.js",
		"scripts": {
			"test": "echo \"Error: no test specified\" && exit 1"
		},
		"keywords": [],
		"author": "",
		"license": "ISC"
	}
	```

	> В корне проекта должен быть создан файл _/package.json_!

3. Устанавливаем пакет `@therteenten/sassify` в проект:

	```sh
	therteenten-pc :: ~/Проекты/MyTestProject » npm install @therteenten/sassify sass --save-dev

	added 18 packages, and audited 19 packages in 5s

	2 packages are looking for funding
		run `npm fund` for details

	found 0 vulnerabilities
	therteenten-pc :: ~/Проекты/MyTestProject »
	```

	> Также мы установили пакет `sass`, который нужен для компиляции Sass в CSS. Если у Вас используется какой-то другой компилятор, то можно не устанавливать пакет `sass`.

4. Готово!

## Проверка установки Sassify
Теперь, когда пакет Sassify установлен в наш проект, нам надо убедиться что все работает.

В любом Sass-файле прописываем следующее (я использую синтаксис SCSS):

```scss
// main.scss

/// Импортируем модуль Sassify в наш Sass-файл:
@use 'node_modules/@therteenten/sassify' as sassify;

/// Используем миксин `check` для проверки установки:
@include check();
```

```css
/* dist/stylesheets/main.css */

@charset "UTF-8";
/* (sassify) 🟩 The check was successful! */
/* (sassify) ⬜ Package Name: @therteenten/sassify */
/* (sassify) ⬜ Description:  Большой набор миксинов и функций на языке CSS-препроцессора Sass */
/* (sassify) ⬜ Author:       Haba Kudzaev <therteenten@inbox.ru> */
/* (sassify) ⬜ License:      MIT */
/* (sassify) ⬜ npm:          https://www.npmjs.com/package/@therteenten/sassify */
/* (sassify) ⬜ Source Code:  https://github.com/therteenten/sassify */
```

Если у Вас в CSS-файле подобная информация присутствует - все готово. Можно удалить строчку `@include check();` из Sass-файла.

### А что, если я не использую в проекте пакетный менеджер Node.js?
В принципе, вы можете склонировать [репозиторий](https://github.com/therteenten/sassify) проекта Sassify с GitHub и подключать Sassify непосредственно так.

```sh
# Клонирование репозитория с GitHub
git clone https://github.com/therteenten/sassify.git
```

> А также вы можете [скачать](https://github.com/therteenten/sassify/archive/refs/heads/main.zip) ZIP-архив проекта Sassify с того же GitHub.

## Воркфлоу работы с Sassify
Т.к. команда Sass [не рекомендует](https://sass-lang.com/blog/the-module-system-is-launched) использовать директиву [`@import`](https://sass-lang.com/documentation/at-rules/import) в пользу [`@use`](https://sass-lang.com/documentation/at-rules/use), мы и не используем в разработке её. Если у Вас в проекте используется компилятор Sass, не поддерживающий директиву `@use`, то возможны проблемы с совместимостью.

Т.к. при использовании директивы `@use` мы не отправляем Sassify в глобальную область видимости, то логично подключать Sassify там, где он требуется.

В одном из своих проектов я использую отдельный файл _\_sassify.scss_, в котором содержится импорт модуля Sassify с нужными конфигами:

```scss
// file: './stylesheets/vendor/_sassify.scss'
@forward '../../node_modules/@therteenten/sassify' with (
	$setting--strict-mode: false,
	$dvalues--grid-class-names: (
		container: 'container',
		container-fluid: 'container-f',
		row: 'row',
		no-gutters: 'no-gtrs',
		col: 'col',
		cols: 'cols',
		order: 'order',
		offset: 'offset'
	),
	$dvalues--grid-generate-minimal-reset: true
);
```

И в нужном файле импортирую именно этот файл, в котором нужен Sassify:
```scss
// file: './stylesheets/components/_button.scss'
@use '../vendor/sassify' as sassify;
@use '../abstracts/variables' as vars;

.button {
	// ...
	@include sassify.border-radius(vars.$button--border-radius);
}
```
```scss
// file: './stylesheets/vendor/grid.scss'
@use '../vendor/sassify' as sassify;

// Генерация сетки Bootstrap Grid
@include make-grid();
```

Таким образом можно сконфигурировать Sassify в одном месте и использовать там, где надо.
