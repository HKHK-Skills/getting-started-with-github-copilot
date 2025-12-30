## Samm 4: Lülita hüperaju sisse - Copilot Agent režiim 🚀

### 📖 Teooria: Mis on Copilot Agent režiim?

Copilot [agent režiim](https://code.visualstudio.com/docs/copilot/chat/chat-agent-mode) on AI-toega kodeerimise järgmine areng. Toimides autonoomse kaaslasest programmeerijana, täidab see mitmeetapilisi kodeerimisülesandeid sinu käsul.

Copilot Agent režiim reageerib kompileerimis- ja lint-vigadele, jälgib terminali ja testide väljundit ning parandab automaatselt tsüklis, kuni ülesanne on lõpetatud.

#### Muuda režiim vs Agent režiim (ülevaade)

| Aspekt | ✏️ Muuda režiim | 👩‍🚀 Agent režiim |
| ------ | --------------- | ----------------- |
| Konteksti ulatus | Ainult failid, mille sa selgelt lisad | Võib lugeda/lisada täiendavaid faile ja pindu vastavalt vajadusele |
| Ise-ülevaatus | Minimaalne (sina juhid iteratsiooni) | Sisseehitatud tagasiside ja uuesti proovimise tsükkel vigade korral |
| Muudatuse ulatus | Väga piiritletud ja kirurgiline | Laiem; võib puudutada seotud kihte järjepidevuse tagamiseks |
| Millal valida | Tead täpselt, mida muuta | Eesmärk on laiem või ebakindel; nõuab uurimist |
| Tööriistade kutsumine | Puudub (käivitad käsud käsitsi) | Saab kutsuda tööriistu (lugeda/muuta faile, käivitada käske, kontrollida terminali ja testide väljundit) |

#### 🧰 Agent režiimi tööriistad

Agent režiim kasutab tööriistu spetsialiseeritud ülesannete täitmiseks kasutaja päringu töötlemisel. Selliste ülesannete näited on:

- Sinu viiba täitmiseks asjakohaste failide leidmine
- Veebilehe sisu toomine
- Testide või terminali käskude käivitamine

> [!TIP]
> Kuigi VS Code pakub palju sisseehitatud tööriistu, saad anda Agent režiimile ka domeenispetsiifilisemaid võimeid **MCP tööriistade** kaudu.
>
> Loe rohkem [MCP serveritest](https://code.visualstudio.com/docs/copilot/customization/mcp-servers) ja [GitHub MCP serverist](https://github.com/github/github-mcp-server)

Nüüd proovime **Agent režiimi**! 👩‍🚀

### :keyboard: Tegevus: Kasuta Agent režiimi funktsionaalsete "tühista registreerimine" nuppude lisamiseks

Katsetame mõne avatud lõpuga päringuga, mis lisab meie veebirakendusele rohkem funktsionaalsust.

Kui sa ei saa soovitud tulemusi, võid proovida teisi mudeleid või anda järeltagasisidet tulemuste täpsustamiseks.

1. Ava **Copilot** vestluspaneel ja kasuta rippmenüüd **Agent** režiimile lülitumiseks.

   <img width="250" alt="agent režiim" src="https://github.com/user-attachments/assets/9bb85530-77a1-4d47-86b2-99769ce197db" />

1. Kliki **Tools** ikoonil ja uuri kõiki Copilot Agent režiimile praegu saadaolevaid tööriistu.

   <img width="250" alt="tööriistade ikoon" src="https://github.com/user-attachments/assets/8f73400a-2647-4b28-b52b-721b8cf348d8" />


1. Aeg meie testiks! Palume Copilotil lisada osalejate eemaldamise funktsionaalsus.

   > ![Static Badge](https://img.shields.io/badge/-Viip-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > #codebase Palun lisa kustutusikoon iga osaleja kõrvale ja peida täpploendid.
   > Klikkides tühistab see selle osaleja registreeringu tegevuselt.
   > ```

   `#codebase` tööriista kasutab Copilot asjakohaste failide, käesolevale ülesandele relevantsete kooditükkide leidmiseks.

   > 🪧 **Märkus:** Selles laboris lisame selgelt `#codebase` tööriista, et saada kõige korratavamaid tulemusi.
   > Proovi julgelt viipa **ilma** `#codebase`'ita ja jälgi, kas Agent režiim otsustab ise laiema projekti konteksti koguda.

1. Kui Copilot on lõpetanud, taaskäivita silur ja kontrolli tulemusi. Kui tulemused meeldivad, vajuta **Keep** nuppu. Kui ei, proovi anda Copilotile tagasisidet tulemuste täpsustamiseks.

1. Palu Copilotil parandada registreerimisviga.

   > ![Static Badge](https://img.shields.io/badge/-Viip-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Olen märganud, et tundub olevat viga.
   > Kui osaleja on registreeritud, tuleb lehte värskendada, et näha muudatust tegevusel.
   > ```

1. Kui Copilot on lõpetanud, kontrolli tulemusi. Kui tulemused meeldivad, vajuta **Keep** nuppu. Kui ei, proovi anda Copilotile tagasisidet.

### :keyboard: Tegevus: Kasuta Agent režiimi testide katvuse saamiseks 🧑‍🚀

Sinu tagarakendus on nüüd funktsioonirikas - aga ikka null testide katvusega. Kasuta Copilot **Agent režiimi** testsõltuvuste lisamiseks, algtestide loomiseks ja nende käivitamiseks.

1. Palu Copilotit **Agent režiimis** seadistada ja käivitada testid sinu tagarakenduse jaoks.

   > ![Static Badge](https://img.shields.io/badge/-Viip-placeholder?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Lisa fastapi testid kasutades pytest'i uude tests kausta ja käivita need.
   > Veendu, et lisad kõik uued sõltuvused requirements.txt faili
   > ```

1. Kui Copilot töötab sinu viiba kallal, võivad erinevad tööriistad vajada sinu heakskiitu.

   **🎯 Eesmärk: Saa kõik testid läbima (rohelised) - sihi puhta käivituse poole! ✅**

   > 🪧 **Märkus:** Copilot võib selle esialgse viibaga kohe ära teha või vajada sinult rohkem juhendamist.

1. Kui testid läbivad - **commit'i** ja **saada** kõik muudatused oma `accelerate-with-copilot` harusse, et liikuda viimase sammu juurde! Peaaegu valmis!
