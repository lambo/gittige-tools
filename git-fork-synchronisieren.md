# Synchronisierung von Forks mit Git

Viele Aktionen sind in GitHub direkt über die Weboberfläche möglich, z.B.:

* Eigenen Fork eines Repositories erstellen
* Einzelne Datei bearbeiten
* Pull vom Ursprungs-Repository anfordern

Leider fehlt die Möglichkeit, einen eigenen Fork durch Pull mit dem
Original-Repository zu synchronisieren. Dazu ist ein lokaler Git-Client
notwendig, z.B. das Kommandozeilenprogramm `git`. Zunächst ist der Fork lokal
herunterzuladen und das Original-Repository als weitere Quelle anzugeben:

    git clone git@github.com:jakobib/gittige-tools.git
    git remote add lambo https://github.com/lambo/gittige-tools.git

Falls das eigene Repository keine eigenen Änderungen hat, ist die
Synchronisierung mit einem einfachen Pull vom Original-Repository möglich:

    git pull lambo master

Es empfiehlt sich aber, stattdessen erst die Änderungen zu holen:

    git fetch lambo

dann die Änderungen bei Bedarf zu inspizieren:
 
    git diff lambo/master

und erst dann in den aktuellen Stand des eigenen Repositories zu übernehmen:

    git merge lambo/master

