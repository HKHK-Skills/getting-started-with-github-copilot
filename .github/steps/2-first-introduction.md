## Samm 2: Töö tegemine Copilotiga

Eelmises sammus aitas GitHub Copilot meil projektiga tutvuda. Ainuüksi see on tohutu ajasääst, aga nüüd teeme päris tööd!

:bug: **VEEBILEHEL ON VIGA** :bug:

Oleme avastanud, et registreerimise voos on midagi valesti.
Õpilased saavad praegu samale tegevusele registreeruda **rohkem kui ühe korra**! Vaatame, kui kaugele Copilot meid viib põhjuse avastamisel ja puhta paranduse kujundamisel.

Enne sukeldumist kiire sissejuhatus, kuidas Copilot töötab. 🧑‍🚀

### 📖 Teooria: Kuidas Copilot töötab

Lühidalt, võid mõelda Copilotist kui väga spetsialiseeritud kolleegist. Et temaga efektiivne olla, pead andma talle tausta (konteksti) ja selge suuna (viibad). Lisaks on erinevad inimesed erinevates asjades paremad oma ainulaadsete kogemuste tõttu (mudelid).

- **Kuidas me konteksti anname?:** Meie kodeerimiskeskkonnas arvestab Copilot automaatselt lähedal olevat koodi ja avatud vahekaarte. Kui kasutad vestlust, saad ka failidele selgelt viidata.

- **Millist mudelit peaksime valima?:** Meie harjutuse jaoks ei tohiks see palju loota. Erinevate mudelitega katsetamine on osa lõbust! See on teine tund! 🤖

- **Kuidas viipasid teha?:** Selgesõnalisus ja selgus aitab Copilotil parimat tööd teha. Kuid erinevalt mõnedest traditsioonilistest süsteemidest saad alati oma suunda täpsustada järelviibadega.

