# Hoe kunnen we online een samenwerking opzetten voor MusicService?

## Welke workflow past binnen MusicService?

# Inleiding
Voor het samenwerken met een team in een software project heb je zonder twijfel wel eens gebruik gemaakt van een Code Repository en een specifieke manier van werken in deze repositories. De meest gebruikte hosts voor dit soort projecten zijn Github, BitBucket, Gitlab (Stackify, Source code repository hosts, 2017) om er maar een paar op te noemen. Deze services werken vrijwel volledig hetzelfde met een aantal verschillen in UI of extra features die tijdens per platform verschillend zijn, maar allemaal werken ze met branches (Jelvix, bitbucket vs github vs gitlab, 2021). Maar door alleen gebruik te maken van een repository host ben je nog niet klaar voor een goede samenwerking. Je repository heeft namelijk structuur nodig die iedereen weet te gebruiken en duidelijk is zodat iedereen efficiënt er mee om kan gaan. Hierdoor zorg je niet alleen voor een betere samenwerking en snellere opleveringen, maar ook uiteindelijk voor betere code.

Voor een goede samenwerken is het cruciaal om een goede structuur in je repository te behouden. Het bedenken van je eigen structuur is vaak lastig en neemt tijd in beslag die je het beste tijdens development kon gebruiken. Een succesvolle workflow houd namelijk rekening met verschillende  factoren zoals het team cultuur en het feit dat iedereen zo efficiënt mogelijk moet kunnen werken. Zeker voor mensen die nog redelijk nieuw zijn met het gebruik maken van repositories kan dit verwarrend zijn, daarom zijn er al bestaande workflows waar je gebruik van kan maken. Er is geen definitief antwoord over welke workflow de beste is, maar je kan er wel achter komen welke het beste is voor je situatie. Dit is wat ik ook heb gedaan tijdens het maken van de repository voor het individuele project. 
Er zijn een aantal workflows die het meest gebruikt worden waaronder GitFlow, Github Flow en Gitlab Flow elk met eigen voordelen en nadelen. (Learn Git Flow, sd)

# Gitflow
Gitflow is verre weg de meest gebruikte workflow tot nu toe. Het bestaat uit verschillende primaire branches zoals de stable release branch en de development branch. De belangrijkste branches zijn de feature branches of hotfix branches. Deze branches worden gebruikt wanneer er aan een nieuwe feature gewerkt wordt of wanneer er een bug gevonden word die gefixt moet worden. Zodra een feature klaar is word deze naar de develop branch gemerged. Als deze branch uiteindelijk goed genoeg is krijg je de release branch met de versie nummer. Hierin kan je nog dingen zoals release notes toevoegen aan het programma maar geen echte code veranderingen meer doen. Zodra dit allemaal goed is kan de main stable branch geupdate worden met de nieuwe versie. (Gitflow on GitHub: How to use Git Flow workflows with GitHub Based Repos, 2021)

## Voordelen van het gebruiken van Gitflow
Het grootste voordeel van het gebruiken van gitflow zijn de feature branches. Deze zijn vooral handig voor het programmeren in grotere teams omdat meerdere mensen tegelijk aan verschillende features kunnen werken. Meerdere mensen kunnen ook samenwerken aan dezelfde feature omdat elke branch zijn eigen sandboxomgeving is.  

Een ander groot voordeel is de Develop branch die als een staging branch word gebruikt voor alle nieuwe features die nog niet gereleased zijn. Hierdoor kan je de volgende release branch baseren op de nieuwste develop branch en dan heeft het alle nieuwe features.

## Nadelen van het gebruiken van Gitflow
Het allergrootste nadeel van deze workflow is dat het niet altijd even makkelijk is om te gebruiken. Vooral bij applicaties die meerdere releases kunnen hebben binnen enkele weken is het niet de beste optie om gitflow te gebruiken. 

# Github Flow
Github Flow word gezien als de makkelijkere versie van Gitflow. In deze workflow is het wel mogelijk om meerdere keren per dag te deployen. Bij de Github flow draait het allemaal om de master branch. Alles wat in deze branch zit is bedoeld om gedeployed te worden te worden. Als er een nieuwe feature gemaakt moet worden, wordt er eerst een nieuwe branch gemaakt vanuit de master branch. De naam van deze branch moet duidelijk de feature beschrijven. Als de feature klaar is, is het de bedoeling dat je via een pull request naar de master branch pushed. Deze pull request moet gereviewed worden waarna de master branch wordt geupdate. (Github Flow Quickstart, sd)

## Voordelen van Github Flow
Het gebruiken van github flow is simpel en overzichtelijk. Het volgt een simpele workflow die begint bij de master branch en ook weer eindigt met de master branch zonder al te veel verschillende branches ertussen te creëren. 

Een ander voordeel is het aantal keer dat je kan deployen. Het deployen in Github Flow is vele malen makkelijker dan in een workflow zoals bijvoorbeeld Gitflow. Hierdoor is deze workflow geschikter voor projecten waar veel gedeployed moet worden. 

## Nadelen van Github flow
Het grootste nadeel van Github flow is de limitatie met betrekking tot versies. Je hebt altijd maar 1 versie in de repository staan en dat is de versie op de main branch. Nooit in het proces wordt er een release branch aangemaakt net als bij Gitflow die dan gepushed word naar master. 

