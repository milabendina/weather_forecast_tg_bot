# weather_forecast_tg_bot
Телеграм-бот, который распознаёт вопросы о том, какая сегодня погода в том или ином городе и выдаваёт информацию о погоде.


Для распознавания человеческой речи я выбрала фреймворк DialogFlow, который также имеет встроенный в него ML.

Бот распознаёт русскую и английскую речь.

![Dialogflow - Google Chrome 11_23_2021 5_25_42 PM (3)](https://user-images.githubusercontent.com/65489941/143042569-6d8847b7-5c94-4288-a544-7ce664ce4c86.png)

Вот примеры тренировочных фраз, которые распознаёт бот:

![Dialogflow - Google Chrome 11_23_2021 5_38_44 PM (2)](https://user-images.githubusercontent.com/65489941/143044586-e4770f67-a4a1-48a6-b15b-eafc803ce3ee.png)



Для получения информации о погоде мною был выбран OpenWeather API.
Кроме того, поскольку информация о погоде в этом API выдается по параметрам latitude и longitude — ширина и долгота — мне необходимо было как-то преобразовывать город в его ширину и долготу. В этом мне помогла Python-библиотека geopy.

Я использовала Flask, чтобы написать роут, по которому осуществляется переход в само приложение.

Программа лежала на нашей локальной машине, но DialogFlow о ней ничего не знает. Чтобы превратить её в сервер, который станет доступен в интернете, нужна особая утилита. Этим требованиям соответствует ngrok.

Вот так выглядит весь код программы:

![main py - weather_forecast_tg_bot - Visual Studio Code 11_23_2021 5_35_03 PM](https://user-images.githubusercontent.com/65489941/143043903-36128428-8b61-4ee6-8dd2-d17889efe819.png)

А вот так собственно бот и работает:
