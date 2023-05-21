![Изображение-баннер с логотипом проекта Sassify и логотипом GitHub](https://github.com/therteenten/sassify/blob/main/.github/images/sassify_banner_github.png?raw=true)

<img src="https://github.com/therteenten/sassify/blob/main/.github/images/sassify_logo_round.png?raw=true" width="96" height="96" align="right" alt="Логотип проекта Sassify"> [Sassify](https://github.com/therteenten/sassify.git)
===

Большой набор миксинов и функций на языке CSS-препроцессора [Sass](https://github.com/sass).

![Список языков](https://img.shields.io/github/languages/count/therteenten/sassify?color=%23ff0056)
![Топ язык в репо](https://img.shields.io/github/languages/top/therteenten/sassify?color=%23ff0056)
![Кол-во открытых ишью](https://img.shields.io/github/issues-raw/therteenten/sassify)
![Кол-во открытых PR](https://img.shields.io/github/issues-pr-raw/therteenten/sassify)
![Лицензия](https://img.shields.io/github/license/therteenten/sassify)
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
Есть ошибка или запрос функции? Пожалуйста, сначала прочитайте [руководство по Issues][sassify-github-contributing-issues] и найдите существующие и закрытые проблемы. Если ваша проблема или идея еще не рассмотрены, пожалуйста, откройте [новый вопрос][sassify-github-new-issue].

## Документация
Код Sassify задокументирован в формате [SassDoc][sassdoc-site]. Документацию можно получить локально:

1. Клонируйте этот репозиторий:

	```sh
	git clone https://github.com/therteenten/sassify
	```

2. Перейдите в директорию проекта:

	```sh
	cd sassify
	```

3. Установите зависимости npm:

	```sh
	npm install
	```

4. Выполните команду для генерации документации SassDoc:

	```sh
	npm run sassdoc
	```

5. В папке _docs/_ должен появиться файл _index.html_ с документацией по проекту - откройте его в браузере.

> На данный момент это единственная версия документации проекта. В будущем я планирую использовать для этого GitHub Actions и GitHub Pages.

## Сообщество
У проекта Sassify нет какого-либо сервера в Discord и нет своего канала или чата в Telegram или где-либо еще.

Все основные новости по проекту публикуются в личном Telegram-канале автора проекта - [@therte2nten][sassify-telegram] (там же есть и чат).

## Версии
Для обеспечения прозрачности цикла выпуска и стремления поддерживать обратную совместимость Sassify поддерживается в соответствии с рекомендациями [Semantic Versioning][semver-site]. Иногда я ошибаюсь, но я придерживаюсь этих правил, когда это возможно.

## Благодарности
Несмотря на то, что я умудрился как-то гармонично (надеюсь) уложить все эти функции и миксины в один котел, я не могу не выразить огромную благодарность след. персонажам:
- [Kitty Giraudel][github-user-KittyGiraudel] - за большое количество кода и статей по Sass,
- [takamoso][github-user-takamoso] - за полезный код,
- [Sindre Sorhus][github-user-sindresorhus] - за полезный код,
- разработчикам [Bootstrap][github-repo-bootstrap] - за шаблон для этого README,
- разработчикам CSS-препроцессора [Sass][sass-site] - за непосредственно Sass,
- всем тем у кого я учился (хоть я и не помню ваши имена).

## Лицензия
Проект распространяется по свободной лицензии MIT, однако в проекте используются труды иных людей, чьё авторство я также обозначил в местах, где используется их код.

```
MIT License

Copyright (c) 2023 Haba Kudzaev <therteenten@inbox.ru>
```

> Если Вы нашли нарушение чьей-либо лицензии в моем проекте, то просьба написать мне → [Telegram][therteenten-telegram], [эл. почта][therteenten-email] или [VK][therteenten-vk].

<!-- ! -->
[sass-site]: https://sass-lang.com/
[github-repo-bootstrap]: https://github.com/twbs/bootstrap
[github-user-KittyGiraudel]: https://github.com/KittyGiraudel
[github-user-takamoso]: https://github.com/takamoso
[github-user-sindresorhus]: https://github.com/sindresorhus
[semver-site]: https://semver.org/
[sassdoc-site]: http://sassdoc.com/
[sassify-github-new-issue]: https://github.com/therteenten/sassify/issues/new/choose
[sassify-github-contributing-issues]: https://github.com/therteenten/sassify/blob/main/CONTRIBUTING.md#%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC%D1%8B-%D0%B8-%D1%8F%D1%80%D0%BB%D1%8B%D0%BA%D0%B8
[sassify-telegram]: https://t.me/therte2nten
[therteenten-vk]: https://vk.com/therteenten
[therteenten-telegram]: https://t.me/therteenten
[therteenten-email]: mailto:therteenten@inbox.ru
<!-- ! -->
