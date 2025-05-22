# Домашнее задание к занятию "Системы контроля версий" - Колесин Владимир

Создаем репозиторий на Github.com

![alt text](https://github.com/Villigun/netology-02-git-01-vcs/blob/main/img/img1-02.png)

и генерируем токен, который сохраняем в файле token.txt, который позже добавим в .gitignore

![alt text](https://github.com/Villigun/netology-02-git-01-vcs/blob/main/img/img1-01.png)

Создаем каталог для будущего репозитория:  

```
PS C:\Users\doom\Desktop\DZ> cd .\netology-02-git-01-vcs\
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git init
```

Проверяем настройки:  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git config --global user.name
Villigun
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git config --global user.email
kolessinv@yandex.ru

PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        img/
        token.txt

nothing added to commit but untracked files present (use "git add" to track)
```

Клонируем репозиторий с github:  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git clone https://github.com/Villigun/netology-02-git-01-vcs.git
Cloning into 'netology-02-git-01-vcs'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.
```

Поскольку при клонировании создался каталог .\netology-02-git-01-vcs\netology-02-git-01-vcs, переносим  
файл README.md на уровень выше в .\netology-02-git-01-vcs.  
*Скорее всего из-за этой операции будет потерян 'Initial commit'*  

Создаем файл .gitignore, куда записываем имя файла token.txt, в котором хранится токен авторизации.  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git status  
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        README.md
        img/

nothing added to commit but untracked files present (use "git add" to track)
```

Вносим изменения в файл README.md  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        README.md
        img/

nothing added to commit but untracked files present (use "git add" to track)
```

Как видим, ничего не изменилось, по причине того, что файлы не добавлены в отлеживание.  
Добавляем:  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git add *
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
        new file:   README.md
        new file:   img/img1-01.png
        new file:   img/img1-02.png
```

Повторно вносим изменения в README.md и проверяем:  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
        new file:   README.md
        new file:   img/img1-01.png
        new file:   img/img1-02.png

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md
```

Состояние фала README.md изменилось на modified.  
Выполняем п10 задания, редактируя README.md и проверяя командами git diff и git diff --staged:  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git diff
diff --git a/README.md b/README.md
index 390c05d..6219fc7 100644
--- a/README.md
+++ b/README.md
@@ -1,3 +1,7 @@
 # netology-02-git-01-vcs

-Превед медвед
\ No newline at end of file
+Превед медвед!
+
+Сам Превед!
+
+Чё началось то? Нормально же общались!
\ No newline at end of file
```

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git diff --staged
diff --git a/.gitignore b/.gitignore
new file mode 100644
index 0000000..77b3ac2
--- /dev/null
+++ b/.gitignore
@@ -0,0 +1 @@
+token.txt
\ No newline at end of file
diff --git a/README.md b/README.md
new file mode 100644
index 0000000..390c05d
--- /dev/null
+++ b/README.md
@@ -0,0 +1,3 @@
+# netology-02-git-01-vcs
+
+Превед медвед
\ No newline at end of file
diff --git a/img/img1-01.png b/img/img1-01.png
new file mode 100644
index 0000000..794ee55
Binary files /dev/null and b/img/img1-01.png differ
diff --git a/img/img1-02.png b/img/img1-02.png
new file mode 100644
index 0000000..5c10419
Binary files /dev/null and b/img/img1-02.png differ
(END)
--- /dev/null
+++ b/.gitignore
@@ -0,0 +1 @@
+token.txt
\ No newline at end of file
diff --git a/README.md b/README.md
new file mode 100644
index 0000000..390c05d
--- /dev/null
+++ b/README.md
@@ -0,0 +1,3 @@
+# netology-02-git-01-vcs
+
+Превед медвед
\ No newline at end of file
diff --git a/img/img1-01.png b/img/img1-01.png
new file mode 100644
index 0000000..794ee55
Binary files /dev/null and b/img/img1-01.png differ
diff --git a/img/img1-02.png b/img/img1-02.png
new file mode 100644
index 0000000..5c10419
Binary files /dev/null and b/img/img1-02.png differ
--- /dev/null
+++ b/.gitignore
@@ -0,0 +1 @@
+token.txt
\ No newline at end of file
diff --git a/README.md b/README.md
new file mode 100644
index 0000000..390c05d
--- /dev/null
+++ b/README.md
@@ -0,0 +1,3 @@
+# netology-02-git-01-vcs
+
+Превед медвед
\ No newline at end of file
diff --git a/img/img1-01.png b/img/img1-01.png
new file mode 100644
index 0000000..794ee55
Binary files /dev/null and b/img/img1-01.png differ
diff --git a/img/img1-02.png b/img/img1-02.png
new file mode 100644
index 0000000..5c10419
Binary files /dev/null and b/img/img1-02.png differ
```

Как видим команда git diff показывает сразу все изменения между рабочей директорией и satging area,  
а команда git diff --staged показывает разницу между staged area и последним коммитом.  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git add README.md
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> 
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git status       
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
        new file:   README.md
        new file:   img/img1-01.png
        new file:   img/img1-02.png

PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git diff
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git diff --staged
diff --git a/.gitignore b/.gitignore
new file mode 100644
index 0000000..77b3ac2
--- /dev/null
+++ b/.gitignore
@@ -0,0 +1 @@
+token.txt
\ No newline at end of file
diff --git a/README.md b/README.md
new file mode 100644
index 0000000..6219fc7
--- /dev/null
+++ b/README.md
@@ -0,0 +1,7 @@
+# netology-02-git-01-vcs
+
+Превед медвед!
+
+Сам Превед!
+
+Чё началось то? Нормально же общались!
\ No newline at end of file
diff --git a/img/img1-01.png b/img/img1-01.png
new file mode 100644
index 0000000..794ee55
Binary files /dev/null and b/img/img1-01.png differ
diff --git a/img/img1-02.png b/img/img1-02.png
new file mode 100644
index 0000000..5c10419
Binary files /dev/null and b/img/img1-02.png differ
```

Выполняем первый коммит:  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git commit -m 'Commit 01'
[master (root-commit) e4ccbbd] Commit 01
 4 files changed, 8 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 README.md
 create mode 100644 img/img1-01.png
 create mode 100644 img/img1-02.png
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git diff                 
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git diff --staged
```

Все файлы были актуализированы.  

Создаем каталог terraform и в ней файл .gitignore. Добавляем в .gitignore файлы из задания.  
Не будут отслеживаться каталог .terraform/ и его содержимое;  
все файлы в названии которых содержится .tfstate;  
файлы crash.log, override.tf, override.tf.json, .terraform.tfstate.lock.info, .terraformrc, terraform.rc;  
файлы, имена которых начинаются на crash. и заканчиваются на .log;  
файлы, имена которых заканчиваются на *.tfvars и .tfvars.json;  
файлы, имена которых заканчиваются на _override.tf и _override.tf.json  

Делаем коммит с комментарием 'Added gitignore':  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git add *
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git commit -m 'Added gitignore'
[master 7ae12ce] Added gitignore
 1 file changed, 37 insertions(+)
 create mode 100644 terraform/.gitignore
 ```

Создаем файлы will_be_deleted.txt и will_be_moved.txt, записываем в них текст.  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git add *    
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git commit -m 'Prepare to delete and move'
[master 3b87ed2] Prepare to delete and move
 2 files changed, 2 insertions(+)
 create mode 100644 will_be_deleted.txt
 create mode 100644 will_be_moved.txt
```

Затем удаляем will_be_deleted.txt, а will_be_moved.txt переименовываем в has_been_moved.txt.  

```
PS C:\Users\doom\Desktop\DZ\netology-02-git-01-vcs> git commit -am 'Moved and deleted'
[master 415c23e] Moved and deleted
 2 files changed, 2 deletions(-)
 delete mode 100644 will_be_deleted.txt
 delete mode 100644 will_be_moved.txt

git log
commit 415c23e927b18f88720577eeb2819864658f72c2 (HEAD -> master)
Author: Villigun <kolessinv@yandex.ru>
Date:   Thu May 22 14:01:35 2025 +0500

    Moved and deleted

commit 3b87ed28225e9bcfa62bc4567a5730893ab543e3
Author: Villigun <kolessinv@yandex.ru>
Date:   Thu May 22 13:57:27 2025 +0500

    Prepare to delete and move

commit 7ae12cea91722ef06b4141fea69d2f943da653ba
Author: Villigun <kolessinv@yandex.ru>
Date:   Thu May 22 12:07:15 2025 +0500

    Added gitignore

commit e4ccbbded8d704206807e1e1d59b5d26194aebb7
Author: Villigun <kolessinv@yandex.ru>
Date:   Thu May 22 11:42:27 2025 +0500

    Commit 01
```

*Как и предполагалось в начале задания, из-за переноса файла README.md потерялся Initial Commit*

Вносим этот ^ текст в README.md, выполняем коммит и пушим на github.