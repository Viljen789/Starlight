# Fase 0: Øvelser og grunnteori

Kilde: Claude Code / Claude

Dropper bevisst del A og B ettersom begge har mer enn grunnleggende nok kunnskaper i disse oppgavene.
Anbefalt rekkefølge og tid (estimat): A Matte (1-2 uker), B Derivasjon (1-2 uker), C NumPy (1-2 uker), D C/C++ (3-4 uker), E Git (1 dag).

**Slik jobber du:** regn og forutsi svaret for hånd først, skriv koden fra tom fil, og sjekk mot fasit.

---

## C. Python og NumPy

### Teori
- Et NumPy-array har en **form** (`.shape`). Nesten alle feil handler om former.
- `@` er matrisemultiplikasjon. `*` er elementvis gange (noe helt annet).
- **Broadcasting:** NumPy strekker automatisk mindre arrayer så formene passer, hvis dimensjonene (regnet fra høyre) er like eller 1. Det er slik `x@W + b` legger `b` til hver rad.
- `sum(axis=0)` summerer nedover radene (én verdi per kolonne). `axis=1` summerer bortover (én verdi per rad).
- Vektorisert kode (NumPy) er mye raskere enn Python-løkker. Det er også grunnen til at GPU-er er nyttige senere.
- `np.random.default_rng(0)` gir gjentakbare tilfeldige tall.

### Øvelser
1. Lag matrisene fra A2 i NumPy og sjekk at `A@B` stemmer med håndregningen din.
2. Forutsi formene før du kjører: `(5,2)+(2,)`, `(5,2)+(5,)`, `(5,1)+(1,3)`. Kjør og forklar feilmeldingen for den som feiler.
3. Lag `X` med form `(5,2)`. Hva blir formen på `X.sum(axis=0)` og `X.sum(axis=1)`?
4. Skriv skalarprodukt med en `for`-løkke og sammenlign med `np.dot` på to vektorer med 1 000 000 tall. Mål tiden til begge.
5. Skriv matrisemultiplikasjon med tre `for`-løkker. Sjekk mot `@` med `np.allclose`, og mål tiden for matriser på `200×200`.
6. Skriv en funksjon `num_deriv(f, x)` for numerisk derivert. Test på `f(x)=x²` ved `x=3` (skal bli omtrent 6).
7. Tren **én** vekt med koden din: `x=3`, `y=6`, `lr=0.01`, 50 steg, `w` starter på 1. Skriv ut `w` underveis. Kontroller gradienten din med `num_deriv`.

<details><summary>Fasit C</summary>

2. `(5,2)`, feil (2 og 5 passer ikke), `(5,3)`
3. `(2,)` og `(5,)`
4. og 5. NumPy skal være mange ganger raskere. Det er poenget.
7. `w` går mot 2.
</details>

---

## D. C/C++ (forberedelse til CUDA)

### Teori
- Hver variabel ligger på en **adresse** i minnet. En **peker** er en variabel som lagrer en adresse: `int* p = &x;` og `*p` er verdien på adressen.
- Et **array** er flere like verdier etter hverandre i minnet. `a[i]` betyr verdien `i` plasser etter starten.
- I Java rydder en garbage collector opp. I C bestiller du selv minne med `malloc` og frigjør med `free`. Glemmer du `free`, får du en **minnelekkasje**. Leser du utenfor arrayet, får du feil tall eller krasj, uten pen feilmelding.
- En C-array vet ikke hvor lang den er. Du må sende lengden med som eget argument.
- **Row-major:** en matrise med `cols` kolonner lagres som én lang rekke, og element `(i, j)` ligger på indeks `i*cols + j`. Dette er nøyaktig slik GPU-arrayer vil se ut senere.
- Kompiler med `g++ fil.cpp -o program`, og kjør `./program`. Legg til `-fsanitize=address -g` for å fange minnefeil.

### Øvelser
1. Skriv et program som skriver ut «Hei» og kompiler det med `g++`.
2. Lag en `int x = 5`. Skriv ut verdien og adressen (`&x`). Skriv funksjonen `void doble(int* p)` som dobler verdien den peker på, og kall den.
3. Skriv `float sum(const float* a, int n)` som summerer et array. Test på et lite array du lager for hånd.
4. Bruk `malloc` til å lage et array med 1000 floats, fyll det, summer det og frigjør med `free`. Fjern så `free` og kjør med `-fsanitize=address`. Les rapporten.
5. Lag en `2×3`-matrise som et flatt array. Skriv ut element `(1,2)` med `i*cols + j`. Skriv så funksjonen `matmul(A, B, C, M, K, N)` med tre løkker. Test på matrisene fra A2 og sammenlign med håndregningen.
6. Ødelegg med vilje: les ett element utenfor arrayet, og kjør med `-fsanitize=address`. Forklar hva rapporten sier.

<details><summary>Fasit D</summary>

Det finnes ikke ett fasitsvar. Sjekk at (3) gir riktig sum, at (5) gir `[[2,1],[4,3]]` for A2, og at (4) og (6) gir en tydelig feilrapport fra sanitizeren.
</details>

---

## E. Git

1. `git init`, lag en fil, `git add`, `git commit`.
2. Lag en branch, gjør en endring, og lag en pull request på GitHub.
3. Gjør en endring hver og se hvordan en merge-konflikt ser ut, og løs den.

---

## Selvtest: forklar med egne ord
1. Hva betyr «form» på en matrise, og hvorfor må de indre tallene være like i `@`?
2. Hva sier den deriverte om en feilfunksjon, og hvorfor flytter vi vektene *mot* den?
3. Hva er kjerneregelen, og hvorfor trenger backprop den?
4. Hva er broadcasting, og når bruker vi det i et lag?
5. Hva er en peker, og hvorfor må vi selv kalle `free`?
6. Hvorfor er `i*cols + j` riktig indeks i en flatt matrise?
