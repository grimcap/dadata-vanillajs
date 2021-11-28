# dadata-vanillajs
Библиотека [DaData](https://dadata.ru/api/suggest/) на чистом js

[Оригинальная библиотека](https://www.npmjs.com/package/@dadata/suggestions) обещает версию 20.11.2 - самое новое, что нашел
(сейчас версия [jQuery-плагина](https://www.npmjs.com/package/suggestions-jquery) - 21.8.0)

Пришлось немного подправить вывод выпадающего списка

Подключение:
1. Подключаем файл с библиотекой
2. suggestions.init(input_element, {dadatda_options})

Например:

	const ddtoken = 'respectful_token';
	const input_element = document.getElementById('respectful_input');

	try {

	suggestions.init(input_element, {
		token: ddtoken,
		type: "ADDRESS",
		hint: false,
		bounds: "city",
		onSelect: (suggestion) => {
			let region = suggestion.data.region_iso_code;
			let sCity = suggestion.data.city;
			// и т.д.
		}
	});

	} catch (err) {
		console.error(err)
	}
