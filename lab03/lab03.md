# Отчёт о выполнении лабораторной работы №3 Управление версиями
## цель работы 
Изучить идеологию и применение средств контроля версий.
## Задание 
1. Настройка git
- Создайте учётную запись на https://github.com.
- Настройте систему контроля версий git, как это описано выше c использованием
сервера репозиториев https://github.com/.
- Создайте структуру каталога лабораторных работ согласно пункту М.2.
2. Подключение репозитория к github
– Создайте репозиторий на GitHub. Для примера назовём его os-intro.
– Рабочий каталог будем обозначать как laboratory. Вначале нужно перейти в этот
каталог:
cd laboratory
– Инициализируем системы git:
git init
– Создаём заготовку для файла README.md:
echo "# Лабораторные работы" >> README.md
git add README.md
– Делаем первый коммит и выкладываем на github:
git commit -m "first commit"
git remote add origin
↪ git@github.com:<username>/sciproc-intro.git
git push -u origin master
3. Первичная конфигурация
– Добавим файл лицензии:
wget https://creativecommons.org/licenses/by/4.0/legalcode.txt
↪ -O LICENSE
– Добавим шаблон игнорируемых файлов. Просмотрим список имеющихся шаблонов:
curl -L -s https://www.gitignore.io/api/list
Затем скачаем шаблон, например, для C:
curl -L -s https://www.gitignore.io/api/c >> .gitignore
Можно это же сделать через web-интерфейс на сайте https://www.gitignore.
io/.
– Добавим новые файлы:
git add .
– Выполним коммит:
git commit -a
– Отправим на github:
git push
4. Конфигурация git-flow
– Инициализируем git-flow
git flow init
Префикс для ярлыков установим в v.
– Проверьте, что Вы на ветке develop:
git branch
– Создадим релиз с версией 1.0.0
Кулябов Д. С. и др. Операционные системы 21
git flow release start 1.0.0
– Запишем версию:
echo "1.0.0" >> VERSION
– Добавим в индекс:
git add .
git commit -am 'chore(main): add version'
– Зальём релизную ветку в основную ветку
git flow release finish 1.0.0
– Отправим данные на github
git push --all
git push --tags
– Создадим релиз на github.
## Выполнение работы

## Вывод
> Изучила идеологию и применение средств контроля версий.
