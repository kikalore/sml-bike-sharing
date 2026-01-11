# Bike Sharing Predictions for Trento

<img src="./img/logo.png" alt="Hopsworks Logo" width="120" />

---

## Station selection

<select id="stationSelect" onchange="updateStation()">
<option value="bren_center">Bren Center</option>
<option value="top_center">Top Center</option>
<option value="piazza_centa">Piazza di Centa</option>
<option value="piazza_venezia">Piazza Venezia</option>
<option value="stazione_autocorriere">Stazione autocorriere</option>
<option value="biblioteca">Biblioteca</option>
<option value="universita">Università</option>
<option value="studentato_mayer">Studentato Mayer</option>
<option value="centro_santa_chiara">Centro Santa Chiara</option>
<option value="stazione_ospedale">Stazione FS Ospedale</option>
<option value="azienda_sanitaria">Azienda Sanitaria</option>
<option value="lidorno">Lidorno</option>
<option value="muse">Muse</option>
<option value="bezzi">Bezzi</option>
<option value="gardolo">Gardolo</option>
<option value="vannetti">Vannetti</option>
<option value="cimitero">Cimitero</option>
<option value="zuffo">Zuffo</option>
<option value="atesina_lidl">Ex-atesina Lidl</option>
<option value="mattarello">Mattarello</option>
<option value="campo_coni">Campo CONI</option>
<option value="borgata">Borgata</option>
<option value="mayer">Mayer</option>
<option value="verona">Verona</option>
<option value="clarina">Clarina</option>
<option value="barbacovi">Barbacovi</option>
<option value="gardolo_segheria">Gardolo-ex segheria</option>
<option value="maccani">Maccani</option>
<option value="canova">Canova</option>
<option value="piedicastello">Piedicastello</option>
<option value="madonna_bianca">Madonna Bianca</option>
<option value="stazione_villazzano">Stazione F.S. Villazzano</option>
<option value="san_bartolameo">Studentato San Bartolameo</option>
<option value="gorizia">Gorizia</option>
<option value="ospedale_santa_chiara">Ospedale Santa Chiara</option>
<option value="palatrento">PalaTrento</option>
<option value="roncafort">Roncafort</option>
<option value="cimitero_villazzano">Cimitero Villazzano</option>
<option value="piedicastello_italcementi">Piedicastello-Ex Italcementi</option>
<option value="ponte_cavalleggeri">Ponte dei Cavalleggeri</option>
<option value="ospedale_san_giovanni">Ospedale San Giovanni</option>
<option value="stazione_male">Stazione TN-Malè</option>
<option value="fiera">Piazza Fiera</option>
<option value="cavalleggeri">Cavalleggeri</option>
<option value="borgata">Borgata</option>
<option value="stazione_male2">Stazione TN-Malè 2</option>
<option value="municipio">Municipio</option>
<option value="mach">Mach</option>
<option value="zambana">Zambana</option>
<option value="stazione_fs">Stazione FS</option>
<option value="stazione_male3">Stazione TN-Malè 3</option>
<option value="aldeno">Aldeno</option>
<option value="besenello">Besenello</option>
<option value="calliano">Calliano</option>
<option value="nomi">Nomi</option>
<option value="stazione_fs2">stazione FS 2</option>
<option value="ospedale">Ospedale</option>
<option value="municipio2">Municipio 2</option>
<option value="mart">Mart</option>
<option value="zona_industriale">Zona Industriale</option>
<option value="paoli">Paoli</option>
<option value="lizzana">Lizzana</option>
<option value="sacco">Saccp</option>
<option value="noriglio">Noriglio</option>
<option value="brione">Brione</option>
<option value="rosmini">Rosmini</option>
<option value="quercia">Quercia</option>
<option value="orvea">Orvea</option>
<option value="stazione_mori">Stazione Mori</option>
<option value="balista">Balista</option>
<option value="piscina">Piscina</option>
<option value="baldresca">Baldresca</option>
<option value="follone">Follone</option>
<option value="cimitero">Cimitero</option>
<option value="polo_meccatronica2">Polo Meccatronica 2</option>
<option value="lizzanella">Lizzanella</option>
<option value="cartiera">Cartiera</option>
<option value="marangoni">Ex Marangoni</option>
<option value="volano">Volano</option>
<option value="pomarolo">Pomarolo</option>
<option value="villa_lagarina">Villa Lagarina</option>
<option value="piazzo">Piazzo</option>
<option value="nogaredo">Nogaredo</option>
<option value="isera">Isera</option>
<option value="cornale">Cornalè</option>
<option value="mori">Mori</option>
</select>

