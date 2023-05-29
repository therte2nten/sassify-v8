# Кастомизация и логика Sassify
Sassify включает в себя большое количество Sass-переменных, которые позволяют внести изменения в поведение Sassify.

Например, переменная `$vvalues--justify-content` определяет допустимые значения для миксина `justify-content`. Эти переменные можно переопределять:

```scss
@use '../../node_modules/@therteenten/sassify' as sassify with (
	$vvalues--justify-content: center start end flex-start flex-end left right baseline (first baseline) (last baseline) space-between space-around space-evenly stretch (safe center) (unsafe center) inherit initial unset
);
```

Или мы можем переопределить значение по умолчанию для миксина `justify-content`, которое сейчас является `flex-start`. Давайте переопределим стандартное значение миксина `justify-content` на `baseline`:

```scss
@use '../../node_modules/@therteenten/sassify' as sassify with (
	$dvalues--justify-content: baseline
);

.justify-baseline {
	@include sassify.justify-content();
}
```
```css
/* CSS */
.justify-baseline {
  -webkit-justify-content: baseline;
  justify-content: baseline;
}
```

Но если мы установим значение по умолчанию, которого нет в списке `$vvalues--justify-content`, то Sassify выдаст нам ошибку:

```scss
@use '../../node_modules/@therteenten/sassify' as sassify with (
	$dvalues--justify-content: fake-value
);

.justify-baseline {
	@include sassify.justify-content();
}
```
```css
/* CSS */
.justify-baseline {
  /* (sassify) 🟧 Миксин «justify-content» не может принимать значение «fake-value»! */
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
  /* (sassify) 🟥 └⤬ fake-value */
}
```

> Также, если у вас не переопределена переменная `$setting--strict-mode`, то в консоли вы также увидите сообщение об ощибке, а также прекратится компиляция Sass в CSS. Например:
> ```sh
> [2023-05-27 18:30] Compiled _test.scss to test.css.
> Error: "🟥 Миксин «justify-content» не может принимать значение «fake-value»! Допустимые значения миксина: center start end flex-start flex-end left right baseline first baseline last baseline space-between space-around space-evenly stretch safe center unsafe center inherit initial unset"
>    ╷
> 52 │ ┌         @include invalid-value-message(
> 53 │ │             'justify-content',
> 54 │ │             $value,
> 55 │ │             config.$vvalues--justify-content
> 56 │ │         );
>    │ └─────────^
>    ╵
>   core/cssex/justify/_content.scss 52:3  justify-content()
>   _test.scss 38:2
> ```

## Основные типы переменных
В Sassify переменные разделены на тип настройки, за которые они отвечают.

- [Default Values](https://github.com/therteenten/sassify/blob/main/config/_default-values.scss) (`$dvalues--*`) - значения по умолчанию для функций и миксинов
- [Valid Values](https://github.com/therteenten/sassify/blob/main/config/_valid-values.scss) (`$vvalues--*`) - допустимые значения миксинов и функций
- [Strings](https://github.com/therteenten/sassify/blob/main/config/_strings.scss) (`$string--*`) - строки сообщений ошибок или отладки
- [Prefixes](https://github.com/therteenten/sassify/blob/main/config/_prefixes.scss) (`$prefixes--*`) - список префиксов для тех или иных CSS-свойств
- [Settings](https://github.com/therteenten/sassify/blob/main/config/_index.scss) (`$setting--*`) - глобальные настройки непосредственно Sassify
