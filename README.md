# Hoe kunnen we online een samenwerking opzetten voor MusicService?

## Welke workflow past binnen MusicService?

## Inleiding
Voor het samenwerken met een team in een software project heb je zonder twijfel wel eens gebruik gemaakt van een Code Repository en een specifieke manier van werken in deze repositories. De meest gebruikte hosts voor dit soort projecten zijn Github, BitBucket, Gitlab (Stackify, Source code repository hosts, 2017) om er maar een paar op te noemen. Deze services werken vrijwel volledig hetzelfde met een aantal verschillen in UI of extra features die tijdens per platform verschillend zijn, maar allemaal werken ze met branches (Jelvix, bitbucket vs github vs gitlab, 2021). Maar door alleen gebruik te maken van een repository host ben je nog niet klaar voor een goede samenwerking. Je repository heeft namelijk structuur nodig die iedereen weet te gebruiken en duidelijk is zodat iedereen efficiënt er mee om kan gaan. Hierdoor zorg je niet alleen voor een betere samenwerking en snellere opleveringen, maar ook uiteindelijk voor betere code.

Voor een goede samenwerken is het cruciaal om een goede structuur in je repository te behouden. Het bedenken van je eigen structuur is vaak lastig en neemt tijd in beslag die je het beste tijdens development kon gebruiken. Een succesvolle workflow houd namelijk rekening met verschillende  factoren zoals het team cultuur en het feit dat iedereen zo efficiënt mogelijk moet kunnen werken. Zeker voor mensen die nog redelijk nieuw zijn met het gebruik maken van repositories kan dit verwarrend zijn, daarom zijn er al bestaande workflows waar je gebruik van kan maken. Er is geen definitief antwoord over welke workflow de beste is, maar je kan er wel achter komen welke het beste is voor je situatie. Dit is wat ik ook heb gedaan tijdens het maken van de repository voor het individuele project. 
Er zijn een aantal workflows die het meest gebruikt worden waaronder GitFlow, Github Flow en Gitlab Flow elk met eigen voordelen en nadelen. (Learn Git Flow, sd)

### Gitflow
Gitflow is verre weg de meest gebruikte workflow tot nu toe. Het bestaat uit verschillende primaire branches zoals de stable release branch en de development branch. De belangrijkste branches zijn de feature branches of hotfix branches. Deze branches worden gebruikt wanneer er aan een nieuwe feature gewerkt wordt of wanneer er een bug gevonden word die gefixt moet worden. Zodra een feature klaar is word deze naar de develop branch gemerged. Als deze branch uiteindelijk goed genoeg is krijg je de release branch met de versie nummer. Hierin kan je nog dingen zoals release notes toevoegen aan het programma maar geen echte code veranderingen meer doen. Zodra dit allemaal goed is kan de main stable branch geupdate worden met de nieuwe versie. (Gitflow on GitHub: How to use Git Flow workflows with GitHub Based Repos, 2021)

### Voordelen van het gebruiken van Gitflow
Het grootste voordeel van het gebruiken van gitflow zijn de feature branches. Deze zijn vooral handig voor het programmeren in grotere teams omdat meerdere mensen tegelijk aan verschillende features kunnen werken. Meerdere mensen kunnen ook samenwerken aan dezelfde feature omdat elke branch zijn eigen sandboxomgeving is.  

Een ander groot voordeel is de Develop branch die als een staging branch word gebruikt voor alle nieuwe features die nog niet gereleased zijn. Hierdoor kan je de volgende release branch baseren op de nieuwste develop branch en dan heeft het alle nieuwe features.

### Nadelen van het gebruiken van Gitflow
Het allergrootste nadeel van deze workflow is dat het niet altijd even makkelijk is om te gebruiken. Vooral bij applicaties die meerdere releases kunnen hebben binnen enkele weken is het niet de beste optie om gitflow te gebruiken. 

## Github Flow
Github Flow word gezien als de makkelijkere versie van Gitflow. In deze workflow is het wel mogelijk om meerdere keren per dag te deployen. Bij de Github flow draait het allemaal om de master branch. Alles wat in deze branch zit is bedoeld om gedeployed te worden te worden. Als er een nieuwe feature gemaakt moet worden, wordt er eerst een nieuwe branch gemaakt vanuit de master branch. De naam van deze branch moet duidelijk de feature beschrijven. Als de feature klaar is, is het de bedoeling dat je via een pull request naar de master branch pushed. Deze pull request moet gereviewed worden waarna de master branch wordt geupdate. (Github Flow Quickstart, sd)

### Voordelen van Github Flow
Het gebruiken van github flow is simpel en overzichtelijk. Het volgt een simpele workflow die begint bij de master branch en ook weer eindigt met de master branch zonder al te veel verschillende branches ertussen te creëren. 

Een ander voordeel is het aantal keer dat je kan deployen. Het deployen in Github Flow is vele malen makkelijker dan in een workflow zoals bijvoorbeeld Gitflow. Hierdoor is deze workflow geschikter voor projecten waar veel gedeployed moet worden. 

