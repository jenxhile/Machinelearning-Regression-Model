# Rakennusten lämmityskuorman ennustaminen regressiomallilla
Tässä projektissa käytetään **lineaarista regressiota**, joka on koneoppimisen oppimismenetelmä. Tavoitteena on ennustaa rakennuksen lämmityskuorma sen eri ominaisuuksien perusteella. Mallinnuksessa keskitytään erityisesti siihen, kuinka hyvin valitut muuttujat selittävät lämmityskuorman vaihtelua ja miten mallia voidaan käyttää luotettavasti uusiin ennusteisiin.

Lineaarinen regressio sopii hyvin tähän analyysiin, koska se mallintaa riippuvuuden selittävien muuttujien ja kohdemuuttujan välillä selkeällä tavalla, ja mallin suorituskyky voidaan helposti arvioida selityskertoimen (R²) ja ennustevirheiden avulla.

## Analyysin tavoitteet
* Mallinnus ja ennustaminen: Selvittää, miten hyvin rakennuksen ominaisuudet, kuten kompaktius, seinän ala ja lasitusalue, voivat ennustaa lämmityskuormaa (kWh/m²).
* Ominaisuuksien merkittävyys: Tunnistaa, mitkä muuttujat ovat tilastollisesti merkittäviä ja miten ne vaikuttavat lämmityskuormaan.
* Mallin luotettavuus: Arvioida mallin suorituskykyä opetus- ja testidatalla sekä sen kykyä yleistyä uuteen dataan.

## Analyysin vaiheet
**Datan esikäsittely:**

* Käytetään Energy Efficiency -datasettiä, joka sisältää rakennusten ominaisuuksia (esim. pinta-ala, seinän ala) ja niiden lämmityskuormaa.
* Poistetaan selittävät muuttujat, joilla ei ole tilastollista merkitystä (esim. suuntautuminen p-arvon perusteella).
* Normalisoidaan data StandardScalerilla, jotta eri muuttujat olisivat yhteismitallisia.
**Mallin rakentaminen:**
  
* Käytetään lineaarista regressiomallia.
* Malli koulutetaan (fit) opetusdatalla, joka on jaettu testidatasta suhteessa 75 % / 25 %.
* Mallin arviointi:

**Arvioidaan mallin selityskykyä (R²) opetus- ja testidatalla.**
* Tarkastellaan ennustevirheitä (residuals) graafisesti hajontakuvioilla ja histogrammeilla.
  
**Uuden datan ennustaminen:**
* Sovelletaan mallia uusiin rakennustietoihin ja arvioidaan lämmityskuorma.
