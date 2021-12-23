# 04-lecture-notes-git-MTeofan
= Lecture Notes / 3BHITM / ITP
Teofan Mihaescu
1.0.0, {docdate}: ITP
ifndef::imagesdir[:imagesdir: images]
//:toc-placement!:  // prevents the generation of the doc at this position, so it can be printed afterwards
:sourcedir: ../src/main/java
:icons: font
:sectnums:    // Nummerierung der Überschriften / section numbering
:toc: left

== Lecture 21.12.2021

=== Github Keygen

mithilfe von SSH keys:

    ssh-keygen -t rsa

== GIT:

neuen Ordner erstellen und erneut Klonen

    mkdir work
    cd work
    git clone <LINK>

File im Directory abändern:

    gedit readme.md
    <ändern des files>
    git commit -m "test merge"
    git push

Andere Person nun auf dem repo:

    git status

man bemerkt, dass das Repo nicht auf dem aktuellen Stand ist +
updaten des Repos:

    git pull

mit diesen Command laded man alle Abänderungen in den
Dateien des remote repos herunter.

Person 2 editiert dann die Datei, commited und pusht

    echo "Person 2 edit" >> readme.md
    git commit -m "update readme.md - Person 2"
    git push

Person 1 ladet nun wieder die Abänderungen herunter

    git pull

nun ändern beide Personen die Datei readme.md ab. +
beide Personen:

    git add
    git commit -m "merge test2"
    git push

bei einer Person wird der push rejected, da das Remote
repo Änderungen beinhaltet, die noch nicht existieren. +
Daher braucht man git stash:

    git stash

aufgrund des Commites kann stash nicht ausgeführt werden.

IMPORTANT: vor dem commit IMMER einen pull machen

Öffnen des Repos in Intelliji für einen Merge
Mergeconflikte sind auf der Commandzeile eher schwer zu machen,
daher sollten wir dafür einen Editor verwenden (Intelliji, VSCode)
