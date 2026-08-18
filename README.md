# Robot-PickAndPlace
Conceperea unui robot si vizualizarea in mediul de simulare ROS2.

## Etapa 1 - Stabilirea unui mecanism/robot.

  Am ales sa realizez un brat robotic cu 3 grade de libertate atasat unei platforme mobile ce are ca scop mutarea si transportarea obiectelor in diferite locuri. Acest tip de robot poate fi utilizat in spitale pentru transportul medicamentelor dintr-o camera in alta.

## Etapa 2 - Procesul de proiectare iterativ.
- [x] Proiectarea diferitelor componente utilizate
  - [X] Baterie
  - [X] Breadboard
  - [x] Servomotoare
  - [x] Roti
  - [X] LiDAR
  - [X] Controller
     
- [x] Proiectarea EOF(gripper)
  - [X] Proiectarea clestelui: lungimea trebuie sa fie mare astfel incat gripperul sa ia obiectele de pe jos.
  - [X] Aplicarea si verificarea mate-ului de tip Gear.
  - [X] Limitarea unghiurilor de actionare: Limit Angles.
  - [X] Verificarea bunei functionari a EOF.
        
- [X] Proiectarea bratului robotic
  - [X] Proiectarea componentelor astfel incat ele sa asigure gradele de libertate dorite.
  - [X] Identificarea locaselor potrivite pentru servomotoare.
  - [X] Aplicarea mate-urilor de tip Limit Angles si Limit Distances pentru a evita diferite coliziuni intre componente 

- [X] Proiectarea platformei
  - [X] Conceperea si modelarea unui sistem de directie pe baza servomotorului
  - [X] Modelarea astfel incat platforma sa fie rigida
  - [X] Identificarea locaselor potrivite pentru servomotoarele responsabile de actionarea rotilor.

- [X] Ansamblul final

> [!IMPORTANT]
> Dupa ce am facut tot ansamblul am luat decizia de a nu complica si mai mult componentele(sa adaug gauri, suruburi, etc) pentru a avea o simulare cat mai buna in mediul de vizualizare, spre urmare produsul final este unul simplificat.

## Etapa 3 - Pregatirea fisierelor STL > URDF Export.

In aceasta etapa a trebuit sa export robotul cu ajutorul URDF pentru a putea sa il testez in RViz. Acest export necesita ca tot robotul sa fie impartit in linkuri si jointuri pentru a vedea miscarile in simulare. 

>[!NOTE]
> Prima oara am incercat sa generez configuratia URDF automat, dar rezultatul a fost unul nemultumitor primind o eroare. Nu se puteau gasi jointuri si linkuri. Spre urmare, am facut urmatorul sir de decizii.

1. Am facut vizibile toate sistemele de axe ale componentelor si am vazut ca sunt amestecate, unele axe Z erau in jos, altele in sus, orizontale, etc
2. Am facut subansambluri din mai multe piese, de exemplu la partea de sasiu unde erau rotile, componentele electrice si altele, le-am unificat intr-un singur ansamblu si am stabilit primu sistem de coordonate(baza fixa).
3. Am adaugat sisteme de coordonate si pentru celelalte componente care realizeaza miscari de translatie si rotatie.
4. Am adaugat axe pentru fiecare sistem pentru a stii in jurul cui facem miscarea.
5. Am definit jointurile si linkurile pentru un primul test.

>[!IMPORTANT]
> Pentru primul test am ales sa folosesc platforma web pentru usurinta. Link: [https://discourse.openrobotics.org/t/web-based-urdf-visualization-tool-and-library-opensourced-from-nasa-jpl/14404]. Vezi folderul de Screenshots pentru a vedea.

6. Definirea limitelor.

>[!NOTE]
>Fiecare joint are nevoie de limite pentru a simula cat mai realistic miscarea, de exemplu pentru translatie putem observa cum bratul se afla intre 2 componente. El trebuie constrans astfel incat el sa nu treaca prin ele. De asemenea, am observat cum mate-urile din ansamblu pe care le-am mentionat in etapa 2 nu au fost folositoare in URDF Exporter.

7. Testarea finala

## Etapa 4 - Miscarile in RViz

- [x] Pregatirea masinii virtuale si a mediului de simulare.
- [x] Importarea configuratiei URDF.
- [x] Miscarile de test pe jointuri.
- [x] Rezultatele au fost multumitoare.

## Concluzii

  In urma acestui proiect, am simtit dificultatea realizarii unui robot de la 0, pornind de la o idee, apoi incercand sa proiectez ce am in viziunea mea. Am vazut cum decurge acest proces de modelare de la o singura piesa la tot ansamblul. Dupa unele piese, a trebuit sa remodelez altele pentru a se potrivi intre ele si pentru a indeplini scopul pentru care au fost facute. Am vazut ce inseamna simularea acestui robot si trecerea prin niste etape pentru a avea rezultatul dorit. 
  
  In final, consider ca am dezvoltat mai multe skill-uri folositoare oricarui inginer si ca am avut ce invata din acest proiect, cum ar fi: 

  1. Stabilirea mai multor idei inainte sa incepi tot procesul.
  2. Impunerea unor deadline-uri intermediare si a etapelor, pentru a fi sigur ca vei livra un produs bun la timp.
  3. Sa ceri feedback in urma alegerilor pe care le-ai facut, pentru a verifica ca directia pe care ai luat-o este una buna.
  4. Sa gandesti ce rol are piesa pe care o faci, cum se poate realiza si sa vezi ca se poate utiliza impreuna cu altele.
  5. Sa abordezi mai multe metode cand vine vorba de un pas important pe care urmeaza sa il faci, pentru ca metodele usoare nu sunt si cele care ofera cele mai bune rezultate.
