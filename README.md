
# Phased-Array Ultrasound Beamforming in MATLAB

Et individuelt prosjekt fra IN3015 ved Universitetet i Oslo.

I dette prosjektet implementerte jeg en beamformer for rekonstruksjon av
ultralydbilder fra phased-array-data. Implementasjonen ble sammenlignet med
en referanseimplementasjon i Ultrasound Toolbox (USTB).

## Mitt arbeid

- Implementerte beam-based beamforming fra bunnen av i MATLAB
- Beregnet sende- og mottaksforsinkelser for flere transmit events
- Tidsforsinket RF-kanaldata ved hjelp av interpolasjon
- Rekonstruerte ultralydbilder fra beamformede data
- Sammenlignet egen implementasjon med USTBs beamformer
- Undersøkte hvordan receive apodization, inkludert Hamming-vindu og
  $f$-nummer, påvirker bildekvaliteten

## Teknologi

- MATLAB
- Ultrasound Toolbox (USTB)
- Field II-data / ultralyddata i `.uff`-format

## Avhengigheter og data

Koden krever Ultrasound Toolbox (USTB), som ikke er inkludert i dette
repositoryet.

Prosjektet bruker også ultralyddata i `.uff`-format. Datafilene er ikke
inkludert, siden de er store og er knyttet til det opprinnelige
kurs-/USTB-oppsettet.

## Resultater

Resultatfigurer og sammenligninger er tilgjengelige i mappen `images/`.

## Merk

Dette repositoryet inneholder utvalgte filer fra mitt eget arbeid.
Det inneholder ikke USTB, komplette datasett, kursmateriell eller den
opprinnelige oppgaveteksten.
