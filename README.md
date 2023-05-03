![Изображение-баннер с логотипом проекта Sassify и логотипом GitHub](https://github.com/therteenten/sassify/blob/main/.github/images/sassify_banner_github.png?raw=true)

<img src="https://github.com/therteenten/sassify/blob/main/.github/images/sassify_logo_round.png?raw=true" width="96" height="96" align="right" alt="Логотип проекта Sassify"> [Sassify](https://github.com/therteenten/sassify.git)
===

Большой набор миксинов и функций на языке CSS-препроцессора [Sass](https://github.com/sass).

![Список языков](https://img.shields.io/github/languages/count/therteenten/sassify?color=%23ff0056)
![Топ язык в репо](https://img.shields.io/github/languages/top/therteenten/sassify?color=%23ff0056)
![Кол-во открытых ишью](https://img.shields.io/github/issues-raw/therteenten/sassify)
![Кол-во открытых PR](https://img.shields.io/github/issues-pr-raw/therteenten/sassify)
![Лицензия](https://img.shields.io/github/license/therteenten/sassify)
![Версия пакета Sassify](https://img.shields.io/github/package-json/v/therteenten/sassify)
![Версия пакета Sassify в ветке develop](https://img.shields.io/github/package-json/v/therteenten/sassify/develop)
![Версия зависимости `sass`](https://img.shields.io/github/package-json/dependency-version/therteenten/sassify/dev/sass/develop?color=%23d94390)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/therteenten/sassify)
![GitHub contributors](https://img.shields.io/github/contributors/therteenten/sassify)
![GitHub last commit](https://img.shields.io/github/last-commit/therteenten/sassify)

- [Список изменений](./CHANGELOG.md)
- [Участие в разработке Sassify](./CONTRIBUTING.md)
- [Кодекс Поведения участника](./CODE_OF_CONDUCT.md)
- [Техническое задание проекта](.docs/technical-specification.md)

## Быстрый старт
1. Перед тем как начать нужно удостовериться в том, что у Вас установлен Node.js:

	```sh
	node -v
	# или
	npm -v
	```
	```sh
	v16.18.1
	# или
	9.6.4
	```

	> Если у Вас какая-то другая версия - всё нормально. Значит Node.js у Вас установлен.

2. Далее с помощью пакетного менеджера для Node.js устанавливаем пакет в ваш проект:

	```sh
	# npm
	npm install @therteenten/sassify --save-dev
	```
	```sh
	# Yarn
	yarn add @therteenten/sassify --dev
	```
	```sh
	# pnpm
	pnpm install @therteenten/sassify -D
	```

3. Далее в нужный Sass/SCSS-файл импортируем модуль Sassify:

	```scss
	@use 'node_modules/@therteenten/sassify' as sassify;
	```

	> Если Вы до сих пор используете директиву `@import` в Sass, то вот что говорят разработчики Sass в своем блоге:
	>
	> > The Sass team wants to allow for a large amount of time when `@use` and `@import` can coexist, to help the ecosystem smoothly migrate to the new system. However, doing away with `@import` entirely is the ultimate goal for simplicity, performance, and CSS compatibility.
	> > <details><summary>Перевод (машинный)</summary><br><p>Команда Sass хочет предусмотреть большое количество времени, когда <code>@use</code>  и <code>@import</code> могут сосуществовать, чтобы помочь экосистеме плавно перейти на новую систему. Однако полный отказ от <code>@import</code> является конечной целью для простоты, производительности и совместимости с CSS.</p></details>

4. Проверяем подключение Sassify:

	```scss
	@include sassify.check();
	```
	```css
	/* (sassify) 🟩 The check was successful! */
	/* (sassify) ⬜ Package Name: @therteenten/sassify */
	/* (sassify) ⬜ Description:  Большой набор миксинов и функций на языке CSS-препроцессора Sass */
	/* (sassify) ⬜ Author:       Haba Kudzaev <therteenten@inbox.ru> */
	/* (sassify) ⬜ License:      MIT */
	/* (sassify) ⬜ npm:          https://www.npmjs.com/package/@therteenten/sassify */
	/* (sassify) ⬜ Source Code:  https://github.com/therteenten/sassify */
	```

5. **Готово!**

## Нашли проблему? Есть предложение?
...

## Документация
...

### Локальная документация
...

## Сообщество
...

## Версии
...

## Благодарности
...

## Лицензия
Проект распространяется по свободной лицензии MIT, однако в проекте используются труды иных людей, чьё авторство я также обозначил в местах, где используется их код.

```
MIT License

Copyright (c) 2023 Haba Kudzaev <therteenten@inbox.ru>
```

> Если Вы нашли нарушение чьей-либо лицензии в моем проекте, то просьба написать мне → [Telegram][therteenten-telegram], [эл. почта][therteenten-email] или [VK][therteenten-vk].

<!-- ! -->
[therteenten-vk]: https://vk.com/therteenten
[therteenten-telegram]: https://t.me/therteenten
[therteenten-email]: mailto:therteenten@inbox.ru
<!-- ! -->
