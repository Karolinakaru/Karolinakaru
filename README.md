Zadanie 1
• Utwórz katalog repo1 zawierający dwa pliki tekstowe z dowolną, rożną
zawartością
• Utwórz w tym katalogu repozytorium git i sprawdź jego stan (status)
• Dodaj do niego wszystkie pliki z tego katalogu i sprawdź stan repozytorium
• Zakomituj zmiany i sprawdź stan repozytorium
$ mkdir repo1
$ cd repo1
$ echo "Plik 1" > plik1.txt
$ echo "Plik 2" > plik2.txt
$ git init
$ git status
$ git add .
$ git status
$ git commit -m "Dodano nowe pliki"
$ git status


Zadanie 2
• W repo1 zmodyfikuj zawartość jednego z plików
• Sprawdź stan repozytorium
• Zmodyfikuj zawartość drugiego z plików
• Wyświetl tę różnicę tylko dla jednego z plików
• Zakomituj zmiany
• Wyświetl historię zmian w repozytorium

$ echo "Zawartość zmodyfikowana 1" > plik1.txt
$ git status
$ echo "Zawartość zmodyfikowana 2" > plik2.txt
$ git status
$ git diff plik1.txt
$ git add .
$ git commit -m "Zmodyfikowano pliki"
$ git log

Zadanie 3
• Sklonuj repozytorium repo1 jako repo2

$ cd ..
$ git clone repo1 repo2

Zadanie 4
Działając w repo2:
• Usuń z repozytorium jeden z plików tekstowych
• Zmień nazwę drugiego z plików tekstowych
• Sprawdź stan repozytorium
• Zakomituj zmiany
• Wyświetl historię zmian w repozytorium, z pokazaniem informacji o nazwach
zmienianych plików

$ cd repo2
$ rm plik1.txt

$ git status
$ mv plik2.txt tekst2.txt
$ git status
$ git add .
$ git commit -m "Usunięto jeden plik i zmieniono nazwę drugiego"
$ git log --name-status

Zadanie 5
• Zaktualizuj stan repo1, tak aby odzwierciedlał zmiany dokonane w repo2
$ cd ..
$ cd repo1
$ git status
$ git pull ../repo2 master

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

$ echo "Zmiana repo1" > tekst2.txt
$ cd ../repo2
$ echo "Zmiana repo2" > tekst2.txt
$ cd ../repo1
$ git add .
$ git commit -m "Zmiana repo1"
$ cd ../repo2
$ git add .
$ git commit -m "Zmiana repo2"
$ git status
$ cd ../repo1
$ git status
$ git pull ../repo2
$ git add .
$ git commit -m "Konflikt rozwiązany"
$ git status
$ git log
$ cd ../repo2
$ git pull ../repo1 master

Zadanie 7
• Przywrócić stan kopii roboczej do stanu repozytorium sprzed zadania 6.
sprawdź stan repozytorium
• Wyświetl zawartość pliku modyfikowanego w zadaniu 6
• Powróć do normalnego stanu repozytorium
• Sprawdź stan repozytorium
$ cd ../repo1
$ git checkout HEAD~1
$ git status
$ cat tekst2.txt
$ git checkout HEAD
$ git status
Zadanie 8
• Wyświetl zawartość pliku modyfikowanego w 6 przed dokonaniem tych
modyfikacji bez przełączania kopii roboczej na ówczesny stan repozytorium
$ git show HEAD~1:tekst2.txt

Zadanie 9
• Wyświetl różnicę stanu obecnego pliku modyfikowanego w 6 i stanu przed
dokonaniem tych modyfikacji
$ git diff HEAD~1 HEAD tekst2.txt
Zadanie 10
• Utwórz nowy branch w repo1 o nazwie test i przełącz się na niego
• Zmodyfikuj plik tekstowy w ramach tego brancha i zakomituj zmiany
• Wyświetl informacje na temat branchy
• Wróć do domyślnej gałęzi „master” i wyświetl zawartość modyfikowanego pliku
oraz stan repozytorium
$ cd ../repo1
$ git checkout master
$ git checkout -b test
$ echo "Zmiana w nowym branchu" > test2.txt
$ git commit -m "Zmiana w branchu test"
$ git branch
$ git checkout master
$ cat tekst2.txt
$ git status

Zadanie 11
• Zaciągnij zmiany dokonane w zadaniu 10 z repo1 do repo2 tak aby znalazły się
one w brachu o nazwie test
• wyświetl stan repozytorium, informacje na temat branchy oraz dwa najnowsze
wpisy z historii repozytorium

$ cd ../repo2
$ git pull ../repo1 test
$ git status
$ git branch
$ git log -n 2