> [!TIP]
> On mitmeid teisi viise Copiloti teadmiste ja võimete täiendamiseks nagu [vestlusosalised](https://docs.github.com/en/copilot/using-github-copilot/copilot-chat/github-copilot-chat-cheat-sheet?tool=vscode#chat-participants), [vestlusmuutujad](https://docs.github.com/en/copilot/using-github-copilot/copilot-chat/github-copilot-chat-cheat-sheet?tool=vscode#chat-variables), [kaldkriipsu käsud](https://docs.github.com/en/copilot/using-github-copilot/copilot-chat/github-copilot-chat-cheat-sheet?tool=vscode#slash-commands-1) ja [MCP tööriistad](https://code.visualstudio.com/docs/copilot/chat/mcp-servers).

### :keyboard: Tegevus: Kasuta Copilotit meie registreerimisvea parandamiseks :bug:

1. Palume Copilotil soovitada, kust meie viga võib pärineda. Ava **Copilot Chat** paneel **Küsi režiimis** ja küsi järgmist.

   > ![Static Badge](https://img.shields.io/badge/-Viip-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > @workspace Õpilased saavad tegevusele kaks korda registreeruda.
   > Kust see viga võib pärineda?
   > ```

1. Nüüd, kui teame, et probleem on `src/app.py` failis ja `signup_for_activity` meetodis, järgime Copiloti soovitust ja parandame selle (poolkäsitsi). Alustame kommentaariga ja laseme Copilotil paranduse lõpetada.

   1. VS Code'is vali **Explorer** vaheleht projekti failide kuvamiseks ja ava `src/app.py` fail.

   1. Keri faili lõpu lähedale ja leia `signup_for_activity` meetod.

   1. Leia kommentaaririda, mis kirjeldab õpilase lisamist. Selle kohal tundub loogiline teha meie registreerimiskontroll.

   1. Sisesta allolev kommentaar ja vajuta enter järgmisele reale minekuks. Hetke pärast ilmub ajutine varjutekst Copiloti soovitusega! Tore! :tada:

      ```python
      # Kontrolli kas õpilane pole juba registreeritud
      ```

   1. Vajuta `Tab`, et aktsepteerida Copiloti soovitus ja muuta varjutekst koodiks.

   <details>
   <summary>Näite tulemused</summary><br/>

   Copilot areneb iga päev ja ei pruugi alati samu tulemusi anda. Kui sa pole soovitustega rahul, siin on näide kehtivast soovitustulemusest, mille me selle harjutuse tegemise ajal tootsime. Saad seda kasutada jätkamiseks.

   ```python
   @app.post("/activities/{activity_name}/signup")
   def signup_for_activity(activity_name: str, email: str):
      """Registreeri õpilane tegevusele"""
      # Kontrolli kas tegevus eksisteerib
      if activity_name not in activities:
         raise HTTPException(status_code=404, detail="Tegevust ei leitud")

      # Võta tegevus
      activity = activities[activity_name]

      # Kontrolli kas õpilane pole juba registreeritud
      if email in activity["participants"]:
        raise HTTPException(status_code=400, detail="Õpilane on juba registreeritud")

      # Lisa õpilane
      activity["participants"].append(email)
      return {"message": f"Registreeriti {email} tegevusele {activity_name}"}
   ```

   </details>

### :keyboard: Tegevus: Lase Copilotil genereerida näidisandmed 📋

Uutes projektiarendustes on sageli kasulik omada realistlikke võltsandmeid testimiseks. Copilot on selles ülesandes suurepärane, nii et lisame veel näidistegevusi ja tutvustame veel üht viisi Copilotiga suhtlemiseks, kasutades **Reasisest vestlust**

**Reasisene vestlus** ja **Copilot Chat** paneel on sarnased, kuid erinevad ulatuses: Copilot Chat tegeleb laiemate, mitme faili või uurimuslike küsimustega; Reasisene vestlus on kiirem, kui tahad sihtotstarbe abi täpsel real või plokil enda ees.

1. `src/app.py` faili ülaosa lähedal (umbes rida 23) leia `activities` muutuja, kus meie näide huviringid on seadistatud.

1. Kliki ükskõik millisel seotud real ja ava Copiloti reasisene vestlus kiirklahviga `Ctrl + I` (Windows) või `Cmd + I` (Mac).

   > 💡 **Vihje:** Teine viis Copiloti reasisese vestluse avamiseks: `paremklikk` ükskõik millisel valitud real -> `Copilot` -> `Editor Inline Chat`.

1. Sisesta järgmine viipatekst ja vajuta enter või **Send and Dispatch** nuppu.

   > ![Static Badge](https://img.shields.io/badge/-Viip-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Lisa 2 spordiga seotud tegevust, 2 kunstiga seotud
   > tegevust ja 2 intellektuaalset tegevust.
   > ```

1. Hetke pärast hakkab Copilot otse koodi muutma. Muudatused on erinevalt stiliseeritud, et lisandusi ja eemaldusi oleks lihtne tuvastada. Võta hetk ülevaatamiseks ja vajuta **Accept** nuppu.

   <details>
   <summary>Näite tulemused</summary><br/>

   Copilot areneb iga päev ja ei pruugi alati samu tulemusi anda. Kui sa pole soovitustega rahul, siin on näitetulemus, mille me selle harjutuse tegemise ajal tootsime. Saad seda jätkamiseks kasutada, kui on probleeme.

   ```python
   # Mälus tegevuste andmebaas
   activities = {
      "Maleklubi": {
         "description": "Õpi strateegiaid ja võistle maleturniiridel",
         "schedule": "Reedeti, 15:30 - 17:00",
         "max_participants": 12,
         "participants": ["michael@mergington.edu", "daniel@mergington.edu"]
      },
      "Programmeerimisklass": {
         "description": "Õpi programmeerimise põhitõdesid ja ehita tarkvaraprojekte",
         "schedule": "Teisipäeviti ja neljapäeviti, 15:30 - 16:30",
         "max_participants": 20,
         "participants": ["emma@mergington.edu", "sophia@mergington.edu"]
      },
      "Kehalise kasvatuse tund": {
         "description": "Kehaline kasvatus ja sporditegevused",
         "schedule": "Esmaspäeviti, kolmapäeviti, reedeti, 14:00 - 15:00",
         "max_participants": 30,
         "participants": ["john@mergington.edu", "olivia@mergington.edu"]
      },
      "Korvpallimeeskond": {
         "description": "Võistluslik korvpallitreening ja mängud",
         "schedule": "Teisipäeviti ja neljapäeviti, 16:00 - 18:00",
         "max_participants": 15,
         "participants": []
      },
      "Ujumisklubi": {
         "description": "Ujumistreeningud ja veespordialad",
         "schedule": "Esmaspäeviti ja kolmapäeviti, 15:30 - 17:00",
         "max_participants": 20,
         "participants": []
      },
      "Kunstistuudio": {
         "description": "Väljenda loovust maalimise ja joonistamise kaudu",
         "schedule": "Kolmapäeviti, 15:30 - 17:00",
         "max_participants": 15,
         "participants": []
      },
      "Draamaklubi": {
         "description": "Teatrikunst ja esinemiskoolitus",
         "schedule": "Teisipäeviti, 16:00 - 18:00",
         "max_participants": 25,
         "participants": []
      },
      "Väitlusklubi": {
         "description": "Õpi avaliku esinemise ja argumenteerimisoskusi",
         "schedule": "Neljapäeviti, 15:30 - 17:00",
         "max_participants": 16,
         "participants": []
      },
      "Teadusklubi": {
         "description": "Praktilised katsed ja teaduslik avastamine",
         "schedule": "Reedeti, 15:30 - 17:00",
         "max_participants": 20,
         "participants": []
      }
   }
   ```

   </details>

### :keyboard: Tegevus: Kasuta Copilotit meie töö kirjeldamiseks 💬

Hea töö vea parandamisel ja näidistegevuste laiendamisel! Nüüd saame oma töö commit'itud ja GitHubi saadetud, jälle Copiloti abiga!

1. Vasakul külgribal vali `Source Control` vaheleht.

   > 💡 **Vihje:** Faili avamine versioonihalduse alast näitab erinevusi originaaliga, mitte lihtsalt ei ava seda.

1. Leia `app.py` fail ja vajuta `+` märki oma muudatuste kogumiseks ettevalmistusalasse.

   ![pilt](https://github.com/user-attachments/assets/7d3daf4e-4125-4775-88a7-33251cd7293e)

1. Ettevalmistatud muudatuste nimekirja kohal leia **Message** tekstikast, aga **ära sisesta praegu midagi**.

   - Tavaliselt kirjutaksid siia muudatuste lühikirjelduse, aga nüüd on meil Copilot abiks!

1. **Message** tekstikasti paremal pool leia ja kliki **Generate Commit Message** nuppu (sädelevate ikoon).

1. Vajuta **Commit** nuppu ja **Sync Changes** nuppu oma muudatuste GitHubi saatmiseks.

1. Oota hetk, kuni Mona kontrollib sinu tööd, annab tagasisidet ja jagab järgmist tundi.

<details>
<summary>Probleeme? 🤷</summary><br/>

Kui sa ei saa tagasisidet, kontrolli järgmist:

- Veendu, et saatsid `src/app.py` faili muudatused harusse `accelerate-with-copilot`.

</details>
