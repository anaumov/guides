# Как делается релиз (v0.3)

* Работаем в ветке develop.
* Инкрементим версию релиза (composite.json, package.json)
* Ветка develop выкатывается на staging
* Тестирование: На staging проверяются все изменения которые выполнены по задачам вошедшим в develop
* Если нужны правки - их делают в develop и переходят на пунк (2).
* Если все OK - идем дальше.
* Вливаем develop -> master. В комментарии к merge commit-у указываем номера задач, которые выкатываются (их можно взять из commit messages)
* Открываем на целевом сервере консоль с логами nginx, php и cron
* Выкатываем на боевой (bundle exec cap production deploy)
* Смотрим в оба глаза на логи (cron.log, php.log (nginx errors.log))
* Проверяем публичную часть, операторскую.
* Если все OK - жмем в трекере на релизе и на выкатившихся задачах кнопку `delivery`
