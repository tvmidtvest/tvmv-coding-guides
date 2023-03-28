# Programmering, best practices

### Skriv kode til mennesker ikke til maskiner! 🤖

**Giv funktioner og variabler sigende navne**

- En funktion som transformerer: `transform_string_to_unicode`
- En funktion som gemmer noget data: `save_entries_to_db`
- En variabel som rummer video-navne: `video_names`
- En funktion, som henter noget data: `get_entries_from_file`

**Strukturer din kode, så den er letlæselig**
Kan din kode ikke umiddelbart læses, er det tid for refaktorering.

**Undgå kommentarer (for det meste)**
Har du brug for at skrive en kommentar, så overvej om det er fordi din kode er for kompliceret eller om du ikke har overholdt reglen om sigende navne til funktioner og variabler.

### Forstå hvad du skal kode inden du går i gang

Lav en prototype med funktionsnavne:

```python
def transform_rss_to_xml(rss: str) -> str:
	pass

def then_do_this_thing(new_param: str) -> str:
    pass

```

### Lær og tilpas

Vær åben for at lære nye teknikker, sprog og værktøjer, og tilpas din tilgang til kodning baseret på feedback og erfaring.

### Skriv kode efter single responsibility-princippet

Tænk generisk og standardiseret. Lav kobling og høj samhørighed: Sørg for at organisere din kode i moduler med minimal afhængighed mellem dem (lav kobling) og relaterede funktioner og data grupperet sammen (høj samhørighed).

### Undgå nestede if-statements

Brug fx Early Return-princippet i stedet eller split en test ud i en funktion.

```python

def calculate_weather(rain: dict) -> Any:

    if rain['drizzle']:
        return False

    if rain['amount'] < 5:
        return False

    # Resten af koden herunder
    return rain['type']

```

### I Python brug en modulopbygget struktur

Alle filer i Python er også et "modul"!

```python
import utilities
import video
import database

utilities.to_string()
video.create_video_title()
```

### Brug exceptions og gør dem så "tynde" som muligt

Hver try/except skal have minimalt ansvar. Lad være med at pakke større kode-blokke ind i exceptions.

### Undgå globale variabler

Globale variabler er forurening. Det er ikke tydeligt, hvor de kommer fra og hvad de indeholder. Variabler hører til i funktioner.

### Følg kodestandarden

Fx ved Python brug PEP8 - brug autopep8 i VSCODE. Brug i det hele taget alle de hjælpeværktøjer du kan i VSCODE.

```bash
$ pip install autopep8
```

### Refaktorer løbende

Det er IKKE spild af tid at gennemskrive noget, hvis du opdager noget nyt eller kan gøre noget bedre. Det er HELT NORMALT at gennemskrive sin kode flere gange undervejs. Tiden er godt givet ud - også selvom du føler, at du ikke kommer videre. Tænk på den næste, som skal kigge i din kode.

Skal du udvide dit program efter et år, er det helt ok at refaktorere noget af det gamle kode.

### ALT skal i Git

Vi skal versionere alt. Både for din egen og for andres skyld. Commit minimum til fyraften.

### ALT skal deployes fra Git

Når vi deployer fra Git (`git pull`) så sikrer vi at det er den korrekte og seneste version, som kører i produktion.

### Kør og test lokalt

Du skal kunne køre og teste din kode lokalt. Brug .env og config-filer til at tilpasse til dit lokale miljø.

### Brug ALTID et virtuelt python-miljø

```bash
$ python -m venv .venv
$ source .venv/bin/activate # MacOS
```

### Brug .env-fil til lokale konstanter

Env-filer gør det muligt at køre dit program lokalt.

### Overvej om du egentlig er i gang med at lave to programmer

Gå efter Single Responsibility-princippet for hele programmet også. Lad være med at lave en schweizer-kniv som kan alt. Overvej om dele af din kode skal have sit eget program.
