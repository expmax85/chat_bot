# Общее описание проекта
В проекте представлена версия Telegram бота для поиска отелей по заданным критериям. Бот написан на языке Python v 3.9.5 на основе <a href="https://core.telegram.org/bots/api">PyTelegramBotAPI</a>, с использованием открытого API Hotels. Чтобы получить возможность работать с этим API, необходимо:
1. Зарегистрироваться на сайте <a href="https://rapidapi.com/">rapidapi.com</a>;
2. Перейти в API Marketplace → категория Travel → Hotels;
3. Нажать кнопку Subscribe to Test;
4. Выбрать бесплатный пакет (Basic).

# Используемые технологии и модули
+ request
+ pyTelegramBotAPI
+ SpeechRecognition
+ langdetect
+ telebot_calendar
+ python_dotenv

# Установка
```shell
git clone https://gitlab.skillbox.ru/maksim_semeniuk/python_basic_diploma.git
```
После выполнения команды clone переместиться в корень проекта и ввести команду:
```shell
pip install -r requirements.txt
```

Затем создайте файл .env на основе шаблона .env.template, вставьте ваш токен и APIHotels.

# Доступные команды
+ /start
+ /help
+ /lowprice
+ /highprice
+ /bestdeal
+ /history

## Команда /start
Базовая команда при первом контакте с ботом, а также для вывода приветственного сообщения.

## Команда /help
Команда для вывода доступных команд.

## Команда /lowprice
При вводе данной команды осуществляется поиск отелей по самым низким ценам.
После ввода команды у пользователя запрашивается:
1. Город, где будет проводиться поиск;
2. Даты заезда/выезда;
3. Количество отелей, которые необходимо вывести в результате (не больше 25);
4. Валюта, в которой будут отображены цены;
5. По выбору пользователя - вывод фотографий отеля (не больше 10).

## Команда /highprice
При вводе данной команды осуществляется поиск отелей по самым высоким ценам.
После ввода команды у пользователя запрашивается:
1. Город, где будет проводиться поиск;
2. Даты заезда/выезда;
3. Количество отелей, которые необходимо вывести в результате (не больше 25).
4. Валюта, в корторой будут отображенеы цены;
5. По выбору пользователя - вывод фотографий отеля (не больше 10).

## Команда /bestdeal
При вводе данной команды осуществляется поиск по дополнительым критериям, заданным пользователем, в частности по диапазону цен и расстоянию от центра города.
После ввода команды у пользователя запрашивается:
1. Город, где будет проводиться поиск;
2. Даты заезда/выезда;
3. Количество отелей, которые необходимо вывести в результате (не больше 25);
4. Валюта, в корторой будут отображенеы цены;
5. Диапазон цен;
6. Диапазон расстояния, на котором находится отель от центра;
7. По выбору пользователя - вывод фотографий отеля (не больше 10).

## Команда /history
Выводит историю запросов пользователя по вышеназванным командам.

# Обработка голосовых команд
Бот оснащен функцией распознавания голоса, и пользователь имеет возможность отдавать голосовые команды и отправлять голосовые сообщения, если бот не предлагает интерактивый выбор вариантов(выбор города из списка, выбор валюты, выбор дат заезда/выезда).
Для использования данной функции необходимо скачать конвертер ffmpeg <a href="https://github.com/BtbN/FFmpeg-Builds/releases/download/autobuild-2021-09-24-12-21/ffmpeg-n4.4-154-g79c114e1b2-win64-gpl-4.4.zip">отсюда</a>, и поместить файл bin/ffmpeg.exe в папку со скриптом main.py.
