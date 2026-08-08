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

