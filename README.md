Opsplitsing van de taak zelf:
1:data verwerking zelf, dus data schoonmaken, en feature engineering (is in principe niet zo moeilijk, wel redelijk frustrerend en kan lang duren. Ook extreem belangrijk, als hier fouten in zijn is al de rest ook beinvloed)

2:exploratory analysis. (dit is veruit het makkelijkste deel). wel de bedoeling dat die op de "originele" data gebeurt (dus met alle cardiac arrests).

3: verwijderen van de cardiac arrests die slecht zijn. Maak je gewoon een kopie van de dataset en verwijder je die instances. (ook de verwijderde instances bijhouden, en de reden waarom ze verwijderd zijn)

4: graphing techniek om de underperforming AED's te vinden (NEO4J). deze dan ook verwijderen later (en de reden waarom ook weer bijhouden)

5: eerste clustering analyse. kan uiteraard pas gebeuren nadat alle vorige stappen voltooid zijn). gebruik sci-kit learn (les 4). dit is al iets moeilijker en complexer. ook gebruik maken van een pipeline.
(https://app.datacamp.com/learn/courses/unsupervised-learning-in-python enkel het eerste deel ziet er echt relevant uit)

6: tweede cluster analyse. papermill kan hiervoor gebruikt worden, aangezien we telkens opnieuw een clusteranalyse doen maar dan op verschillende groepen.

7: assess the impact of changing the current set-up:
die extensie is wel zeer goed, moeten we ook doen. want zoals het nu is stellen we onze aanpassing voor, maar eigenlijk heeft de gebruiker geen idee hoe veel beter die aanpassing is. het kan zijn dat onze aanpassing echt veel beter is, of dat het amper een verschil geeft en dat je net zo goed het zo kan laten. in ieder geval is het belangrijk voor de gebruiker om die info te hebben. Het zou ook zeer goed zijn om hier een visualisatie te gebruiken (bv. landkaart van huidig versus nieuw ofzo), in extensie kan zelfs een visualisatie van elke mogelijke setup gedaan worden. Ook de metric die we gemaakt hebben gebruiken hiervoor (zie verder).


8: finale stap: alles samenvoegen in 1 groot geheel. Papermill, MLflow, app maken (wat die app exact gaat zijn en hoe hij gemaakt gaat worden is nog een andere vraag; bijvoorbeeld het app aspect bestaat dan uit een online ding, dat de visualisaties van de verschillende mogelijke setups geeft, de performance van elke mogelijke setup. dient dan voor die stakeholder, zodat hij een deftig overzicht krijgt van alle informatie en de resultaten van de analyse. ook de exploratory analysis kan hier getoond worden).


Opmerkingen:
opmerking: bij elke stap van het verwijderen van de AED's moeten die AED's ook bijgehouden worden, en de reden waarom ze verwijderd zijn.

aangezien we MLflow moeten gebruiken, kunnen we een measure bedenken voor de performance van de nieuwe config. aangezien elke clustering methode andere configs geeft in principe, kunnen we deze verschillende clustering methodes op deze manier tegenover elkaar pitten, en zo alle methodes incorporeren in onze MLflow ding. Voorbeeld van zo'n performance metric: gemiddelde afstand tov de AED's, hoeveel mensen effectief gered zouden kunnen worden met de AED, ... (moet dus wel nog bedacht worden wat die metric is). die metric wordt dan bepaald op basis van zijn voorgestelde simulatie (bootstrap, historic sampling of een stochastisch proces).

Overload extensie: ziet er complex uit. wat we wel sowieso kunnen doen is gewoon kijken of er uberhaupt overload is. als dat niet of zeer zelden het geval is, dan hoeft er ook geen rekening mee gehouden worden. of als er slechts bepaalde ziekenhuizen zijn die vaak overbelast zijn, dan kan je gewoon die ziekenhuizen markeren (en dan kunnen we bijvoorbeeld die ziekenhuizen uit de dataset halen zoals we ook AED's uit de dataset halen, en op basis van dat dan de nieuwe AED's plaatsen). Die overload checken is dus iets dat eigenlijk al redelijk vroeg in de analyse moet gebeuren, nog voor de cluster analyses.

iedereen zou ook sowieso git moeten leren gebruiken:
https://app.datacamp.com/learn/courses/introduction-to-git