---

## Forecast

<img id="forecastImg" src="./img/bikes_forecast_10.01 Bren Center.png" alt="Forecast" width="100%" />

---

## Model Performance Monitoring

**1-Day Hindcast: Predictions vs Outcomes**

<img id="hindcastImg" src="./img/bikes_hindcast_1day_10.01 Bren Center.png" alt="Hindcast" width="100%" />

---

<script>
function updateStation() {
  const station = document.getElementById("stationSelect").value;

  const forecastMap = {
    bren_center: "./img/bikes_forecast_10.01 Bren Center.png",
    top_center: "./img/bikes_forecast_10.02 Top Center.png",
    piazza_centa: "./img/bikes_forecast_10.03 Piazza di Centa.png",
    piazza_venezia: "./img/bikes_forecast_10.04 Piazza Venezia.png",
    stazione_autocorriere: "./img/bikes_forecast_10.06 Stazione Autocorriere.png",
    biblioteca: "./img/bikes_forecast_10.07 Biblioteca.png",
    universita: "./img/bikes_forecast_10.08 Universita.png",
    centro_santa_chiara: "./img/bikes_forecast_10.09 Centro Santa Chiara.png",
    stazione_ospedale: "./img/bikes_forecast_10.11 Stazione F.S. - Ospedale.png",
    azienda_sanitaria: "./img/bikes_forecast_10.12 Azienda Sanitaria.png",
    lidorno: "./img/bikes_forecast_10.13 Lidorno.png",
    muse: "./img/bikes_forecast_10.15 Muse.png",
    bezzi: "./img/bikes_forecast_10.16 Bezzi.png",
    gardolo: "./img/bikes_forecast_10.17 Gardolo.png",
    vannetti: "./img/bikes_forecast_10.18 Vannetti.png",
    cimitero: "./img/bikes_forecast_10.19 Cimitero.png",
    zuffo: "./img/bikes_forecast_10.21 Zuffo - via Dos Trento.png",
    atesina_lidl: "./img/bikes_forecast_10.22 Ex Atesina - Lidl.png",
    mattarello: "./img/bikes_forecast_10.23 Mattarello.png",
    campo_coni: "./img/bikes_forecast_10.24 Campo CONI.png",
    studentato_mayer: "./img/bikes_forecast_10.25 Studentato Mayer.png",
    verona: "./img/bikes_forecast_10.26 Verona.png",
    clarina: "./img/bikes_forecast_10.27 Clarina.png",
    barbacovi: "./img/bikes_forecast_10.28 Barbacovi.png",
    gardolo_segheria: "./img/bikes_forecast_10.29 Gardolo - ex segheria.png",
    maccani: "./img/bikes_forecast_10.30 Maccani.png",
    canova: "./img/bikes_forecast_10.31 Canova.png",
    piedicastello: "./img/bikes_forecast_10.32 Piedicastello.png",
    stazione_villazzano: "./img/bikes_forecast_10.33 Stazione F.S. - Villazzano.png",
    madonna_bianca: "./img/bikes_forecast_10.34 Madonna Bianca.png",
    san_bartolameo: "./img/bikes_forecast_10.35 Studentato San Bartolameo.png",
    gorizia: "./img/bikes_forecast_10.36 Gorizia.png",
    ospedale_santa_chiara: "./img/bikes_forecast_10.37 Ospedale Santa Chiara.png",
    palatrento: "./img/bikes_forecast_10.38 PalaTrento.png",
    roncafort: "./img/bikes_forecast_10.39 Roncafort.png",
    cimitero_villazzano: "./img/bikes_forecast_10.40 Cimitero Villazzano.png",
    piedicastello_italcementi: "./img/bikes_forecast_10.41 Piedicastello-Ex Italcementi.png",
    ponte_cavalleggeri: "./img/bikes_forecast_10.42 Ponte dei Cavalleggeri.png",
    ospedale_san_giovanni: "./img/bikes_forecast_11.01 Ospedale San Giovanni.png",
    stazione_male: "./img/bikes_forecast_11.02 Stazione TN-Male`..png",
    fiera: "./img/bikes_forecast_11.03 Fiera.png",
    cavalleggeri: "./img/bikes_forecast_12.01 Cavalleggeri.png",
    borgata: "./img/bikes_forecast_12.02 Borgata.png",
    stazione_male2: "./img/bikes_forecast_12.03 Stazione TN-Male`.png",
    municipio: "./img/bikes_forecast_13.01 Municipio.png",
    mach: "./img/bikes_forecast_13.02 Mach.png",
    zambana: "./img/bikes_forecast_14.02 Zambana.png",
    stazione_fs: "./img/bikes_forecast_15.03 Stazione F.S..png",
    stazione_male3: "./img/bikes_forecast_15.04 Stazione TN-Male`.png",
    aldeno: "./img/bikes_forecast_16.01 Aldeno.png",
    besenello: "./img/bikes_forecast_17.01 Besenello.png",
    calliano: "./img/bikes_forecast_18.01 Calliano.png",
    nomi: "./img/bikes_forecast_19.01 Nomi.png",
    stazione_fs2: "./img/bikes_forecast_20.01 Stazione F.S..png",
    ospedale: "./img/bikes_forecast_20.02 Ospedale.png",
    municipio2: "./img/bikes_forecast_20.03 Municipio.png",
    mart: "./img/bikes_forecast_20.04 Mart.png",
    zona_industriale: "./img/bikes_forecast_20.05 Zona Industriale.png",
    paoli: "./img/bikes_forecast_20.06 Paoli.png",
    marco: "./img/bikes_forecast_20.07 marco.png",
    lizzana: "./img/bikes_forecast_20.08 Lizzana.png",
    sacco: "./img/bikes_forecast_20.09 Sacco.png",
    noriglio: "./img/bikes_forecast_20.10 Noriglio.png",
    brione: "./img/bikes_forecast_20.11 Brione.png",
    rosmini: "./img/bikes_forecast_20.12 Rosmini.png",
    quercia: "./img/bikes_forecast_20.13 Quercia.png",
    orvea: "./img/bikes_forecast_20.14 Orvea.png",
    stazione_mori: "./img/bikes_forecast_20.15 Stazione Mori.png",
    balista: "./img/bikes_forecast_20.16 Balista.png",
    piscina: "./img/bikes_forecast_20.17 Piscina.png",
    baldresca: "./img/bikes_forecast_20.18 Baldresca.png",
    follone: "./img/bikes_forecast_20.19 Follone.png",
    cimitero: "./img/bikes_forecast_20.20 Cimitero.png",
    polo_meccatronica2: "./img/bikes_forecast_20.21 Polo Meccatronica.png",
    lizzanella: "./img/bikes_forecast_20.22 Lizzanella.png",
    cartiera: "./img/bikes_forecast_20.23 Cartiera.png",
    marangoni: "./img/bikes_forecast_20.24 Ex Marangoni.png",
    volano: "./img/bikes_forecast_21.01 Volano.png",
    pomarolo: "./img/bikes_forecast_22.01 Pomarolo.png",
    villa_lagarina: "./img/bikes_forecast_23.01 Villa Lagarina.png",
    piazzo: "./img/bikes_forecast_23.02 Piazzo.png",
    nogaredo: "./img/bikes_forecast_24.01 Nogaredo.png",
    isera: "./img/bikes_forecast_25.01 Isera.png",
    cornale: "./img/bikes_forecast_25.02 Cornale`.png",
    mori: "./img/bikes_forecast_26.01 Mori.png"
  };

const hindcastMap = {};
for (const k in forecastMap) {
  hindcastMap[k] = forecastMap[k]
    .replace("bikes_forecast_", "bikes_hindcast_1day_");
}

  document.getElementById("forecastImg").src = forecastMap[station];
  document.getElementById("hindcastImg").src = hindcastMap[station];
}
</script>