### Nadelen van Github flow
Het grootste nadeel van Github flow is de limitatie met betrekking tot versies. Je hebt altijd maar 1 versie in de repository staan en dat is de versie op de main branch. Nooit in het proces wordt er een release branch aangemaakt net als bij Gitflow die dan gepushed word naar master. 

## Gitlab flow
Gitlab flow is net als de hiervoor genoemde Github Flow een simpelere alternatieve variant van Gitflow. Ook deze manier van werken maakt gebruik van Feature branches en kan verder gezien worden als een uitbreiding op Github flow. 

Gitlab flow kan op twee manieren gebruikt worden. De eerste manier is de environment manier. In deze workflow heb je een production branch, en daarnaast een main branch. Vanuit de main branch worden er feature branches gemaakt op dezelfde manier als bijvoorbeeld Github flow. Deze feature branches worden gemerged naar de main branch via een merge request, die aan het einde van productie weer gemerged wordt naar de production branch. Het werkt hetzelfde als Github Flow, maar met een extra branch boven de main branch die zorgt voor de deployment.

De tweede manier is door release branches te gebruiken. Deze manier is alleen nodig als je echt van plan bent je software te releasen. Deze workflow is hetzelfde als de eerste omdat je nog steeds die main branch hebt waar je feature branches uit maakt. Het verschil is wel dat je bij deze branch na een tijdje een nieuwe release branch maakt. In deze release branches mogen alleen belangrijke bugfixes gepushed worden. Het is aan de gebruiker zelf om te beslissen of deze dan ook een nieuwe versienummer moet krijgen.

### Voordelen van Gitlab Flow
Gitlab flow is vele malen gestructureerder dan wat Github Flow bied, zonder verwarrend over te komen zoals gebeurd bij Gitflow. Hierdoor is het een perfecte mix tussen de beide workflows voor teams die niet genoeg hebben aan de github flow, en gitflow te complex vinden voor het project.

### Nadelen van Gitlab flow
Helaas is de makkelijkheid van Gitlab flow met release branches beïnvloed door het aantal versies die je programma kan hebben. Hoe meer versies er zijn, hoe complexer het uiteindelijk wordt. Het begint dus makkelijk, maar na een tijdje wordt het alsnog complex en misschien wel net zo complex als Gitflow zelf.

## Conclusie
Tijdens ons individuele project hebben wij ook gebruik gemaakt van Github. Om de samenwerking te verbeteren en een duidelijke professionele repository op te bouwen kunnen wij het beste ook gebruik maken van een van deze workflows. De beste optie in ons geval is de environment manier van Gitlab flow. Omdat wij werken in een organization waar meerdere repositories in staan die allemaal een microservice hosten, is het gebruiken van gitflow te complex voor wat wij doen. Bovendien deployen wij misschien wel meerdere keren per dag met bugfixes of nieuwe features. In tegenstelling tot Gitflow is Github flow niet complex genoeg. Het is naar mijn mening altijd een beter plan om een extra branch te hebben voor de applicatie die ook daadwerkelijk gedeployed wordt. Github flow heeft dit gewoon niet.  
## Bronnen
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
Er zijn meerdere manieren om de belangen van je project te communiceren met stakeholders en mede software engineers die geïnteresseerd zijn in jou project. Binnen dit document is te lezen welke dat zijn en wat het verschil hierin is.
### Github
Een van de makkelijkste manieren om dit te doen is via GitHub issues. Via hier kunnen issues aangemaakt worden van wat er nog gedaan moet worden aan het project. Zo ontstaat er een overzicht van alles wat al in het project verwerkt is en alles wat nog uitgevoerd moet gaan worden. Ook kun je via GitHub issues personen aan de issue koppelen die deze issue zal verwerken. Nieuwe software engineers die mee willen helpen kunnen hun zelf ook toewijzen aan issues die nog geen gekoppeld persoon hebben. 
Alle issues kunnen binnen GitHub samen gevoegd in een overzicht dashboard door gebruik te maken van GitHub projects. Door dit te gebruiken krijg je dashboard met alle issues die gemaakt moeten worden. Ook zie je hier de actuele status van elke issue. Zo kan je zien of de issue al in progress is, er een review in progress is of dat de issue al verholpen is.
 
