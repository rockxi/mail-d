# Mail-D

Mail-D — это Python-программа для отправки сообщений из почтового ящика в общий чат Telegram. Эта программа использует IMAP для получения сообщений и Telegram Bot API для отправки сообщений в чат.

## Установка

Инструкция по установке: скопируй и вставь в терминал, далее следуем указаниям. Для работы приложения у вас уже должен быть установлен docker.


```bash
git clone https://github.com/blackrockxi37/mail-d
cd mail-d
bash build.sh
```

Так же, для использования вам пригодятся следующие значения:

- **username**: Ваш адрес электронной почты.
- **mail_pass**: Пароль для доступа к вашей почте (используется для IMAP).
- **imap_server**: IMAP сервер вашей почтовой службы.
- **chatid**: ID чата в Telegram, куда будут отправляться сообщения.
- **rockxi**: ID администратора бота для управления.
- **token**: Токен вашего бота Telegram, который вы можете получить у BotFather. 

## Запуск

Постройте Docker-образ и запустите его.
Чтобы запустить в режиме отладки (с выводом), а не в фоне, уберите ключ '-d'.

```bash
docker build -t mail-d .
docker run -d --restart always mail-d
```

## Использование

После настройки и запуска контейнера, программа будет автоматически отслеживать новые сообщения в указанном почтовом ящике и пересылать их в Telegram чат. 
Чтобы остановить выполнение, используйте:

```bash
docker ps
docker stop id_контейнера
```

## Примечания

- Убедитесь, что у вас установлен Docker и настроен правильно.
- Внимательно проверьте и обновите настройки в `hiddendata.py` перед запуском.
- Если у вас возникли проблемы с доступом к почте, проверьте настройки IMAP для вашей почтовой службы.

## Лицензия

Этот проект лицензируется под MIT License - подробности см. в [LICENSE](LICENSE).

## Контакты

Если у вас возникли вопросы или предложения, не стесняйтесь обращаться к разработчику через [GitHub Issues](https://github.com/blackrockxi37/mail-d/issues).
