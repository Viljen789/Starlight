# Starlight AI
AI-amatører sitt forsøk på en fungerende LLM
# Om prosjektet
Vi er to ambisiøse studenter som begge har hatt et øye for AI siden 2022, når vi prøvde oss på et konsulent-prosjekt ved navn Starlight. Hovedformålet med det prosjektet var å bruke AI til å forbedre arbeidsflyt for potensielle kunder. Vi kom oss aldri langt nok inn i prosessen ettersom AI var langt ifra like bra som det er nå. Vi har dermed bestemt oss for å prøve oss på et ganske mye mer krevende prosjekt med grunnlag i at begge studerer dataingeniør på NTNU, og vil ha noe litt mer krevende å holde på med på siden.

# Om oss
<img width="1344" height="1792" alt="viljenogeirik" src="https://github.com/user-attachments/assets/63a29ad7-854c-448e-8eef-73894065ca0b" />
Vi studerer begge dataingeniør på NTNU i Trondheim, og har kjent hverandre siden 2021 da vi begynte på videregående skole sammen.
| | |
|---|---|
| **Eirik** | Første års dataingeniør-student ved NTNU i Trondheim. Veldig mange hobbyer, men eksempler kan være friluftsliv, gaming, alt av idrett, og ikke minst programmering. [GitHub](https://github.com/eirik-bl) · [LinkedIn](https://www.linkedin.com/in/eirik-brun-lunde-5601bb248/) |
| **Viljen** | Tredje års datateknologi-student ved NTNU i Trondheim. Interessert i fallskjermhopping, popcorn, friidrett og veldig interessert i tog. [GitHub](https://github.com/Viljen789) · [LinkedIn](https://linkedin.com/in/brukernavn) |





# Roadmap: LLM fra bunnen av




Et læringsprosjekt ved siden av studier der vi bygger opp vår forståelse fra grunnen: nevralt nett i NumPy, GPU-programmering i CUDA, og deretter en liten språkmodell. Målet er å forstå og kunne forklare hvert steg, ikke bare å få noe til å kjøre.

> Tidsanslagene er estimater for alt mellom 2-8 timer i uka ved siden av studiene. Planen justeres underveis, og status oppdateres ærlig. Vi stiller lite krav til å møte disse estimatene, ettersom dette blir et hobbyprosjekt.

## Status

| Fase | Tema | Mnd | Status |
|---|---|---|---|
| 0 | Grunnlag | 1-3 | Ikke startet |
| 1 | Nevralt nett i NumPy | 3-5 | Ikke startet |
| 2 | CUDA-grunnlag | 5-8 | Ikke startet |
| 3 | Nettet i CUDA | 8-10 | Ikke startet |
| 4 | Mini-GPT | 10-13 | Ikke startet |
| 5 | Treningspipeline og fine-tuning | 13-16 | Ikke startet |
| 6 | Demo og rapport | 16-20 | Ikke startet |

## Fase 0: Grunnlag (mnd 1-3)
- [ ] C/C++: pekere, arrayer, `malloc`/`free`, kompilering med `g++`
- [ ] Matte: matrisemultiplikasjon, transponering, kjerneregelen (derivasjon)
- [ ] Python/NumPy: arrayer, former (shapes), broadcasting
- [ ] Git-arbeidsflyt: branches og pull requests mellom oss
- **Resultat:** små øvelser i repoet og en læringslogg i `notater/`

## Fase 1: Nevralt nett fra scratch i NumPy (mnd 3-5)
- [ ] Ett lag (forward), med håndregnet eksempel
- [ ] ReLU, softmax og cross-entropy
- [ ] Backprop for hånd
- [ ] Gradientsjekk (numerisk mot analytisk)
- [ ] Trening på spiraldata, deretter MNIST
- **Resultat:** repo med README som forklarer hvert steg, pluss tester

## Fase 2: CUDA-grunnlag (mnd 5-8)
- [ ] Oppsett (WSL2 eller Windows), `nvcc` og hello world
- [ ] Vektoraddisjon, sjekket mot CPU
- [ ] Tråder, blokker og grid forklart med egne ord
- [ ] Elementvise kjerner (ReLU, oppdatering av vekter)
- [ ] Reduksjon (sum, maks)
- [ ] Matmul: naiv, så tiled med shared memory
- [ ] Måling og sammenligning mot cuBLAS
- **Resultat:** egen matmul-kjerne med målte tall

## Fase 3: Nettet i CUDA (mnd 8-10)
- [ ] Forward og loss på GPU, sjekket mot NumPy
- [ ] Backward og vektoppdatering
- [ ] Trening på MNIST med tidsmåling (CPU mot GPU)
- **Resultat:** teknisk rapport med målinger

## Fase 4: Mini-GPT (mnd 10-13)
- [ ] BPE-tokenizer
- [ ] Embeddings, attention og transformer-blokk
- [ ] Mini-GPT i PyTorch på egne data, med perplexity
- **Resultat:** treningskurver og eksempler på generert tekst

## Fase 5: Treningspipeline og fine-tuning (mnd 13-16)
- [ ] Mixed precision, gradient accumulation, checkpointing, logging
- [ ] LoRA på en åpen modell
- [ ] Eget instruksjonsdatasett
- **Resultat:** ryddig, gjenbrukbar kodebase

## Fase 6: Demo og rapport (mnd 16-20)
- [ ] Server/API og kvantisering
- [ ] Discord-bot eller web-grensesnitt
- [ ] Teknisk rapport og live demo
- **Resultat:** live demo og rapport

---

## Definition of done (gjelder alle punkter)
Et punkt er ferdig først når:
1. Koden virker og er testet mot en fasit (for eksempel NumPy).
2. README er oppdatert med en kort forklaring.
3. Vi kan forklare det med egne ord uten å se på koden.

## Arbeidsmetode per steg
1. Skriv teorien med egne ord.
2. Regn et lite eksempel for hånd og forutsi svaret.
3. Skriv koden fra tom fil.
4. Verifiser mot håndregningen eller fasit.
5. Ødelegg med vilje (fjern bias, bytt rekkefølge) og forklar hva som skjer.
6. Forklar det høyt, som i et intervju.

## Mappestruktur
```
fase0-grunnlag/
fase1-numpy/
fase2-cuda/
fase3-cuda-nett/
fase4-mini-gpt/
fase5-pipeline/
fase6-demo/
notater/        # læringslogg
ROADMAP.md
README.md
```

## Ansvar
| Område | Ansvarlig |
|---|---|
| Fase 0-1 | Begge (hver sin implementasjon, så sammenligner vi) |
| Fase 2-3 | Fyll inn |
| Fase 4-5 | Fyll inn |
| Fase 6 | Fyll inn |

## Prinsipper
- Ingenting merkes som ferdig før det er testet.
- Vi lover ikke en stor modell trent fra scratch. Målet er en liten, forstått modell med målte resultater.
- Sene faser holdes løse, og planen justeres etter fase 3.
