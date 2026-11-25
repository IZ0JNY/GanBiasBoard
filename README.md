# GanBiasBoard

Scheda di bias e sequenziamento per amplificatori GaN — prima versione per il **Qorvo QPA1010** (MMIC GaN, 7,9–11 GHz,
circa 15 W) alimentato a **24 V**, usato a 10 GHz nella stazione EME di IZ0JNY.

Lo schema deriva dall'application note Wolfspeed *GaN HEMT Bias Sequencing and Temperature Compensation Circuit*, con le
modifiche descritte nel documento in `docs/`.

## Contenuto

| File | Cosa contiene |
|---|---|
| `kicad/qpa1010_bias.kicad_pro`, `kicad/qpa1010_bias.kicad_sch` | progetto e schema KiCad |
| `docs/qpa1010_bias_schematic.pdf` | lo schema stampato da KiCad |
| `docs/QPA1010_bias_24V_IZ0JNY.pdf` | modifiche per i 24 V rispetto all'application note: dati del QPA1010, cosa cambia e perché |
| `qpa1010_bias_BOM.csv` | distinta componenti (riferimenti, quantità, valori, footprint) |

## Dati del QPA1010 da rispettare

Dal datasheet Qorvo (verificare la revisione in uso):

- Vd consigliata 24 V, **Vd massima assoluta 29,5 V**;
- Idq 600 mA;
- Vg tipica da −1,5 a −2,9 V, Vg massima assoluta da −8 a 0 V.

**Sequenza:** prima la tensione negativa di gate, poi il drain; allo spegnimento il contrario. Senza Vg il drain non deve mai
essere alimentato.

## Stato

Schema da verificare prima di costruire il circuito stampato. Ancora aperto: la scelta del comparatore, TLV3011 o TLV3012.

---
Progetto di Ivan IZ0JNY.
