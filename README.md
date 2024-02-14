Zadanie 1
• Utwórz katalog repo1 zawierający dwa pliki tekstowe z dowolną, rożną
zawartością
• Utwórz w tym katalogu repozytorium git i sprawdź jego stan (status)
• Dodaj do niego wszystkie pliki z tego katalogu i sprawdź stan repozytorium
• Zakomituj zmiany i sprawdź stan repozytorium
singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT (master)
$ mkdir repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT (master)
$ cd repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ echo "Plik 1" > plik1.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ echo "Plik 2" > plik2.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git init
Initialized empty Git repository in C:/Users/singhet/OneDrive - The Timken Company/Pulpit/GIT/repo1/.git/

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        plik1.txt
        plik2.txt

nothing added to commit but untracked files present (use "git add" to track)

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git add .
warning: in the working copy of 'plik1.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'plik2.txt', LF will be replaced by CRLF the next time Git touches it

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   plik1.txt
        new file:   plik2.txt


singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git commit -m "Dodano nowe pliki"
[master (root-commit) 300b421] Dodano nowe pliki
 2 files changed, 2 insertions(+)
 create mode 100644 plik1.txt
 create mode 100644 plik2.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master
nothing to commit, working tree clean


Zadanie 2
• W repo1 zmodyfikuj zawartość jednego z plików
• Sprawdź stan repozytorium
• Zmodyfikuj zawartość drugiego z plików
• Wyświetl tę różnicę tylko dla jednego z plików
• Zakomituj zmiany
• Wyświetl historię zmian w repozytorium

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ echo "Zawartość zmodyfikowana 1" > plik1.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   plik1.txt

no changes added to commit (use "git add" and/or "git commit -a")

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ echo "Zawartość zmodyfikowana 2" > plik2.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   plik1.txt
        modified:   plik2.txt

no changes added to commit (use "git add" and/or "git commit -a")

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git diff plik1.txt
warning: in the working copy of 'plik1.txt', LF will be replaced by CRLF the next time Git touches it
diff --git a/plik1.txt b/plik1.txt
index da4a6e4..c454319 100644
--- a/plik1.txt
+++ b/plik1.txt
@@ -1 +1 @@
-Plik 1
+Zawartość zmodyfikowana 1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git add .
warning: in the working copy of 'plik1.txt', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'plik2.txt', LF will be replaced by CRLF the next time Git touches it

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git commit -m "Zmodyfikowano pliki"
[master b10b7a1] Zmodyfikowano pliki
 2 files changed, 2 insertions(+), 2 deletions(-)

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git log
commit b10b7a1b12c3bbae80864361083df12e4c84d51b (HEAD -> master)
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 08:26:35 2024 +0100

    Zmodyfikowano pliki

commit 300b421d3f6d0fd9c44867ec9c4dd6d320166251
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 08:11:13 2024 +0100

    Dodano nowe pliki

Zadanie 3
• Sklonuj repozytorium repo1 jako repo2

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ cd ..

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT (master)
$ git clone repo1 repo2
Cloning into 'repo2'...
done.

Zadanie 4
Działając w repo2:
• Usuń z repozytorium jeden z plików tekstowych
• Zmień nazwę drugiego z plików tekstowych
• Sprawdź stan repozytorium
• Zakomituj zmiany
• Wyświetl historię zmian w repozytorium, z pokazaniem informacji o nazwach
zmienianych plików

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT (master)
$ cd repo2

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ rm plik1.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    plik1.txt

no changes added to commit (use "git add" and/or "git commit -a")

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ mv plik2.txt tekst2.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    plik1.txt
        deleted:    plik2.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        tekst2.txt

no changes added to commit (use "git add" and/or "git commit -a")

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git add .

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git commit -m "Usunięto jeden plik i zmieniono nazwę drugiego"
[master 5e418bf] Usunięto jeden plik i zmieniono nazwę drugiego
 2 files changed, 1 deletion(-)
 delete mode 100644 plik1.txt
 rename plik2.txt => tekst2.txt (100%)

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git log --name-status
commit 5e418bf7efe6dff28cbb76ace923f6c1106b7531 (HEAD -> master)
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 08:44:50 2024 +0100

    Usunięto jeden plik i zmieniono nazwę drugiego