# Gitlab flow
Gitlab flow is net als de hiervoor genoemde Github Flow een simpelere alternatieve variant van Gitflow. Ook deze manier van werken maakt gebruik van Feature branches en kan verder gezien worden als een uitbreiding op Github flow. 

Gitlab flow kan op twee manieren gebruikt worden. De eerste manier is de environment manier. In deze workflow heb je een production branch, en daarnaast een main branch. Vanuit de main branch worden er feature branches gemaakt op dezelfde manier als bijvoorbeeld Github flow. Deze feature branches worden gemerged naar de main branch via een merge request, die aan het einde van productie weer gemerged wordt naar de production branch. Het werkt hetzelfde als Github Flow, maar met een extra branch boven de main branch die zorgt voor de deployment.

De tweede manier is door release branches te gebruiken. Deze manier is alleen nodig als je echt van plan bent je software te releasen. Deze workflow is hetzelfde als de eerste omdat je nog steeds die main branch hebt waar je feature branches uit maakt. Het verschil is wel dat je bij deze branch na een tijdje een nieuwe release branch maakt. In deze release branches mogen alleen belangrijke bugfixes gepushed worden. Het is aan de gebruiker zelf om te beslissen of deze dan ook een nieuwe versienummer moet krijgen.

## Voordelen van Gitlab Flow
Gitlab flow is vele malen gestructureerder dan wat Github Flow bied, zonder verwarrend over te komen zoals gebeurd bij Gitflow. Hierdoor is het een perfecte mix tussen de beide workflows voor teams die niet genoeg hebben aan de github flow, en gitflow te complex vinden voor het project.

## Nadelen van Gitlab flow
Helaas is de makkelijkheid van Gitlab flow met release branches beïnvloed door het aantal versies die je programma kan hebben. Hoe meer versies er zijn, hoe complexer het uiteindelijk wordt. Het begint dus makkelijk, maar na een tijdje wordt het alsnog complex en misschien wel net zo complex als Gitflow zelf.

# Conclusie
Tijdens ons individuele project hebben wij ook gebruik gemaakt van Github. Om de samenwerking te verbeteren en een duidelijke professionele repository op te bouwen kunnen wij het beste ook gebruik maken van een van deze workflows. De beste optie in ons geval is de environment manier van Gitlab flow. Omdat wij werken in een organization waar meerdere repositories in staan die allemaal een microservice hosten, is het gebruiken van gitflow te complex voor wat wij doen. Bovendien deployen wij misschien wel meerdere keren per dag met bugfixes of nieuwe features. In tegenstelling tot Gitflow is Github flow niet complex genoeg. Het is naar mijn mening altijd een beter plan om een extra branch te hebben voor de applicatie die ook daadwerkelijk gedeployed wordt. Github flow heeft dit gewoon niet.  
# Bronnen
Atlassian, comparing workflows. (sd). Opgehaald van Atlassian: https://www.atlassian.com/git/tutorials/comparing-workflows

Dwarkani, B. (2020, September). GitKraken, Gitflow. Opgehaald van GitKraken: https://www.gitkraken.com/blog/gitflow

Github Flow Quickstart. (sd). Opgehaald van Github Docs: https://docs.github.com/en/get-started/quickstart/github-flow

GitKraken, git workflows and extensions. (sd). Opgehaald van GitKraken: https://support.gitkraken.com/git-workflows-and-extensions/git-flow/

Hughes, K. (2017). stackshare, bitbucket vs github vs gitlab. Opgehaald van stackshare: https://stackshare.io/stackups/bitbucket-vs-github-vs-gitlab

Ilyukha, V. (2021). Jelvix, bitbucket vs github vs gitlab. Opgehaald van Jelvix: https://jelvix.com/blog/bitbucket-vs-github-vs-gitlab

LambdaTest. (2021, September 27). What Is GitLab Workflow | GitLab Flow | GitLab Tutorial For Beginners | Part III. Opgehaald van YouTube: https://www.youtube.com/watch?v=7lgGEXpsflI

Learn Git Flow. (sd). Opgehaald van Gitkraken: https://www.gitkraken.com/learn/git/git-flow

McKenzie, C. (2021, Januari 30). Gitflow on GitHub: How to use Git Flow workflows with GitHub Based Repos. Opgehaald van YouTube: https://www.youtube.com/watch?v=WQuxeEvaCxs

McKenzie, P. (2013, augustus 12). What are the pros and cons of git-flow vs github-flow? Opgehaald van Stackoverflow: https://stackoverflow.com/questions/18188492/what-are-the-pros-and-cons-of-git-flow-vs-github-flow

Medium, 4 branching workflows for git. (sd). Opgehaald van Medium: https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf

Stackify, Source code repository hosts. (2017, Mei 17). Opgehaald van Stackify: https://stackify.com/source-code-repository-hosts/

The best way to use Git and GitHub. (sd). Opgehaald van GitHub Flow: https://githubflow.github.io/





## Hoe communiceer je de belangen van je project

## Hoe kan je er voor zorgen dat het project te begrijpen is voor andere SE's/stakeholders

## Hoe zorg je er voor dat er waardetoevoeging binnen het project mogelijk is


# Sources
- [GitFlow](http://datasift.github.io/gitflow/IntroducingGitFlow.html)
- [LobbyService](https://github.com/IP3Semester3/ipsemester3_lobbyservice)
- [MusicService](https://github.com/IP3Semester3/ipsemester3_music)