[vscode - Microsoft](https://github.com/microsoft/vscode)
 
### Jira
Een andere tool die je kan gebruiken is Jira. Dit werkt bijna het zelfde als GitHub projects. Hierin kan een backlog gemaakt worden met daarin alle user stories die bij het project horen. Aan deze user stories kan je ook work items toevoegen. Ook zijn deze user stories te koppelen aan je GitHub reposetories. Binnen Jira is er ook een overzichtelijk dashboard beschikbaar waarin je goed kan zien wat de belangen zijn binnen het project die nog gedaan moeten worden. 
  
 
### Readme
Binnen een project is vaak een readme te vinden. Hierin is vaak additionele informatie te vinden voor de belangen van het project. Dit zijn vaak non functionele belangen zoals bijvoorbeeld hoe er word om gegaan met een pull request. Ook deze zijn erg belangrijk om in je project te hebben zodat het voor iedereen duidelijk is wat er binnen het project verwacht word. Hierom is altijd handig om een readme te maken zodat je de non functionele belangen ook goed communiceert.
 
[vscode - Microsoft](https://github.com/microsoft/vscode)
### Reflectie
Binnen Music Service zijn we begonnen met het werken in Jira. Dit was in het begin erg duidelijk en overzichtelijk. Later zijn we er achter gekomen dat het makkelijker is om via GitHub projects te werken door middel van issues. Hierdoor is je proces veel meer gekoppeld aan je code en kregen we een overzichtelijkere werkwijze. In een volgend project zullen we dus van het begin af aan werken met GitHub Projects en issues. 
 
## Sources
[Jira](https://semseter3-ip-tomeykholt.atlassian.net/jira/software/projects/SEM3/boards/2/roadmap)
[Lobby Service](https://github.com/IP3Semester3/ipsemester3_lobbyservice)
[Music Service](https://github.com/IP3Semester3/ipsemester3_music)
[CryptoBoardSPA – DirkLemmen](https://github.com/DirkLemmen/CryptoBoardSPA) 
[vscode - Microsoft](https://github.com/microsoft/vscode)
[lisa - Microsoft](https://github.com/microsoft/lisa)
[nni - Microsoft](https://github.com/microsoft/nni)


## Hoe kan je er voor zorgen dat het project te begrijpen is voor andere SE's/stakeholders
Als eerst is het belangrijk om er voor te zorgen dat de [belangen van het project](#Hoe-communiceer-je-de-belangen-van-je-project) goed gecommuniceerd zijn binnen de het project. Hierdoor is het overzichtelijk voor andere software engineers en stakeholders waar het project naar toe gaat. 
Daarnaast is het erg belangrijk om de architectuur duidelijk uit te leggen binnen het project. Er zijn veel manieren om dit uit te leggen. Een van deze manieren is door gebruik te maken van een C4 plaat. Hiermee beschrijf je de volledige architectuur van het project op verschillende vlakken. 

![C3](https://user-images.githubusercontent.com/78905924/145172905-f1746748-4f02-4391-9a11-21e3893ad3c6.png)
 
Een andere manier om de architectuur te beschrijven is door gebruik te maken van UML. Hierin maak je gebruik van het beschrijven van de klasse en de relaties hier tussen binnen het project.

### Software Engineer
Verder is het voor software engineers ook belangrijk dat zij makkelijk kunnen helpen in het project. Hiervoor is het belangrijk dat er ook een overzicht is van hoe de repository werkt en hoe het project in elkaar zit. Hoe het project in elkaar zit kan zoals hier boven vermeld gedaan worden door duidelijke uitleg van de architectuur. Om een beeld te geven van hoe de repository in elkaar zijn zou het nodig zijn in om een readme de braches, code guidelines, pull requests en docker uit te leggen. Met deze informatie kan een software engineer een beeld krijgen van hoe de repository werkt en hoe het project in elkaar zit. Hierdoor zal hij makkelijk kunnen bijspringen binnen een project.
 
### Reflectie
Binnen het Music Service hebben we er voor gezorgd dat de architectuur duidelijk beschreven word door middel van een C4 plaat. We hebben gekozen om het C4 model te gebruiken omdat dit meer diepgang bied op de werking van distrubated architecture. UML heeft deze optie niet omdat hierin voornamelijk de klasse en de relaties hiertussen beschreven worden. Ook hebben we er voor gezorgd dat het voor een software engineer duidelijk is hoe de repository in elkaar zit. Dit hebben we gedan door er voor te zorgen dat de braches, code guidelines, pull requests en docker zorgvuldig uitgelegd word binnen de readme van het project. 

## Source
[vscode Microsoft](https://github.com/microsoft/vscode)
[Web-Dev-For-Beginners Microsoft](https://github.com/microsoft/Web-Dev-For-Beginners)
[Quantum - Microsoft](https://github.com/microsoft/Quantum)
[Playwright - Microsoft](https://github.com/microsoft/playwright)
[Repositories - Microsoft](https://github.com/orgs/microsoft/repositories) 
[nni - Microsoft](https://github.com/microsoft/nni)
[Lobby - Microsoft](https://github.com/IP3Semester3/ipsemester3_lobbyservice)
[Music - Microsoft](https://github.com/IP3Semester3/ipsemester3_music)
[CryptoBoardSPA – DirkLemmen](https://github.com/DirkLemmen/CryptoBoardSPA)

## Hoe zorg je er voor dat er waardetoevoeging binnen het project mogelijk is



