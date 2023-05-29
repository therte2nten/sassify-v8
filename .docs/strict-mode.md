# Strict Mode (жёсткий режим) — зачем?
Жёсткий режим в Sassify отвечает за тип вывода ошибок Sassify компилятором Sass.

```scss
$setting--strict-mode: true | false
```

- Если жёсткий режим вывода ошибок (Strict Mode) включен (состояние по умолчанию), то при появлении какой-то ошибки со стороны Sassify, компилятор Sass прекращает компиляцию CSS на месте аозникновения ошибки.

	```scss
	// Sass

	@use 'index.scss' as sassify with (
		$setting--strict-mode: true
	);

	.justify-baseline {
		@include sassify.justify-content();
	}

	.justify-center {
		@include sassify.justify-content(centere); // здесь ошибка
	}
	```
	```css
	/* CSS */

	/* Error: "🟥 Миксин «justify-content» не может принимать значение «centere»! Допустимые значения миксина: center start end flex-start flex-end left right baseline first baseline last baseline space-between space-around space-evenly stretch safe center unsafe center inherit initial unset"
	*    ,
	* 52 | /         @include invalid-value-message(
	* 53 | |             'justify-content',
	* 54 | |             $value,
	* 55 | |             config.$vvalues--justify-content
	* 56 | |         );
	*    | '---------^
	*    '
	*   core/cssex/justify/_content.scss 52:3  justify-content()
	*   _test.scss 10:2                        root stylesheet */

	body::before {
		font-family: "Source Code Pro", "SF Mono", Monaco, Inconsolata, "Fira Mono",
				"Droid Sans Mono", monospace, monospace;
		white-space: pre;
		display: block;
		padding: 1em;
		margin-bottom: 1em;
		border-bottom: 2px solid black;
		content: "Error: \"\1f7e5  \41c \438 \43a \441 \438 \43d  «justify-content» \43d \435  \43c \43e \436 \435 \442  \43f \440 \438 \43d \438 \43c \430 \442 \44c  \437 \43d \430 \447 \435 \43d \438 \435  «centere»! \414 \43e \43f \443 \441 \442 \438 \43c \44b \435  \437 \43d \430 \447 \435 \43d \438 \44f  \43c \438 \43a \441 \438 \43d \430 : center start end flex-start flex-end left right baseline first baseline last baseline space-between space-around space-evenly stretch safe center unsafe center inherit initial unset\"\a    \2577 \a 52 \2502  \250c          @include invalid-value-message(\a 53 \2502  \2502              'justify-content',\a 54 \2502  \2502              $value,\a 55 \2502  \2502              config.$vvalues--justify-content\a 56 \2502  \2502          );\a    \2502  \2514 \2500 \2500 \2500 \2500 \2500 \2500 \2500 \2500 \2500 ^\a    \2575 \a   core/cssex/justify/_content.scss 52:3  justify-content()\a   _test.scss 10:2                        root stylesheet";
	}
	```
	```sh
	# Terminal

	Error: "🟥 Миксин «justify-content» не может принимать значение «centere»! Допустимые значения миксина: center start end flex-start flex-end left right baseline first baseline last baseline space-between space-around space-evenly stretch safe center unsafe center inherit initial unset"
		╷
	52 │ ┌         @include invalid-value-message(
	53 │ │             'justify-content',
	54 │ │             $value,
	55 │ │             config.$vvalues--justify-content
	56 │ │         );
		│ └─────────^
		╵
		core/cssex/justify/_content.scss 52:3  justify-content()
		_test.scss 10:2                        root stylesheet
	```

- Если Strict Mode выключен. то компилятор Sass продолжит компиляцию в CSS, но без проблемного участка. Сообщение об ошибке будет все же выведено в консоль и в конечный CSS-файл в месте возникновения ошибки.

	```scss
	// Sass

	@use 'index.scss' as sassify with (
		$setting--strict-mode: false
	);

	.justify-baseline {
		@include sassify.justify-content();
	}

	.justify-center {
		@include sassify.justify-content(centere); // здесь ошибка
	}
	```
	```css
	/* CSS */

	.justify-baseline {
		-webkit-justify-content: flex-start;
		justify-content: flex-start;
	}

	.justify-center {
		/* (sassify) 🟧 Миксин «justify-content» не может принимать значение «centere»! */
		/* (sassify) 🟦 ┌ Допустимые значения для «justify-content»: */
		/* (sassify) 🟩 └─ center */
		/* (sassify) 🟩 └─ start */
		/* (sassify) 🟩 └─ end */
		/* (sassify) 🟩 └─ flex-start */
		/* (sassify) 🟩 └─ flex-end */
		/* (sassify) 🟩 └─ left */
		/* (sassify) 🟩 └─ right */
		/* (sassify) 🟩 └─ baseline */
		/* (sassify) 🟩 └─ first baseline */
		/* (sassify) 🟩 └─ last baseline */
		/* (sassify) 🟩 └─ space-between */
		/* (sassify) 🟩 └─ space-around */
		/* (sassify) 🟩 └─ space-evenly */
		/* (sassify) 🟩 └─ stretch */
		/* (sassify) 🟩 └─ safe center */
		/* (sassify) 🟩 └─ unsafe center */
		/* (sassify) 🟩 └─ inherit */
		/* (sassify) 🟩 └─ initial */
		/* (sassify) 🟩 └─ unset */
		/* (sassify) 🟥 └⤬ centere */
	}
	```

	```sh
	# Terminal

	Warning: (sassify) 🟧 Миксин «justify-content» не может принимать значение «centere»!
			devpack/invalid-value-message/_mixin.scss 53:3  invalid-value-message()
			core/cssex/justify/_content.scss 52:3           justify-content()
			_test.scss 10:2                                 root stylesheet

	devpack/invalid-value-message/_mixin.scss:57 Debug: (sassify) 🟧 Миксин «justify-content» не может принимать значение «centere»!
	devpack/invalid-value-message/_mixin.scss:61 Debug: (sassify) 🟦 ┌ Допустимые значения для «justify-content»:
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ center
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ start
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ end
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ flex-start
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ flex-end
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ left
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ right
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ baseline
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ first baseline
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ last baseline
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ space-between
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ space-around
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ space-evenly
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ stretch
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ safe center
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ unsafe center
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ inherit
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ initial
	devpack/invalid-value-message/_mixin.scss:74 Debug: (sassify) 🟩 └─ unset
	devpack/invalid-value-message/_mixin.scss:83 Debug: (sassify) 🟥 └⤬ centere
	```

> Таким образом мы в любом случае увидим ошибку, если она появится.
