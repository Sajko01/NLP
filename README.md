# NLP Parser za Rasadnik Biljaka

Ovaj projekat predstavlja implementaciju NLP sistema za automatsku obradu korisničkih upita u domenu rasadnika biljaka.

Sistem prepoznaje:
- nameru korisnika (cena, dostupnost, preporuka, dostava, lokacija, kontakt itd.),
- naziv biljke,
- uslove za preporuku biljaka (sunce, senka, balkon, terasa, malo vode i slično),
- lokaciju za dostavu.

U radu su implementirana i upoređena tri pristupa:

1. Rule-based pristup (`rulesOnly.py`)
2. LLM-only pristup (`llmOnly.py`)
3. Hibridni pristup (`llm_parser.py`, `hibrid_*.py`)

Za LLM deo korišćen je model **Qwen2.5:3b** kod hibrida i **Llama3.2:3b** za prvi test kod llm_parsera pokrenuti lokalno preko **Ollama** platforme.

## Fajlovi

- `llm_parser.py` – prvi pokusaj hibridnog parsera
- `rulesOnly.py` – rule-based parser
- `llmOnly.py` – LLM-only parser
- `hibrid_zero.py` – zero-shot eksperiment
- `hibrid_one.py` – one-shot eksperiment
- `hibrid_three.py` – three-shot eksperiment
- `hibrid_five.py` – five-shot eksperiment
- `hibrid_ten.py` – ten-shot eksperiment
- `test_llm.py` – evaluacija svih parsera na test skupu
- `recommendation_engine.py` – demonstracija rada sistema u realnom vremenu
- `biljke3.csv` – baza biljaka
- `pitanja.csv` – test skup korisničkih upita

## Pokretanje

Pokretanje poređenja:

python rulesOnly.py

python llmOnly.py

python hibrid_ten.py

Pokretanje svih evaluacije(u kodu se podešava koji parser koristi, odkomentariše se import i fajl za greške):

python test_llm.py

Pokretanje demonstracionog sistema:

python recommendation_engine.py

Autor

Aleksandar Jovanović
Master studije – Veštačka inteligencija i mašinsko učenje
Elektronski fakultet Univerziteta u Nišu
