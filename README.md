# Phased-Array Ultrasound Beamforming in MATLAB

Et individuelt prosjekt fra IN3015 ved Universitetet i Oslo.

Prosjektet utforsker rekonstruksjon av ultralydbilder fra phased-array-data.
Jeg implementerte en beam-based delay-and-sum-beamformer i MATLAB og
sammenlignet resultatet med en referanseimplementasjon i Ultrasound Toolbox
(USTB).

## Mitt bidrag

Med utgangspunkt i utdelt prosjektramme implementerte jeg den sentrale
beamforming-logikken:

- Beregning av sende- og mottaksforsinkelser for hvert transmit event og
  mottakselement
- Kompensasjon for tidsforskyvning mellom transmit events
- Interpolering av analytiske RF-signaler ved de beregnede forsinkelsene
- Summering av forsinkede signaler for å rekonstruere et ultralydbilde
- Sammenligning mellom egen implementasjon og USTBs delay-and-sum-beamformer
- Analyse av receive apodization ved bruk av Hamming-vindu med
  $f$-number $2$

## Teknologi

- MATLAB
- Ultrasound Toolbox (USTB)
- Delay-and-sum beamforming
- Phased-array ultrasound imaging

## Resultater

### Receive apodization

Figuren under sammenligner delay-and-sum-beamforming uten og med receive
apodization på et simulert datasett med punktspredere.

- Uten apodization vektes mottakselementene likt.
- Med receive apodization brukes et Hamming-vindu og $f$-number $2$.
- Apodization reduserer sidelober rundt punktsprederne, men kan samtidig
  gi en avveining mot lateral oppløsning.

![Comparison of receive apodization](images/receive-apodization-comparison.png)

## Avhengigheter og data

Koden krever Ultrasound Toolbox (USTB), som ikke er inkludert i dette
repositoryet.

Skriptet bruker et stort ultralyddatasett i `.uff`-format. Datasettet er
ikke inkludert, men skriptet er konfigurert til å hente det via USTBs
nedlastingsfunksjon når USTB er korrekt installert.

## Kjøre prosjektet

1. Installer MATLAB og Ultrasound Toolbox (USTB).
2. Legg USTB til i MATLAB-path.
3. Åpne prosjektmappen i MATLAB.
4. Kjør hovedskriptet.

## Merk

Repositoryet inneholder utvalgte filer fra mitt eget arbeid, inkludert min
beamforming-implementasjon. USTB, komplette datasett, kursmateriell og
opprinnelig oppgavetekst er ikke inkludert.
