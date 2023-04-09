![Изображение-баннер с логотипом проекта Sassify и логотипом GitHub](https://github.com/therteenten/sassify/blob/main/.github/images/sassify_banner_github.png?raw=true)

<img src="https://github.com/therteenten/sassify/blob/main/.github/images/sassify_logo_round.png?raw=true" width="96" height="96" align="right" alt="Логотип проекта Sassify"> [Sassify](https://github.com/therteenten/sassify.git)
===

Большой набор миксинов и функций на языке CSS-препроцессора [Sass](https://github.com/sass).

## Установка
Для начала необходимо создать проект.

1. В первую очередь инициализируем npm:

	```shell
	➜  my-super-sassify-project npm init -y
	Wrote to /home/therteenten/Проекты/my-super-sassify-project/package.json:

	{
		"name": "my-super-sassify-project",
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

2. После устанавливаем npm-пакет [`@therteenten/sassify`](https://www.npmjs.com/package/@therteenten/sassify)

	```shell
	➜  my-super-sassify-project npm install --save-dev @therteenten/sassify

	added 1 package, and audited 2 packages in 3s

	found 0 vulnerabilities
	```

3. Проверяем файл `package.json`:

	```shell
	➜  my-super-sassify-project cat package.json
	{
		"name": "my-super-sassify-project",
		"version": "1.0.0",
		"description": "",
		"main": "index.js",
		"scripts": {
			"test": "echo \"Error: no test specified\" && exit 1"
		},
		"keywords": [],
		"author": "",
		"license": "ISC",
		"devDependencies": {
			"@therteenten/sassify": "^7.0.2"
		}
	}
	```
4. Готово!

## Подключение
Sassify написан на Sass, а значит и подключать набор мы будем в Sass-файл (`*.sass`, `*.scss`).

1. В нужном Sass-файле прописываем импорт модуля через директиву [`@use`](https://sass-lang.com/documentation/at-rules/use):

	```scss
	@use 'node_modules/@therteenten/sassify' as sassify;
	```

	> Также мы занимаем пространство имён `sassify` через `as sassify`.

2. Пишем стили с использованием Sassify:

	```scss
	.card {

		background-color: #fff;
		color: #212121;
		// ...

		// Добавляем закругления через CSS-свойство `border-radius`
		// со всеми необходимыми браузерными префиксами:
		@include sassify.prefixer(
			border-radius,
			8px,
			webkit moz
		);

		// Добавляем тени через CSS-свойство `box-shadow` со всеми
		// необходимыми браузерными префиксами:
		@include sassify.prefixer(
			box-shadow,
			rgba(149, 157, 165, 0.2) 0px 8px 24px,
			webkit moz
		);

	}
	```

3. Смотрим на результат:

	```css
	.card {
		background-color: #fff;
		color: #212121;
		-webkit-border-radius: 8px;
		-moz-border-radius: 8px;
		border-radius: 8px;
		-webkit-box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
		-moz-box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
		box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
	}
	```

	> Стили мы писали для примера, чтобы убедиться в правильном подключении Sassify.

### Демонстрационное видео
Я также выложил [демонстрационное видео](https://youtu.be/DkYvbaIM_mA) на YouTube, в котором показал весь процесс подключения пакета Sassify:

[![Демонстрационное видео](https://github.com/therteenten/sassify/blob/main/.github/images/sassify_banner_demo_youtube.png?raw=true)](https://youtu.be/DkYvbaIM_mA)

...
