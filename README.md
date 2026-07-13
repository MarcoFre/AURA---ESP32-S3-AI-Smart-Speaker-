<div align="center">

# HackMyHome Voice Assistant

### Migrazione Aura · Waveshare ESP32-S3 Audio + display GC9A01A 240×240

La migrazione di **Aura** sull’hardware originale del Voice Speaker HackMyHome, ora equipaggiato con display rotondo **GC9A01A**, interfaccia **LVGL**, anello LED sincronizzato, microWakeWord locale, media player, timer, sveglia e rilevamento del rumore.

[![ESPHome](https://img.shields.io/badge/ESPHome-2026.6.3%2B-03A9F4?style=for-the-badge&logo=esphome&logoColor=white)](#)
[![Home Assistant](https://img.shields.io/badge/Home%20Assistant-Voice%20Assistant-41BDF5?style=for-the-badge&logo=homeassistant&logoColor=white)](#)
[![LVGL](https://img.shields.io/badge/UI-LVGL-22D3EE?style=for-the-badge)](#)
[![Display](https://img.shields.io/badge/Display-GC9A01A%20240%C3%97240-2563EB?style=for-the-badge)](#)
[![LED](https://img.shields.io/badge/Ring-7%20WS2812-EC4899?style=for-the-badge)](#)
[![Project](https://img.shields.io/badge/HackMyHome-Aura-8B5CF6?style=for-the-badge)](#)

<a href="https://github.com/MarcoFre/images-aura/blob/main/aura_half_smile.png">
  <img src="https://raw.githubusercontent.com/MarcoFre/images-aura/main/aura_half_smile.png" alt="Aura con mezzo sorriso" width="260">
</a>

<em>Aura sul nuovo display circolare da 240×240 pixel.</em>

</div>

---

## 📦 Il progetto

| Voce | Dettaglio |
|---|---|
| **Piattaforma** | Waveshare ESP32-S3 Audio |
| **Display aggiunto** | GC9A01A rotondo, 240×240 |
| **Interfaccia display** | SPI |
| **Touchscreen** | Non presente |
| **Controlli locali** | Tre pulsanti fisici: volume −, play/pausa, volume + |
| **Feedback luminoso** | Anello da 7 LED WS2812 |
| **Codec speaker** | ES8311 |
| **Codec microfoni** | ES7210 |
| **Espansore I/O** | TCA9555 |
| **Firmware** | ESPHome |
| **Interfaccia grafica** | LVGL |
| **Integrazione** | Home Assistant Voice Assistant |
| **Versione YAML** | `0.4.1-lvgl-aura-gc9a01a-led-sync` |
| **Modello 3D** | Piatto superiore con slitta per il display disponibile in formato STL |

> [!IMPORTANT]
> Questa configurazione è stata sviluppata per la migrazione di Aura sul dispositivo audio ESP32-S3 originale, collegando esternamente un display **GC9A01A 240×240**.
> 
## 🔗 Link utili
### 🛒 ESP32-S3 AI Smart Speaker Development Board
* **Waveshare:** [https://www.waveshare.com/?&aff_id=HackMyHome](https://www.waveshare.com/?&aff_id=HackMyHome)
* **Amazon:** [https://amzn.to/40JLOQq](https://amzn.to/40JLOQq)
### 🛒 Display LCD IPS 1,28" GC9A01 / GC9A01A
* **Amazon:** [https://amzn.to/4ckpC4M](https://amzn.to/4ckpC4M)
### 🌐 HackMyHome
* [**ESP32-S3 AI Smart Speaker: da “all-in-board” a "Voice Assistant" - Home Assistant**](https://youtu.be/Lcp8FQ9NLyo)
* [**Aggiungiamo un Display Circolare! 📺✨**](https://youtu.be/EsESK5aimu4)
* [**YouTube: HackMyHome**](https://www.youtube.com/@HMH-Aura-Nova)
* [**Facebook: HackMyHome**](https://www.facebook.com/profile.php?id=61583821941006)
---
## 🧭 Indice

- [Obiettivo della migrazione](#-obiettivo-della-migrazione)
- [Caratteristiche principali](#-caratteristiche-principali)
- [Hardware supportato](#-hardware-supportato)
- [Piatto superiore stampabile in 3D](#-piatto-superiore-stampabile-in-3d)
- [Pinout principale](#-pinout-principale)
- [Architettura firmware](#-architettura-firmware)
- [Aura e interfaccia LVGL](#-aura-e-interfaccia-lvgl)
- [Anello LED Aura Sync](#-anello-led-aura-sync)
- [Pulsanti fisici](#-pulsanti-fisici)
- [Voice Assistant](#-voice-assistant)
- [Modalità musica e VU meter](#-modalità-musica-e-vu-meter)
- [Timer e sveglia](#-timer-e-sveglia)
- [Rilevamento rumore e antifurto](#-rilevamento-rumore-e-antifurto)
- [Entità Home Assistant](#-entità-home-assistant)
- [Azioni API](#-azioni-api)
- [Installazione](#-installazione)
- [Asset grafici Aura](#-asset-grafici-aura)
- [Troubleshooting](#-troubleshooting)
- [Struttura del repository](#-struttura-del-repository)
- [Roadmap](#-roadmap)
- [Crediti](#-crediti)

---

## 🏠 Obiettivo della migrazione

Il progetto nasce per portare la nuova interfaccia grafica di **Aura** sul primo Voice Speaker HackMyHome, mantenendo l’hardware audio originale e sostituendo la parte visiva con un display rotondo **GC9A01A da 240×240 pixel**.

La migrazione conserva:

- codec audio e microfoni originali;
- wake word locale;
- Voice Assistant di Home Assistant;
- media player e annunci TTS;
- timer e sveglia;
- pulsanti fisici;
- anello LED WS2812;
- rilevamento del rumore.

La nuova interfaccia aggiunge:

- Aura animata tramite LVGL;
- boot grafico con avanzamento reale;
- bocca sincronizzata con il parlato;
- espressioni casuali;
- modalità sonno;
- modalità musica con pose Dance;
- VU meter circolare;
- sincronizzazione tra archi del display e anello LED fisico.

---

## ✨ Caratteristiche principali

| Area | Funzione |
|---|---|
| 🎙️ **Voice Assistant** | Integrazione con Assist di Home Assistant |
| 🧠 **Wake word locale** | microWakeWord con modelli configurabili |
| 👩 **Aura** | Blink, espressioni, sonno e bocca audio-reattiva |
| 🖥️ **Display** | GC9A01A rotondo 240×240 con LVGL |
| 🔘 **Controlli locali** | Volume −, play/pausa e volume + |
| 💡 **Aura Sync** | Anello WS2812 sincronizzato con gli archi del display |
| 🔊 **Audio** | Speaker I2S, ES8311, mixer media e annunci |
| 🎧 **Microfoni** | ES7210 via I2S |
| 🎵 **Modalità musica** | Pose Dance, note animate, movimento e VU meter RMS |
| ⏱️ **Timer** | Countdown grafico e stato dedicato alla scadenza |
| ⏰ **Sveglia** | Ora e azione configurabili da Home Assistant |
| 🛡️ **Antifurto** | Rilevamento del rumore sopra soglia |
| 🌙 **Sonno** | Aura si addormenta automaticamente durante la quiete |
| 📥 **Asset online** | Download sequenziale di 16 immagini Aura |
| 📊 **Boot progressivo** | 18 passaggi: Wi-Fi, Home Assistant e 16 asset |
| 🔄 **OTA** | Aggiornamento firmware tramite ESPHome |
| 🧩 **API HA** | Azioni richiamabili da Home Assistant |
| 🖨️ **Parte stampabile** | Piatto superiore adattato disponibile in formato STL |

---

## 🔧 Hardware supportato

| Componente | Dettaglio |
|---|---|
| MCU | ESP32-S3 dual core, 240 MHz |
| Flash | 16 MB |
| PSRAM | Octal PSRAM a 80 MHz |
| Display | GC9A01A rotondo, 240×240 |
| Bus display | SPI |
| Touch | Non presente |
| Codec speaker | ES8311 |
| Codec microfoni | ES7210 |
| Expander I/O | TCA9555, indirizzo `0x20` |
| LED | 7 × WS2812 |
| Controlli | Tre pulsanti su TCA9555 |
| Connettività | Wi-Fi 2.4 GHz |

---

## 🖨️ Piatto superiore stampabile in 3D

Nel repository è disponibile anche il modello 3D del **piatto superiore modificato**, realizzato per integrare il display rotondo nella struttura originale di Aura.

### File disponibile

[**Supporto_piatto_slitta_inferiore_v2.stl**](./Supporto_piatto_slitta_inferiore_v2.stl)

Il modello prevede:

- supporto superiore sostitutivo;
- slitta nella parte inferiore per inserire il display circolare;
- parte posteriore aperta per lasciare spazio ai collegamenti;
- passaggio libero per i cavi del display;
- apertura laterale in prossimità della porta USB e dei cavi della board.

> [!NOTE]
> Prima della stampa definitiva è consigliato eseguire una prova rapida della slitta e verificare eventuali tolleranze legate alla propria stampante e al materiale utilizzato.

---

## 🧷 Pinout principale

### Display GC9A01A SPI

| Segnale | Pin |
|---|---|
| CS | `GPIO3` |
| CLK | `GPIO4` |
| DC | `GPIO7` |
| MOSI | `GPIO9` |

Configurazione display utilizzata:

```yaml
display:
  - platform: mipi_spi
    model: GC9A01A
    rotation: 0
    color_order: BGR
    invert_colors: true
    data_rate: 80MHz
    color_depth: 16
```

### Bus I²C

| Segnale | Pin |
|---|---|
| SCL | `GPIO10` |
| SDA | `GPIO11` |

### Audio I2S

| Segnale | Pin |
|---|---|
| MCLK | `GPIO12` |
| BCLK | `GPIO13` |
| LRCLK | `GPIO14` |
| DIN microfono | `GPIO15` |
| DOUT speaker | `GPIO16` |

### Anello LED

| Voce | Valore |
|---|---|
| Pin dati | `GPIO38` |
| Numero LED | `7` |
| Chipset | `WS2812` |
| Ordine colore | `RGB` |
| Effetto predefinito | `Aura Sync` |

### TCA9555

| Funzione | Pin espansore |
|---|---:|
| Controllo amplificatore | `8` |
| Pulsante volume − | `9` |
| Pulsante play/pausa | `10` |
| Pulsante volume + | `11` |
| RTC interrupt | `5` |

---

## 🧱 Architettura firmware

```text
ESP32-S3
├─ Display GC9A01A SPI
│  └─ Interfaccia LVGL 240×240
├─ Online Image
│  └─ 16 asset Aura scaricati da GitHub
├─ Anello LED WS2812
│  └─ Effetto Aura Sync
├─ TCA9555
│  ├─ Amplificatore
│  ├─ Volume −
│  ├─ Play / pausa
│  └─ Volume +
├─ Audio Codec ES8311
├─ Microphone ADC ES7210
├─ Speaker Pipeline
│  ├─ Media pipeline
│  └─ Announcement / TTS pipeline
├─ Voice Assistant
│  ├─ microWakeWord
│  ├─ STT / TTS Home Assistant
│  ├─ timer
│  └─ stati assistente
├─ Sound Level
│  ├─ RMS per il VU meter
│  └─ Peak per bocca e rilevamento rumore
└─ Home Assistant API actions
```

### Fasi del Voice Assistant

| Valore | Stato | Comportamento |
|---:|---|---|
| `1` | Idle | Aura pronta alla wake word |
| `2` | Waiting | Wake word rilevata, attesa comando |
| `3` | Listening | L’utente sta parlando |
| `4` | Thinking | Comando in elaborazione |
| `5` | Replying | Risposta TTS in corso |
| `10` | Not ready | Home Assistant o Voice Assistant non disponibili |
| `11` | Error | Errore della pipeline |

---

## 👩 Aura e interfaccia LVGL

Aura occupa l’intero display rotondo da 240×240 pixel e cambia espressione in base allo stato del dispositivo.

| Stato | Comportamento visivo |
|---|---|
| Idle | Blink naturale ed espressioni casuali |
| Waiting | Aura attende il comando |
| Listening | Espressione dedicata all’ascolto |
| Thinking | Occhi rivolti verso l’alto |
| Replying | Bocca animata in funzione del livello del TTS |
| Musica | Pose Dance, note animate e VU meter |
| Timer scaduto | Stato rosso dedicato |
| Sonno | Occhi chiusi, scena attenuata e `Zzz...` |
| Errore | Colori e stato visivo dedicati |
| Non connessa | Aura resta visibile con indicazione di connessione assente |

### Boot grafico

Durante l’avvio vengono mostrati:

1. collegamento alla rete Wi-Fi;
2. collegamento all’API di Home Assistant;
3. download sequenziale dei 16 asset grafici;
4. barra di avanzamento in 18 passaggi;
5. percentuale di completamento;
6. indicazione dell’asset in download;
7. passaggio automatico alla pagina principale.

Tre punti luminosi orbitano attorno al logo HackMyHome mentre l’anello LED fisico mostra una cometa azzurra.

### Bocca audio-reattiva

Durante il TTS il firmware utilizza `playback_peak` per selezionare i frame della bocca:

- chiusa;
- poco aperta;
- apertura media;
- molto aperta.

Il segnale viene smussato con attacco rapido e rilascio più lento, quindi modulato per simulare sillabe, pause e micro-chiusure.

### Modalità sonno

Dopo un periodo di quiete Aura:

- chiude gli occhi;
- attenua la scena;
- mostra le animazioni `Zzz...`;
- mantiene visibile l’orologio;
- riduce la luminosità dell’anello LED.

Aura si risveglia quando rileva attività, rumore, musica, un timer o una nuova interazione con il Voice Assistant.

---

## 💡 Anello LED Aura Sync

L’effetto `Aura Sync` replica sul ring fisico gli stati mostrati dal display.

### Sincronizzazione normale

I sette LED seguono:

- rotazione degli archi LVGL;
- colore della fase Voice Assistant;
- intensità della risposta vocale;
- stato di connessione;
- sonno;
- timer;
- allarme.

### Palette delle fasi

| Stato | Colore |
|---|---|
| Waiting | Ciano |
| Listening | Verde |
| Thinking | Viola |
| Replying | Rosa |
| Error | Rosso |
| Not ready | Grigio |
| Sleep | Blu/grigio attenuato |

### Modalità musica

Durante la riproduzione:

- l’anello accelera;
- utilizza la stessa palette multicolore degli archi LVGL;
- segue il livello del VU meter;
- produce un breve flash bianco sui picchi più forti.

### Taratura dell’orientamento

```yaml
substitutions:
  led_ring_reverse: "false"
  led_ring_offset_deg: "0"
```

Imposta `led_ring_reverse` su `true` se la rotazione avviene nel verso opposto.

Modifica `led_ring_offset_deg` per allineare il primo LED alla parte superiore del display. Con sette LED, un passo corrisponde a circa 51°.

---

## 🔘 Pulsanti fisici

Poiché questa migrazione non utilizza il touchscreen, i comandi locali principali restano affidati ai pulsanti originali.

| Pulsante | Funzione |
|---|---|
| K1 | Volume − |
| K2 | Play / pausa |
| K3 | Volume + |

I pulsanti del volume generano anche un breve flash bianco sull’anello LED senza interrompere l’effetto `Aura Sync`.

Le altre configurazioni restano disponibili tramite le entità esposte in Home Assistant.

---

## 🎙️ Voice Assistant

Il firmware utilizza il componente `voice_assistant` di ESPHome con microfono I2S e media player speaker.

### Funzioni incluse

- wake word locale;
- modalità singola o continua;
- ascolto e risposta tramite Home Assistant;
- ducking dell’audio durante l’ascolto;
- eventi Home Assistant per testo STT e URI TTS;
- animazione della bocca durante la risposta;
- gestione timer;
- stop word temporanea;
- riavvio controllato di microWakeWord;
- timeout della modalità continua dopo inattività.

### Wake word configurate

| Modello | Uso |
|---|---|
| `okay_nabu` | Wake word principale |
| `kenobi` | Wake word alternativa |
| `hey_jarvis` | Wake word alternativa |
| `stop` | Modello interno per interrompere timer e annunci |

### Sensibilità wake word

Da Home Assistant è disponibile il selettore:

```text
WakeWord - Sensibilita
├─ Poco sensibile
├─ Medio
└─ Molto sensibile
```

### Comandi locali

| Intento | Esempi |
|---|---|
| Volume su | “alza volume”, “aumenta volume” |
| Volume giù | “abbassa volume”, “riduci volume” |
| Modalità silenziosa | “modalità silenziosa” |
| Antifurto ON | “attiva antifurto”, “inserisci antifurto” |
| Antifurto OFF | “disattiva antifurto”, “disinserisci antifurto” |

---

## 🎵 Modalità musica e VU meter

Quando il media player entra nello stato `playing`, Aura attiva automaticamente la modalità musica.

La scena comprende:

- tre pose Dance;
- selezione casuale senza ripetizioni immediate;
- blink naturali;
- sei note animate;
- piccolo movimento orizzontale e verticale del personaggio;
- VU meter circolare;
- palette multicolore sincronizzata con i LED fisici.

### VU meter RMS

Il VU meter usa il valore `playback_rms`:

```cpp
constexpr float floor_db = -58.0f;
constexpr float full_scale_db = -1.0f;

float normalized =
  (rms_db - floor_db) / (full_scale_db - floor_db);

real_level = powf(normalized, 1.55f);
```

Lo smoothing applica:

```cpp
const float alpha =
  target > id(aura_music_level) ? 0.58f : 0.14f;
```

Soglie colore:

- verde sotto il 70%;
- giallo dal 70%;
- arancione/rosso dal 90%.

Se il livello reale non è disponibile o è quasi fermo, viene mantenuto un leggero ritmo sintetico per evitare che l’animazione si blocchi completamente.

---

## ⏱️ Timer e sveglia

### Timer Voice Assistant

Il firmware conserva le informazioni del primo timer attivo:

- nome;
- durata totale;
- secondi rimanenti;
- stato;
- avanzamento grafico.

Alla scadenza:

- viene riprodotto il suono configurato;
- viene abilitata temporaneamente la stop word;
- Aura mostra `TIMER SCADUTO`;
- display e anello LED passano al rosso;
- il media player viene sottoposto a ducking.

### Sveglia locale

Sono disponibili:

- ora in formato `HH:MM`;
- switch `Sveglia attiva`;
- selezione dell’azione;
- fuso orario POSIX configurabile via API.

| Azione | Comportamento |
|---|---|
| Riproduci suono | Riproduce il suono locale |
| Invia evento | Invia `esphome.alarm_ringing` a Home Assistant |
| Suono ed evento | Esegue entrambe le azioni |

---

## 🛡️ Rilevamento rumore e antifurto

Il componente `sound_level` misura:

- `RMS`, usato dal VU meter musicale;
- `Peak`, usato per la bocca e per il rilevamento del rumore.

La soglia è regolabile tra `-75 dB` e `-25 dB`.

Per ridurre i falsi trigger, il rilevamento viene ignorato quando:

- il dispositivo sta riproducendo musica;
- è in corso un annuncio;
- il timer sta suonando;
- è già in corso un allarme.

Quando `Modalità antifurto` è attiva e il rumore supera la soglia:

- viene eseguito lo script di allarme;
- l’anello LED alterna rosso e blu;
- Aura si risveglia;
- lo stato resta disponibile in Home Assistant.

> [!WARNING]
> Questa funzione è sperimentale e non sostituisce un impianto antifurto certificato.

---

## 🧩 Entità Home Assistant

<details>
<summary><strong>Select</strong></summary>

| Entità | Funzione |
|---|---|
| `Display - Emozione` | Forza l’espressione di Aura |
| `WakeWord - Sensibilita` | Regola la sensibilità di `okay_nabu` |
| `Livello log` | Cambia il livello dei log ESPHome |
| `Sveglia - Azione` | Sceglie cosa fare alla sveglia |

</details>

<details>
<summary><strong>Switch</strong></summary>

| Entità | Funzione |
|---|---|
| `Modalità antifurto` | Attiva o disattiva l’antifurto acustico |
| `Assistente - Ascolto continuo` | Abilita la conversazione continua |
| `Amplificatore` | Controlla l’amplificatore audio |
| `Microfono disattivato` | Disattiva microfono e wake word |
| `Suono Mute-Unmute` | Abilita il feedback sonoro |
| `Suono Wake Word` | Abilita il suono alla wake word |
| `Sveglia attiva` | Abilita la sveglia |
| `Controllo nuovo firmware` | Abilita la verifica remota della versione |

</details>

<details>
<summary><strong>Number</strong></summary>

| Entità | Range | Funzione |
|---|---:|---|
| `Soglia Rumore` | `-75` → `-25 dB` | Soglia di rilevamento |
| `Mic-Guadagno` | `0` → `42` | Guadagno ES7210 |
| `VA-Guadagno` | `1` → `64` | Gain factor Voice Assistant |
| `Sopp. Rumore` | `0` → `4` | Noise suppression |

</details>

<details>
<summary><strong>Sensor e Text Sensor</strong></summary>

| Entità | Tipo | Funzione |
|---|---|---|
| `Prossimo timer` | Sensor | Secondi rimanenti |
| `Prossimo timer - Nome` | Text sensor | Nome del timer |
| `Ora sveglia` | Text sensor | Orario impostato |
| `Ora dispositivo` | Text sensor | Ora locale |

I sensori RMS e Peak restano interni al firmware.

</details>

<details>
<summary><strong>Binary Sensor</strong></summary>

| Entità | Funzione |
|---|---|
| `K1 Volume -` | Pulsante volume giù |
| `K2 Play-Pausa` | Pulsante play/pausa |
| `K3 Volume +` | Pulsante volume su |
| `Rilevamento rumore` | Segnala il superamento della soglia |

</details>

<details>
<summary><strong>Light, Media Player e Button</strong></summary>

| Entità | Funzione |
|---|---|
| `Anello LED` | Controllo del ring WS2812 e degli effetti |
| Media player Aura | Media e annunci TTS |
| `Test antifurto` | Simula il trigger acustico |
| `Riavvia` | Riavvia il dispositivo |
| `Controlla nuovo firmware` | Esegue il controllo versione |

</details>

---

## 🔌 Azioni API

| Azione | Parametri | Descrizione |
|---|---|---|
| `set_led_color` | `red`, `green`, `blue` | Aggiorna il colore logico del ring |
| `start_va` | — | Avvia il Voice Assistant |
| `stop_va` | — | Ferma il Voice Assistant |
| `set_alarm_time` | `alarm_time_hh_mm` | Imposta la sveglia |
| `set_time_zone` | `posix_time_zone` | Imposta il fuso POSIX |

Esempio:

```yaml
action: esphome.home_assistant_voice_speaker_start_va
```

> Il nome reale dell’azione dipende dal valore di `device_name`.

---

## 🚀 Installazione

### Requisiti

- Home Assistant;
- ESPHome **2026.6.3 o successivo**;
- pipeline Assist configurata;
- connessione Internet durante il primo avvio;
- display GC9A01A collegato ai pin indicati;
- asset Aura raggiungibili su GitHub.

### Procedura

1. Collega il display GC9A01A alla board.
2. Verifica attentamente alimentazione e pin SPI.
3. Copia il file YAML nel progetto ESPHome.
4. Sostituisci credenziali, chiavi e indirizzi.
5. Valida la configurazione.
6. Compila il firmware.
7. Esegui il primo flash via USB.
8. Attendi la connessione Wi-Fi.
9. Attendi il collegamento a Home Assistant.
10. Lascia completare il download dei 16 asset.
11. Verifica display, audio, microfoni, pulsanti e anello LED.
12. Stampa e monta il piatto superiore STL.

### Credenziali

> [!CAUTION]
> Non pubblicare password Wi-Fi, chiavi API, password OTA, indirizzi IP privati o altri segreti.

Utilizza `secrets.yaml`:

```yaml
substitutions:
  ssid: !secret wifi_ssid
  password: !secret wifi_password
  api_key: !secret aura_api_key
  ota_key: !secret aura_ota_password
```

Esempio:

```yaml
wifi_ssid: "NOME_RETE"
wifi_password: "PASSWORD_WIFI"
aura_api_key: "CHIAVE_API_BASE64"
aura_ota_password: "PASSWORD_OTA"
```

### Substitutions principali

```yaml
substitutions:
  device_name: home-assistant-voice-speaker
  friendly: "Home Assistant Voice Speaker"
  fw_version: "0.4.1-lvgl-aura-gc9a01a-led-sync"

  ip: "192.168.xxx.xxx"
  gateway: "192.168.xxx.xxx"
  subnet: "255.255.255.0"
  dns: "192.168.xxx.xxx"

  led_ring_reverse: "false"
  led_ring_offset_deg: "0"
```

Per usare DHCP, rimuovi il blocco `manual_ip` dalla sezione `wifi:`.

### Primo avvio

Il download degli asset è intenzionalmente sequenziale. Questa scelta riduce il rischio di esaurimento della memoria mentre ESP32-S3 gestisce contemporaneamente:

- Wi-Fi;
- TLS;
- PNG;
- LVGL;
- audio;
- Voice Assistant.

Non interrompere l’alimentazione finché la barra non raggiunge il 100%.

---

## 🖼️ Asset grafici Aura

Gli asset vengono scaricati da:

[MarcoFre/images-aura](https://github.com/MarcoFre/images-aura)

La sequenza contiene 16 immagini:

1. idle;
2. blink a metà;
3. occhi chiusi;
4. occhi a sinistra;
5. occhi a destra;
6. occhi in alto;
7. viso in alto;
8. viso in basso;
9. mezzo sorriso;
10. sorriso completo;
11. bocca poco aperta;
12. bocca aperta;
13. bocca molto aperta;
14. Dance 01;
15. Dance 02;
16. Dance 03.

Le immagini vengono ridimensionate a 240×240 e convertite in RGB565.

Il download utilizza:

```yaml
buffer_size: 32768
update_interval: never
```

Ogni asset avvia il successivo dopo una breve pausa, evitando download concorrenti.

---

## 🛠️ Troubleshooting

### Display nero

Controlla:

- alimentazione del display;
- `CS` su `GPIO3`;
- `CLK` su `GPIO4`;
- `DC` su `GPIO7`;
- `MOSI` su `GPIO9`;
- modello `GC9A01A`;
- `invert_colors: true`;
- `color_order: BGR`;
- PSRAM attiva;
- cavi corti e collegamenti stabili.

Se il display è instabile, prova temporaneamente:

```yaml
data_rate: 40MHz
```

### Colori errati

Verifica:

```yaml
color_order: BGR
invert_colors: true
```

Il firmware forza inoltre l’inversione del GC9A01A dopo l’avvio.

### Immagine ruotata

Modifica:

```yaml
rotation: 0
```

Provando, in base al montaggio fisico:

```yaml
rotation: 90
rotation: 180
rotation: 270
```

### Anello LED ruota al contrario

Imposta:

```yaml
led_ring_reverse: "true"
```

### Anello LED non allineato al display

Regola:

```yaml
led_ring_offset_deg: "51"
```

Procedi per passi di circa 51°.

### Audio assente

Controlla:

- ES8311 su I²C;
- ES7210 su I²C;
- amplificatore abilitato;
- pin I2S;
- volume del media player;
- clock condivisi;
- sample rate a 16 kHz;
- stato dello switch `Amplificatore`.

### Microfono o wake word non funzionano

Controlla:

- `Microfono disattivato` su OFF;
- guadagno ES7210;
- gain factor del VA;
- noise suppression;
- connessione API;
- pipeline Assist;
- log di microWakeWord.

### Wake word non riparte dopo un annuncio

Lo script di ripristino verifica che:

- API e Voice Assistant siano connessi;
- il microfono non sia disattivato;
- il timer non stia suonando;
- non sia già attivo un Voice Assistant;
- il media player non stia riproducendo o annunciando.

### Boot fermo su un asset

Verifica:

- connessione Internet;
- DNS;
- raggiungibilità di `raw.githubusercontent.com`;
- data e ora corrette per TLS;
- esistenza dell’immagine indicata;
- memoria disponibile.

Il firmware riprova periodicamente il download se la sequenza non è stata completata.

### Errori di memoria

- mantieni PSRAM Octal a 80 MHz;
- non aumentare contemporaneamente numero e risoluzione degli asset;
- conserva i download sequenziali;
- non aumentare inutilmente i buffer;
- mantieni `compile_process_limit: 1`;
- evita ulteriori immagini residenti non necessarie.

### Aura non entra in modalità musica

Verifica che:

- il media player sia realmente nello stato `playing`;
- non sia attivo un timer;
- non sia in corso un annuncio;
- il Voice Assistant non sia in fase di ascolto o risposta;
- `playback_rms` venga aggiornato.

---

## 📁 Struttura del repository

```text
.
├── README.md
├── aura-gc9a01a.yaml
├── Supporto_piatto_slitta_inferiore_v2.stl
├── secrets.example.yaml
├── LICENSE
└── docs/
    ├── aura-gc9a01a.jpg
    ├── montaggio-display.jpg
    └── piatto-superiore.jpg
```

Aggiungi al `.gitignore`:

```gitignore
secrets.yaml
.esphome/
```

---

## 🗺️ Roadmap

- [x] Migrazione di Aura sul display GC9A01A 240×240.
- [x] Boot LVGL con avanzamento reale.
- [x] Download sequenziale dei 16 asset.
- [x] Bocca sincronizzata con il TTS.
- [x] Modalità musica con VU meter RMS.
- [x] Sincronizzazione degli archi LVGL con il ring WS2812.
- [x] Supporto dei tre pulsanti fisici.
- [x] Piatto superiore stampabile in 3D.
- [ ] Ottimizzazione dei tempi di avvio.
- [ ] Aggiunta di nuovi frame ed espressioni.
- [ ] Pagina diagnostica semplificata in Home Assistant.
- [ ] Profilo notturno configurabile.
- [ ] Ulteriori varianti del supporto STL.

---

## 🙌 Crediti

| Ruolo | Nome / progetto |
|---|---|
| Progetto e integrazione | HackMyHome / MarcoFre |
| Personaggio e asset grafici | Aura · [images-aura](https://github.com/MarcoFre/images-aura) |
| Verifica codice | Sanji78 |
| Codice voice speaker di riferimento | CaptainMustard |
| Componente ES8311 | [sw3Dan/waveshare-s2-audio_esphome_voice](https://github.com/sw3Dan/waveshare-s2-audio_esphome_voice) |
| Hardware | Waveshare ESP32-S3 Audio + GC9A01A |
| Firmware | ESPHome |
| Domotica e Voice Assistant | Home Assistant |
| Interfaccia grafica | LVGL |
| Modello 3D | Piatto superiore Aura con slitta inferiore |

---

## ⚠️ Disclaimer

Questo progetto è sperimentale e destinato a uso maker e domotico.

Verifica sempre:

- alimentazione;
- pinout;
- isolamento dei collegamenti;
- revisione hardware;
- stabilità del montaggio;
- corretta ventilazione;
- tolleranze del modello stampato.

La funzione di rilevamento del rumore non sostituisce un sistema antifurto certificato.

Non pubblicare mai su GitHub password Wi-Fi, chiavi API, chiavi OTA o indirizzi IP privati reali.
