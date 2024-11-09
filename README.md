<h1>Aiorm - лучший шаблон бота на AioGram с удобной ORM системой</h1>

<h2>Преимущества этого шаблона</h2>
Не нужно больше в каждом хендлере копировать запрос к базе данных. Система все сделает за вас, рассмотрим на простом примере:<br><br>

```python
@dp.message_handler(CommandStart())
async def bot_start(msg: types.Message, user: User) -> None:
    await msg.answer(f"👋 Привет, {msg.from_user.first_name}. Твой баланс {user.balance}")
```
Система сама добавляет всех новых пользователей в базу данных. Если моделе есть колонка balance, то стоит просто обратиться к этой переменной, не делая запроса вручную.<br>
Если мы захотим обновить баланс, к примеру, увеличить его на 500, то просто сделаем:<br>

```python
  user.balance += 500
  user.save()
```

<h2>Настройка</h2>
Укажите в файле .env токен от бота и список ID администраторов:

`botToken=123456789:ABCDEFGHIJKLMNOPQRSTUVWXYZ`<br>
`admins=123456789,987654321,111111111`

Чтобы перевести бота на mysql, укажите в .env:

`DBtype=mysql`<br>
`mysqlDatabase=name`<br>
`mysqlUser=admin`<br>
`mysqlPassword=12345678`

<h2>Запуск бота</h2>
Через терминал линукс:<br>

`pip3 install -r requirements.txt` (установка необходимых модулей) <br>
`python3 bot.py`

Через Docker:<br>
`chmod +x runbot.sh` (команда вводится один раз, в последующие запуски ее можно не вводить)<br>
`./runbot.sh` (подготовка и запуск контейнера с ботом)

<h2>Добавление новых колонок</h2>
Если вам понадобится добавить в таблицу Peewee новую колонку, то используйте migrator.py.
Его нужно запустить отдельно:<br>

`python3 migrator.py`


