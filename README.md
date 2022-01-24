# VEnv, Pip en Import Demo

## Wat is dit?

Als je in een team complexere Python programmas maakt is het handig een paar truukjes te leren. Deze komen in Blok C van SD ook terug, maar dan in Java. 

Drie dingen zijn dan handig:

1. Eigen Python modules
2. Andermans Python modules
3. Unit tests (lees: 'module tests')

Een module is hier niets meer of minder dan wat python code waarvan je wilt dat anderen het kunnen gebruiken.

## Installatie:

Misschien moet je nog eerst even de 'virtual environment' plugin installeren in Python

```
pip install virtualenv
```

*(Mocht pip het niet doen, dan moeten we eerst even je Python installatie uitzoeken: je mist dan namelijk iets in je PATH environment variabele. Allemaal stuff die we je hadden moeten uitleggen.)*

Nu dan, om daadwerkelijk het project te installeren:

```
python -m virtualenv venv
./venv/Scripts/activate
pip install -r requirements.txt
```
De eerste regel maakt een nieuwe 'virtual environment' en zet dit in de venv directory.

De tweede regel -activeert- die virtual environment.

De derde regel installeert python-modules die in de requirements.txt staat -in- die virtual environment.

Kijk dus vooral even in die venv directory om te zien wat daar uiteindelijk is gebeurd.

## Opstarten

Aangenomen dat de installatie gelukt is zijn er er twee interessante manieren om deze code te draaien:

```
python main.py
```
Dit start 'het programma' en laat een koe hallo zeggen. Niet bijzonder spannend maar het gaat om het idee:
 Wij hebben een legoblokje, het internet heeft een legoblokje, en samen hebben we een programma.

De andere manier is het 'testen':
```
pytest
```
Dit draait alle tests (`def`s die starten met `test_`, zoals `test_hello()`), in alle .py bestanden die starten met `test_`, zoals `test_hello.py`.

Hier checken we of onze eigen module netjes werkt. Andermans modules hoeven we in principe niet te testen, dat is de verantwoordelijkheid van die programmeurs.

## Achtergrond

### Eigen modules

In dit voorbeeld is de eigen module de `hello.py` file. Daar staat 1 simpele functie ge`def`inieerd.

### Andermans modules

De `main.py` is het opstartpunt van de applicatie. Die importeert zowel onze module `hello.py`, die je zo kan vinden, als de cowsay module, die verstopt is in de `venv/Lib/site_packages` folder. 

### Modules testen

Als andere mensen jouw modules gebruiken is het wel handig als je zeker weet dat ze het doen. Daarom is het aan te raden kleine oefeningen (tests) voor je code te schrijven en die geregeld te draaien om te dubbelchecken of je per ongeluk iets stuk hebt gemaakt.