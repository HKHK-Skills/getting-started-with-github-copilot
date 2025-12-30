## Samm 1: Tere Copilot

Tere tulemast oma **"GitHub Copiloti alustamine"** harjutusse! :robot:

Selles harjutuses kasutad erinevaid GitHub Copiloti funktsioone töötades veebilehega, mis võimaldab Mergington High Schooli õpilastel registreeruda huviringidesse. 🎻 ⚽️ ♟️

<img width="600" alt="Mergington High Schooli veebirakenduse ekraanipilt" src="https://github.com/user-attachments/assets/472398fd-1aa1-4084-b443-4e242deb30d9" />

### 📖 Teooria: GitHub Copilotiga tutvumine

<img width="150" align="right" alt="copiloti logo" src="https://github.com/user-attachments/assets/4d22496d-850b-4785-aafe-11cba03cd5f2" />

GitHub Copilot on AI kodeerimisabiline, mis aitab sul koodi kiiremini ja väiksema vaevaga kirjutada, võimaldades sul keskenduda rohkem probleemide lahendamisele ja koostööle.

GitHub Copilot on tõestatud suurendavat arendajate produktiivsust ja kiirendavat tarkvara arenduse tempot. Lisainfot leiad artiklist [Research: quantifying GitHub Copilot's impact on developer productivity and happiness GitHubi blogis.](https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/)

Töötades oma IDE-s, suhtled GitHub Copilotiga kõige sagedamini järgmistel viisidel:

| Suhtlusrežiim | 📝 Kirjeldus | 🎯 Parim kasutus |
| ------------- | ------------ | ---------------- |
| **⚡ Reasisesed soovitused** | AI-toega koodisoovitused, mis ilmuvad kirjutades, pakkudes kontekstiteadlikke täiendusi ühest reast tervete funktsioonideni. | Praeguse rea täiendamine, mõnikord terve uus koodiplokk |
| **💬 Küsi režiim** | Optimeeritud vastama küsimustele sinu koodibaasi, kodeerimise ja üldiste tehnoloogiakontseptsioonide kohta. | Koodi tööpõhimõtete mõistmine, ideede ajurünnak, küsimuste esitamine |
| **✏️ Muuda režiim** | Optimeeritud koodi muudatuste tegemiseks mitmes failis sinu projektis. VS Code rakendab koodimuudatused otse redaktoris kohapealse ülevaatuse jaoks. | Kodeerimisülesanded, kui sul on hea arusaam soovitud muudatustest ja failidest |
| **🤖 Agent režiim** | Optimeeritud autonoomsete muudatuste tegemiseks mitmes failis sinu projektis. | Kodeerimisülesanded, kui sul on vähem määratletud ülesanne, mis võib nõuda ka terminali käskude ja tööriistade käivitamist |
| **💭 Reasisene vestlus** | Interaktiivne vestlus, mis on piiratud sinu praeguse faili või valikuga. Küsi küsimusi konkreetsete koodiplokkide kohta. | Koodi selgitused, konkreetsete funktsioonide silumine, sihitud parendused |

Töötades leiad, et GitHub Copilot saab aidata mitmes kohas üle `github.com` veebilehe ja sinu lemmik kodeerimiskeskkondades nagu VS Code, Jet Brains ja Xcode!

Tänase kodeerimise jaoks harjutame VS Code'iga eelseadistatud arenduskeskkonnas, mida tuntakse kui [GitHub Codespace](https://github.com/features/codespaces).

> [!TIP]
> Praeguste ja tulevaste funktsioonide kohta saad rohkem teada [GitHub Copiloti funktsioonide](https://docs.github.com/en/copilot/about-github-copilot/github-copilot-features) dokumentatsioonist.

### :keyboard: Tegevus: Saa projektitutvustus Copilot Chat'ist

Alustame oma arenduskeskkonnaga, kasutame Copilotit projekti kohta veidi õppimiseks ja siis testime seda.

1. Kasuta allolevat nuppu **Create Codespace** lehe avamiseks uuel vahekaardil. Kasuta vaikeseadistust.

   [![Ava GitHub Codespaces'is](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

1. Kinnita, et **Repository** väli on sinu koopia harjutusest, mitte originaal, siis kliki rohelist **Create Codespace** nuppu.

   - ✅ Sinu koopia: `/{{full_repo_name}}`
   - ❌ Originaal: `/skills/getting-started-with-github-copilot`

1. Oota hetk, kuni Visual Studio Code laadib sinu brauseris.

1. Vasakul külgribal kliki laienduste vahekaardil ja kontrolli, et `GitHub Copilot` ja `Python` laiendused on paigaldatud ja lubatud.

   <img width="350" alt="copiloti laiendus VS Code jaoks" src="https://github.com/user-attachments/assets/ef1ef984-17fc-4b20-a9a6-65a866def468" />

   <img width="350" alt="pythoni laiendus VS Code jaoks" src="https://github.com/user-attachments/assets/3040c0f5-1658-47e2-a439-20504a384f77" />

1. VS Code ülaosas leia ja kliki **Toggle Chat ikooni**, et avada Copilot Chat külgpaneel.

   <img width="150" alt="pilt" src="https://github.com/user-attachments/assets/abf584e9-ef68-4725-8b22-4803805e6d55" />

   > 🪧 **Märkus:** Kui see on sinu esimene kord GitHub Copiloti kasutamisel, pead jätkamiseks aktsepteerima kasutustingimused.

1. Veendu, et oled meie esimeseks suhtluseks **Küsi režiimis**

   <img width="350" alt="ekraanipilt Küsi režiimi valikust Copilot Chat'is" src="https://github.com/user-attachments/assets/fb1d7cac-2d39-4199-b5d9-0f3dfcfb3bcd" />

1. Sisesta allolev viip, et paluda Copilotil sind projektiga tutvustada.

   > ![Static Badge](https://img.shields.io/badge/-Viip-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > @workspace Palun selgita lühidalt selle projekti struktuuri.
   > Mida ma pean tegema selle käivitamiseks?
   > ```

   > 🪧 **Märkus:** Copiloti soovitatud juhiseid pole vaja järgida. Oleme juba keskkonna sinu jaoks ette valmistanud.

   <details>
   <summary>Mis on @workspace?</summary>

   Hea küsimus! See on spetsialiseeritud [vestlusosaline](https://docs.github.com/en/copilot/using-github-copilot/copilot-chat/github-copilot-chat-cheat-sheet?tool=vscode#chat-participants), mis uurib projekti repositooriumi ja üritab kaasata asjakohast lisakonteksti.

   </details>

1. Nüüd, kui teame projekti kohta veidi rohkem, proovime seda tegelikult käivitada! Vasakul külgribal vali `Run and Debug` vaheleht ja vajuta **Start Debugging** ikooni.

   <img width="300" alt="pilt" src="https://github.com/user-attachments/assets/50b27f2a-5eab-4827-9343-ab5bce62357e" />

1. Tahame näha oma veebilehte brauseris, nii et leiame url-i ja pordi. Kui see pole nähtav, laienda alumist paneeli ja vali **Ports** vaheleht.

1. Nimekirjas leia port `8000` ja seotud link. Hõlju lingi kohal ja vali **Open in browser** ikoon.

   ![pilt](https://github.com/user-attachments/assets/92d5642e-ce99-4a66-850c-2d311a673596)

### :keyboard: Tegevus: Kasuta Copilotit terminali käsu meeldetuletamiseks 🙋

Suurepärane töö! Nüüd, kui oleme rakendusega tuttavad ja teame, et see töötab, palume Copilotilt abi haru alustamiseks, et saaksime kohandada.

1. VS Code alumises paneelis vali **Terminal** vaheleht ja paremal pool kliki pluss `+` märki uue terminaliakna loomiseks.

   > 🪧 **Märkus:** See väldib olemasoleva silumissessiooni peatamist, mis majutab meie veebirakenduse teenust.

1. Uues terminaliaknas kasuta kiirklahvi `Ctrl + I` (Windows) või `Cmd + I` (Mac), et avada **Copiloti terminali reasisene vestlus**.

1. Palume Copilotilt abi unustatud käsu meeldetuletamiseks: haru loomine ja avaldamine.

   > ![Static Badge](https://img.shields.io/badge/-Viip-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Hei Copilot, kuidas saan luua ja avaldada uue Giti haru nimega "accelerate-with-copilot"?
   > ```

   > 💡 **Vihje:** Kui Copilot ei anna päris seda, mida tahad, saad alati jätkata selgitamist, mida vajad. Copilot mäletab vestlusajalugu järeldustuste jaoks.

1. Vajuta `Run` nuppu, et lasta Copilotil terminali käsk meie eest sisestada. Pole vaja kopeerida ja kleepida!

1. Hetke pärast vaata VS Code alumist olekuriba vasakul, et näha aktiivset haru. See peaks nüüd ütlema `accelerate-with-copilot`. Kui jah, oled selle sammuga valmis!

1. Nüüd, kui sinu haru on GitHubi saadetud, peaks Mona juba hõivatud olema sinu tööd kontrollides. Anna talle hetk ja jälgi kommentaare. Näed teda vastamas edenemisinfo ja järgmise tunniga.

<details>
<summary>Probleeme? 🤷</summary><br/>

Kui sa ei saa tagasisidet, kontrolli järgmist:

- Veendu, et lõid haru täpse nimega `accelerate-with-copilot`. Ilma eesliideteta ja järelliideteta.
- Veendu, et haru on tõesti avaldatud sinu repositooriumisse.

</details>
