# Note delle librerie PECD_P7

I file di libreria non possono contenere commenti: KiCad li rifiuta
(verificato con KiCad 10.0.6, `kicad-cli`). Le note che stavano nei file
sono state spostate qui, con il numero di riga del file originale
(copia in `_originali_commentati/`).

## `PECD_P7.kicad_sym`

```
   5  =====================================================================
   6  E3M0016120K - SiC MOSFET 1200 V / 16 mOhm, TO-247-4L, automotive (AEC-Q101)
   7  Stessa piedinatura di tutta la famiglia Wolfspeed TO-247-4L: per il
   8  MOSFET di scarica (E3M0040120K) si usa lo stesso simbolo e si cambia Value.
   9  Pin 1 Drain, 2 Source di potenza, 3 Source di Kelvin, 4 Gate.
  10  Il terzo pin e' l'intera ragione della scelta del package: separa il
  11  ritorno del driver dal percorso di potenza (doc. ausiliari 1, §8.5).
  12  =====================================================================
  28  barra di gate
  31  canale a tre segmenti (enhancement mode)
  38  drain
  41  source di potenza
  44  bulk verso source
  47  freccia di bulk (canale N)
  50  diodo di corpo: e' il componente di libera circolazione reale,
  51  non c'e' Schottky esterno (doc. ausiliari 1, §1.2)
  62  ramo del source di Kelvin
  82  =====================================================================
  83  UCC21750DW - gate driver isolato rinforzato, DESAT, Miller clamp
  84  Lato primario a sinistra, secondario a destra, barriera al centro.
  85  =====================================================================
 103  barriera di isolamento rinforzato (2121 V DC, DIN EN IEC 60747-17)
 108  --- lato primario (riferito a GND) ---
 133  --- lato secondario (riferito a COM, flottante) ---
 161  =====================================================================
 162  AMC1302DWV - amplificatore isolato per shunt, ingresso +/-50 mV
 163  =====================================================================
 212  =====================================================================
 213  AMC1311DWV - amplificatore isolato ad alta impedenza, 0...2 V
 214  Stessa piedinatura dell'AMC1302: cambia solo il campo d'ingresso.
 215  =====================================================================
 226  =====================================================================
 227  MGJ2D121505SC - DC-DC isolato 2 W, +15 / -5 V, per gate drive
 228  =====================================================================
 268  =====================================================================
 269  Shunt a quattro terminali (Kelvin)
 270  I terminali di misura NON coincidono con quelli di potenza: e' il
 271  motivo per cui si sceglie un 4 terminali (doc. ausiliari 1, §8.4).
 272  =====================================================================
```

## `TO-247-4L_Wolfspeed_Vertical.kicad_mod`

```
  14  ---- corpo plastico, vista dall'alto -------------------------------
  15  E  = 15.9 nominale (15.75...16.13), centrato sul punto medio della
  16  fila di pin, cioe' x = 5.08
  17  D1 = 16.95 nominale (16.25...17.65)
  18  La quota verticale del corpo rispetto alla fila di pad dipende da
  19  quanto si infilano i reofori, che a sua volta dipende dal fissaggio
  20  meccanico al coldplate: qui si assume 2.0 mm di stacco. VERIFICARE
  21  sul prototipo meccanico prima di mandare in produzione.
  27  marcatore del pin 1
  31  ---- strato Fab: stessa sagoma piu' l'aletta metallica -------------
  36  l'aletta (drain) sporge oltre il corpo plastico fino a D = 23.5
  40  foro di fissaggio dell'aletta al coldplate (diametro 3.58 nominale),
  41  disegnato solo su Fab come riferimento meccanico: NON e' un foro PCB
  45  ---- courtyard ------------------------------------------------------
  51  ---- piazzole -------------------------------------------------------
  52  Spaziatura da datasheet: 1->2 = 5.08 mm, 2->3 = 3->4 = 2.54 mm.
  53  ATTENZIONE: NON e' il passo uniforme 5.45 mm del TO-247-3.
  54  
  55  ASOLA ALLARGATA A 1.45 mm (datasheet: 1.33). Il valore di datasheet e'
  56  pari alla larghezza MASSIMA del reoforo (b = 1.07...1.33): nel caso
  57  peggiore il gioco e' zero, accettabile per inserimento automatico ma
  58  non per montaggio e smontaggio a mano su un prototipo da banco.
  59  
  60  L'allargamento NON tocca nessuna distanza superficiale: la piazzola
  61  resta 1.84 mm e l'asola sta dentro di essa, quindi il gap rame-rame
  62  fra drain e source resta 5.08 - 1.84 = 3.24 mm. Cala solo l'anello,
  63  da 0.255 a 0.195 mm per lato, che e' ancora quattro volte il minimo
  64  IPC-6012 classe 2 (0.05 mm dopo metallizzazione).
  74  Nessun modello 3D: non ne esiste uno in questa libreria e referenziarne
  75  uno mancante fa lamentare il visualizzatore 3D a ogni apertura.
  76  Wolfspeed pubblica lo STEP del TO-247-4L: scaricarlo, metterlo in
  77  librerie/PECD_P7.3dshapes/ e aggiungere qui la riga (model ...).
```
