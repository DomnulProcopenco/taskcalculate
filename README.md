# taskcalculate
Metrica, revizuirea şi analiza statică (revizuire)
* Observații privind codul:

Start.java:
- Linia 12: Variabila `scanIn` ar trebui să fie închisă folosind un bloc `try-with-resources` pentru a evita potențialele scurgeri de resurse.
- Linia 15: Verificarea egalității între șiruri de caractere ar trebui să fie făcută folosind metoda `equals()` în loc de operatorul `==`.

Calculator.java:
- Linia 6: Utilizarea variabilei `finalResult` ca variabilă statică poate duce la probleme de concurență și ar trebui evitată. Ar fi mai bine să se utilizeze o variabilă locală sau să se returneze rezultatul ca valoare de retur din metoda Calculate.
- Linia 15: Clasa internă `Operations` este statică și ar trebui să fie marcată ca `static`.
- Linia 37: Evaluarea expresiei poate genera o excepție și ar trebui să fie gestionată corespunzător, de preferat cu un bloc `try-catch`.
- Linia 69: În metoda `Calculate`, se pot face optimizări pentru a evita duplicarea codului și a crește claritatea algoritmului.
- Linia 74: Metoda `Calculate` modifică starea globală (`finalResult`) și ar putea duce la comportament neașteptat în cazul apelurilor concurente.

* Calcularea Metricilor și Revizuirea Codului:
- Numărul total de linii de cod (LOC):
- Fișierul `Start.java`:
- Numărul de linii de cod: `19`
- Fișierul `Calculator.java`:
- Numărul de linii de cod: `134`
- Număr total de linii de cod (proiectul complet): `153`

* Am analizat codul metodei evaluateExpression și am calculat complexitatea ciclomatică și cognitivă. Iată rezultatul:
- Complexitatea Ciclomatică:
- Identificăm următoarele structuri de control:
- O buclă `for` în linia 26 și blocuri `if` în linia `30`, `48`, `61`, `73`.
- Numărăm căile independente prin aceste structuri de control:
- Bucla `for` contribuie cu o unitate.
- Fiecare bloc `if` contribuie cu o unitate.
- Complexitatea ciclomatică rezultată este `5`.

* Complexitatea cognitivă a metodei evaluateExpression este ridicată din următoarele motive:
- Utilizarea unei structuri de buclă `for` pentru parcurgerea expresiei poate face dificilă înțelegerea fluxului de control al metodei.
- Există mai multe blocuri `if` care se ocupă de diferite scenarii ale expresiei aritmetice, crescând complexitatea logică a metodei.