D       plik1.txt
R100    plik2.txt       tekst2.txt

commit b10b7a1b12c3bbae80864361083df12e4c84d51b (origin/master, origin/HEAD)
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 08:26:35 2024 +0100

    Zmodyfikowano pliki

M       plik1.txt
M       plik2.txt

commit 300b421d3f6d0fd9c44867ec9c4dd6d320166251
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 08:11:13 2024 +0100

    Dodano nowe pliki

A       plik1.txt
A       plik2.txt

Zadanie 5
• Zaktualizuj stan repo1, tak aby odzwierciedlał zmiany dokonane w repo2

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ cd ..

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT (master)
$ cd repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git pull ../repo2 master
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (1/1), done.
remote: Total 2 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (2/2), 251 bytes | 20.00 KiB/s, done.
From ../repo2
 * branch            master     -> FETCH_HEAD
Updating b10b7a1..5e418bf
Fast-forward
 plik1.txt               | 1 -
 plik2.txt => tekst2.txt | 0
 2 files changed, 1 deletion(-)
 delete mode 100644 plik1.txt
 rename plik2.txt => tekst2.txt (100%)

Zadanie 6
• Zmodyfikuj plik tekstowy zarówno w repo1 i w repo2 w sprzeczny sposób
• Zakomituj zmiany w repo1 i w repo1
• Spróbuj zaktualizować stan repo1, tak aby odzwierciedlał zmiany dokonane w
repo2
• Sprawdź stan repozytorium
• Rozwiąż konflikt
• Sprawdź stan repozytorium
• Wyświetl historię zmian pokazującą wykres gałęzi w których były dokonywane
zmiany
• Spróbuj zaktualizować stan repo2, tak aby odzwierciedlał zmiany dokonane w
repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ echo "Zmiana repo1" > tekst2.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ cd ../repo2

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ echo "Zmiana repo2" > tekst2.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ cd ../repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git add .
warning: in the working copy of 'tekst2.txt', LF will be replaced by CRLF the next time Git touches it

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git commit -m "Zmiana repo1"
[master 5b7776a] Zmiana repo1
 1 file changed, 1 insertion(+), 1 deletion(-)

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ cd ../repo2

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git add .
warning: in the working copy of 'tekst2.txt', LF will be replaced by CRLF the next time Git touches it

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git commit -m "Zmiana repo2"
[master ed30138] Zmiana repo2
 1 file changed, 1 insertion(+), 1 deletion(-)

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ cd ../repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git pull ../repo2
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 237 bytes | 15.00 KiB/s, done.
From ../repo2
 * branch            HEAD       -> FETCH_HEAD
Auto-merging tekst2.txt
CONFLICT (content): Merge conflict in tekst2.txt
Automatic merge failed; fix conflicts and then commit the result.

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master|MERGING)
$ git add .

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master|MERGING)
$ git commit -m "Konflikt rozwiązany"
[master af53ab3] Konflikt rozwiązany

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git log
commit af53ab3469e669ffbe19da418e65515516d5383b (HEAD -> master)
Merge: 5b7776a ed30138
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 09:47:45 2024 +0100

    Konflikt rozwiązany

commit ed3013857ceb554dc55166a48d5acad201f2422b
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 09:30:52 2024 +0100

    Zmiana repo2

commit 5b7776a04c664a50e4cd3fb5cc9db60b1fee29e9
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 09:26:33 2024 +0100

    Zmiana repo1

commit 5e418bf7efe6dff28cbb76ace923f6c1106b7531
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 08:44:50 2024 +0100

    Usunięto jeden plik i zmieniono nazwę drugiego

commit b10b7a1b12c3bbae80864361083df12e4c84d51b
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 08:26:35 2024 +0100

    Zmodyfikowano pliki

commit 300b421d3f6d0fd9c44867ec9c4dd6d320166251
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 08:11:13 2024 +0100

    Dodano nowe pliki

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ cd ../repo2

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git pull ../repo1 master
remote: Enumerating objects: 10, done.
remote: Counting objects: 100% (10/10), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 6 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 560 bytes | 20.00 KiB/s, done.
From ../repo1
 * branch            master     -> FETCH_HEAD
