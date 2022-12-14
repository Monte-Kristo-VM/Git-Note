# My Git

## Первый шаг
---
После первой установки git необходимо ему представиться:

    git config --global user.name <Ваше Имя> Ввести ваш Ник

    git config --global user.email <Ваша почта@...> Ввести вашу почту

Имя и почта могут быть не существующие, но лучше ввести реальные для простоты дальнейшей идентификации автора.

---
## Начало работы
---
Создаем папку и заходим в нее (либо открываем существующую). Для того, чтобы git начал отслеживать изменения в ней, необходимо его инициализировать в этой папке. Делается это командой

    git init

Если в папке ничего нет, то будет создан пустой репозиторий. В этой папке можно создать файлы с любым расширением. После этого можно воспользоваться командой 

    git status

которая отобразит состояние рабочего каталога (нашей созданой папки).

Далее воспользуемся командой

    git add <Имя файла>

для добавления файла в контроль версий с целью последующего сохранения (commit-а). При вводе имени файла достаточно ввести первые несколько символов из названия и нажать клавишу TAB, имя допишется автоматически.

Для добавления сразу нескольких файлов будет полезна команда

    git add .

После внесения в файл каких-либо первоначальных изменений самое время сохраниться:

    git commit -m "Комментарий к текущему commit-у"
---
## Работа с commit-ами
---
После того, как мы сделали несколько сохранений (commit-ов), возникает потребность переключения между ними. Для этого необходимо знать, какие commit-ы у нас имеются:

    git log

отобразит всю историю сохранений. Если сохранений много и они не помещаются на экране терминала, то воспользуйтесь клавишами стрелок  ВВЕРХ и ВНИЗ для перемещения между commit-ами. После окончания просмотра нажмите клавишу q (возможна и другая клавиша или сочетание клавиш, в зависимости от используемой программы). Также вам будет полезна комманда _clear_ для очистки экрана терминала.

Для переключения между commit-ами используем комманду:

    git checkout <номер commit-а>

в номере достаточно указать первые 4 символа, в большинстве случаев они однозначно определяют конкретный commit.

Чтобы вернуться в главную ветку в последнюю версию, воспользуемся командой:

    git checkout master

Возможно на понадобится сравнить две версии. Разницу между ними можно увидеть при помощи команды

    git diff

---
## Branch = ветка. Работа с ними.
---

    git branch - выводит список всех веток

Для перемещения по веткам, используется команда

    git chekout <Имя ветки>

Создание новой ветки можно выполнить следующим образом:

    git branch <Имя новой ветки>

или другим способом

    git checkout -b <Имя новой ветки> - создает новую ветку и переходит на нее.

Чтобы в текущую ветку добавить другую ветку, необходимо выполнить каманду:

    git merge <Имя добавляемой ветки>

Добавляемая ветка предварительно должна быть сохранена.

Для удаления какой-либо ветки используется команда

    git branch -d <Имя удаляемой ветки>

---
## Игнорирование отслеживания файла
---
Для того, чтобы определенные файлы не отслеживались в контроле версий при сохранении, необходимо создать новый файл с названием __*.gitignore*__ и в него внести имена тех файлов, которые необходимо игнорировать. Далее необходимо это файл за-commit-ить

    git add .gitignore
    git commit
Например, это может быть использованно для изображений и других неизменяемых файлов.

---
## Работа с удаленным репозиторием. [GitHub](https://github.com/)
---
GitHub — веб-сервис, который основан на системе Git. Это такая социальная сеть для разработчиков, которая помогает удобно вести коллективную разработку IT-проектов. Здесь можно публиковать и редактировать свой код, комментировать чужие наработки, следить за новостями других пользователей.

Git и GitHub - это две разные вещи. Git - это программа на вашем компьютере, а GitHub - это сервис, который позволяет интегрироваться с программой Git и настроить удаленную работу с вашим репозиторием.

Для копирования удаленного репозитория в локальный (на ваш компьютер),
необходимо воспользоваться командой

    git clone <адрес удаленного репозитория>

Для обратной операции (локальный репозиторий -> удаленный репозиторий) необходимо зарегистрироваться и создать удаленный репозиторий, например на GitHub.com
При первом обращении будет необходимо пройти авторизацию, чтобы получить возможность вносить какие-либо изменения в удаленный репозиторий.

Чтобы скопировать все изменения с удаленного репозитория на локальный:
    
    git pull <адрес удаленного репозитория>

Процесс очень похож на клонирование репозитория, но здесь скачиваются не все коммиты, а только новые.

Для обратного действия, когда нужно отправить изменения с локального на удаленный репозиторий, используется команда

    git push <адрес удаленного репозитория>
---
## Участие в других проектах
---
Для участия в проекте другого репозитория необходимо проделать следующие действия

* Сделать копию (FORK) в совой аккаунт удаленного репозитория
* Скопировать все это в локальный репозиторий на свой компьютер
 
        git clone <адрес удаленного репозитория>

* Создать новую ветку для внесения изменений
* Произвести необходимые изменения, закомитить их и отправить на удаленный репозиторий
    
        git push <адрес удаленного репозитория>

* Создать пул-реквест при помощи кнопки «Compare & pull request»
* Надеяться, что ваши изменения понравятся авторам :) 

---
## Интерактивный тренажер по Git
[LeanCitBranchin](https://learngitbranching.js.org/?locale=ru_RU)
---