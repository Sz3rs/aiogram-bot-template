<h1>Шаблон бота на Aiogram</h1>

Укажите в файле .env токен от бота и список ID администраторов:

`botToken=123456789:ABCDEFGHIJKLMNOPQRSTUVWXYZ`<br>
`admins=123456789,987654321,111111111`

<h2>Запуск бота</h2>
Через консоль линукс:<br>

`pip3 install -r requirements.txt`<br>
`python3 bot.py`

Через Docker:<br>
`chmod +x runbot.sh` (команда вводится один раз, в последующие запуски ее можно не вводить)<br>
`./runbot.sh` (подготовка и запуск контейнера с ботом)