Updating ed30138..af53ab3
Fast-forward
 tekst2.txt | 4 ++++
 1 file changed, 4 insertions(+)

Zadanie 7
• Przywrócić stan kopii roboczej do stanu repozytorium sprzed zadania 6.
sprawdź stan repozytorium
• Wyświetl zawartość pliku modyfikowanego w zadaniu 6
• Powróć do normalnego stanu repozytorium
• Sprawdź stan repozytorium

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ cd ../repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git checkout HEAD~1
Note: switching to 'HEAD~1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 5b7776a Zmiana repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 ((5b7776a...))
$ git status
HEAD detached at 5b7776a
nothing to commit, working tree clean

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 ((5b7776a...))
$ cat tekst2.txt
Zmiana repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 ((5b7776a...))
$ git checkout HEAD

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 ((5b7776a...))
$ git status
HEAD detached at 5b7776a
nothing to commit, working tree clean

Zadanie 8
• Wyświetl zawartość pliku modyfikowanego w 6 przed dokonaniem tych
modyfikacji bez przełączania kopii roboczej na ówczesny stan repozytorium

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 ((5b7776a...))
$ git show HEAD~1:tekst2.txt
Zawartość zmodyfikowana 2

Zadanie 9
• Wyświetl różnicę stanu obecnego pliku modyfikowanego w 6 i stanu przed
dokonaniem tych modyfikacji

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 ((5b7776a...))
$ git diff HEAD~1 HEAD tekst2.txt
diff --git a/tekst2.txt b/tekst2.txt
index 0ff26df..8eda8c9 100644
--- a/tekst2.txt
+++ b/tekst2.txt
@@ -1 +1 @@
-Zawartość zmodyfikowana 2
+Zmiana repo1

Zadanie 10
• Utwórz nowy branch w repo1 o nazwie test i przełącz się na niego
• Zmodyfikuj plik tekstowy w ramach tego brancha i zakomituj zmiany
• Wyświetl informacje na temat branchy
• Wróć do domyślnej gałęzi „master” i wyświetl zawartość modyfikowanego pliku
oraz stan repozytorium

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 ((5b7776a...))
$ cd ../repo1

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 ((5b7776a...))
$ git checkout master
Previous HEAD position was 5b7776a Zmiana repo1
Switched to branch 'master'

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git checkout -b test
Switched to a new branch 'test'

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (test)
$ echo "Zmiana w nowym branchu" > test2.txt

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (test)
$ git commit -m "Zmiana w branchu test"
On branch test
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test2.txt

nothing added to commit but untracked files present (use "git add" to track)

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (test)
$ git branch
  master
* test

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (test)
$ git checkout master
Switched to branch 'master'

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ cat tekst2.txt
<<<<<<< HEAD
Zmiana repo1
=======
Zmiana repo2
>>>>>>> ed3013857ceb554dc55166a48d5acad201f2422b

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test2.txt

nothing added to commit but untracked files present (use "git add" to track)

Zadanie 11
• Zaciągnij zmiany dokonane w zadaniu 10 z repo1 do repo2 tak aby znalazły się
one w brachu o nazwie test
• wyświetl stan repozytorium, informacje na temat branchy oraz dwa najnowsze
wpisy z historii repozytorium


singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo1 (master)
$ cd ../repo2

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git pull ../repo1 test
From ../repo1
 * branch            test       -> FETCH_HEAD
Already up to date.

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git branch
* master

singhet@SCSWL4072 MINGW64 ~/OneDrive - The Timken Company/Pulpit/GIT/repo2 (master)
$ git log -n 2
commit af53ab3469e669ffbe19da418e65515516d5383b (HEAD -> master)
Merge: 5b7776a ed30138
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 09:47:45 2024 +0100

    Konflikt rozwiązany

commit ed3013857ceb554dc55166a48d5acad201f2422b
Author: KarolinaS <kac.karolina@gmail.com>
Date:   Tue Feb 13 09:30:52 2024 +0100

    Zmiana repo2
