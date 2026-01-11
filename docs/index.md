# Bike Sharing Predictions for Trento

<img src="./img/logo.png" alt="Hopsworks Logo" width="120" />

---

## Station selection

<select id="stationSelect" onchange="updateStation()">
<option value="top_center">10.02 Top Center</option>
<option value="noriglio">20.10 Noriglio</option>
<option value="sacco">20.09 Sacco</option>
<option value="vannetti">10.18 Vannetti</option>
<option value="ospedale_san_giovanni">11.01 Ospedale San Giovanni</option>
<option value="azienda_sanitaria">10.12 Azienda Sanitaria</option>
<option value="mori">26.01 Mori</option>
<option value="studentato_mayer">10.25 Studentato Mayer</option>
<option value="palatrento">10.38 PalaTrento</option>
<option value="quercia">20.13 Quercia</option>
<option value="cimitero_villazzano">10.40 Cimitero Villazzano</option>
<option value="verona">10.26 Verona</option>
<option value="lizzanella">20.22 Lizzanella</option>
<option value="nomi">19.01 Nomi</option>
<option value="paoli">20.06 Paoli</option>
<option value="gorizia">10.36 Gorizia</option>
<option value="madonna_bianca">10.34 Madonna Bianca</option>
<option value="clarina">10.27 Clarina</option>
<option value="villa_lagarina">23.01 Villa Lagarina</option>
<option value="ospedale">20.02 Ospedale</option>
<option value="piazza_di_centa">10.03 Piazza di Centa</option>
<option value="borgata">12.02 Borgata</option>
<option value="stazione_tn_male">15.04 Stazione TN-Male</option>
<option value="barbacovi">10.28 Barbacovi</option>
<option value="lizzana">20.08 Lizzana</option>
<option value="gardolo_ex_segheria">10.29 Gardolo - ex segheria</option>
<option value="grazioli">15.01 Grazioli</option>
<option value="besenello">17.01 Besenello</option>
<option value="cimitero">10.19 Cimitero</option>
<option value="stazione_autocorriere">10.06 Stazione Autocorriere</option>
<option value="piazza_venezia">10.04 Piazza Venezia</option>
<option value="stazione_fs">20.01 Stazione F.S.</option>
<option value="pressano">15.02 Pressano</option>
<option value="mach">13.02 Mach</option>
<option value="campo_coni">10.24 Campo CONI</option>
<option value="piedicastello_ex_italcementi">10.41 Piedicastello - Ex Italcementi</option>
<option value="studentato_san_bartolomeo">10.35 Studentato San Bartolomeo</option>
<option value="centro_santa_chiara">10.09 Centro Santa Chiara</option>
<option value="calliano">18.01 Calliano</option>
<option value="cavalleggeri">12.01 Cavalleggeri</option>
<option value="piedicastello">10.32 Piedicastello</option>
<option value="brione">20.11 Brione</option>
<option value="maccani">10.30 Maccani</option>
<option value="polo_meccatronica">20.21 Polo Meccatronica</option>
<option value="ex_marangoni">20.24 Ex Marangoni</option>
<option value="fiera">11.03 Fiera</option>
<option value="piscina">20.17 Piscina</option>
<option value="gardolo">10.17 Gardolo</option>
<option value="zona_industriale">20.05 Zona Industriale</option>
<option value="roncafort">10.39 Roncafort</option>
<option value="mart">20.04 Mart</option>
<option value="volano">21.01 Volano</option>
<option value="rosmini">20.12 Rosmini</option>
<option value="balista">20.16 Balista</option>
<option value="orvea">20.14 Orvea</option>
<option value="marco">20.07 Marco</option>
<option value="aldeno">16.01 Aldeno</option>
<option value="municipio">13.01 Municipio</option>
<option value="biblioteca">10.07 Biblioteca</option>
<option value="ex_atesina_lidl">10.22 Ex Atesina - Lidl</option>
<option value="universita">10.08 Universita</option>
<option value="bren_center">10.01 Bren Center</option>
<option value="bezzi">10.16 Bezzi</option>
<option value="muse">10.15 Muse</option>
<option value="pomarolo">22.01 Pomarolo</option>
<option value="cartiera">20.23 Cartiera</option>
<option value="ponte_dei_cavalleggeri">10.42 Ponte dei Cavalleggeri</option>
<option value="isera">25.01 Isera</option>
<option value="canova">10.31 Canova</option>
<option value="ospedale_santa_chiara">10.37 Ospedale Santa Chiara</option>
<option value="mattarello">10.23 Mattarello</option>
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
    top_center: "./img/bikes_forecast_10.02 Top Center.png",
    noriglio: "./img/bikes_forecast_20.10 Noriglio.png",
    sacco: "./img/bikes_forecast_20.09 Sacco.png",
    vannetti: "./img/bikes_forecast_10.18 Vannetti.png",
    ospedale_san_giovanni: "./img/bikes_forecast_11.01 Ospedale San Giovanni.png",
    azienda_sanitaria: "./img/bikes_forecast_10.12 Azienda Sanitaria.png",
    mori: "./img/bikes_forecast_26.01 Mori.png",
    studentato_mayer: "./img/bikes_forecast_10.25 Studentato Mayer.png",
    palatrento: "./img/bikes_forecast_10.38 PalaTrento.png",
    quercia: "./img/bikes_forecast_20.13 Quercia.png",
    cimitero_villazzano: "./img/bikes_forecast_10.40 Cimitero Villazzano.png",
    verona: "./img/bikes_forecast_10.26 Verona.png",
    lizzanella: "./img/bikes_forecast_20.22 Lizzanella.png",
    nomi: "./img/bikes_forecast_19.01 Nomi.png",
    paoli: "./img/bikes_forecast_20.06 Paoli.png",
    gorizia: "./img/bikes_forecast_10.36 Gorizia.png",
    madonna_bianca: "./img/bikes_forecast_10.34 Madonna Bianca.png",
    clarina: "./img/bikes_forecast_10.27 Clarina.png",
    villa_lagarina: "./img/bikes_forecast_23.01 Villa Lagarina.png",
    ospedale: "./img/bikes_forecast_20.02 Ospedale.png",
    piazza_di_centa: "./img/bikes_forecast_10.03 Piazza di Centa.png",
    borgata: "./img/bikes_forecast_12.02 Borgata.png",
    stazione_tn_male: "./img/bikes_forecast_15.04 Stazione TN-Male.png",
    barbacovi: "./img/bikes_forecast_10.28 Barbacovi.png",
    lizzana: "./img/bikes_forecast_20.08 Lizzana.png",
    gardolo_ex_segheria: "./img/bikes_forecast_10.29 Gardolo - ex segheria.png",
    grazioli: "./img/bikes_forecast_15.01 Grazioli.png",
    besenello: "./img/bikes_forecast_17.01 Besenello.png",
    cimitero: "./img/bikes_forecast_10.19 Cimitero.png",
    stazione_autocorriere: "./img/bikes_forecast_10.06 Stazione Autocorriere.png",
    piazza_venezia: "./img/bikes_forecast_10.04 Piazza Venezia.png",
    stazione_fs: "./img/bikes_forecast_20.01 Stazione F.S..png",
    pressano: "./img/bikes_forecast_15.02 Pressano.png",
    mach: "./img/bikes_forecast_13.02 Mach.png",
    campo_coni: "./img/bikes_forecast_10.24 Campo CONI.png",
    piedicastello_ex_italcementi: "./img/bikes_forecast_10.41 Piedicastello - Ex Italcementi.png",
    studentato_san_bartolomeo: "./img/bikes_forecast_10.35 Studentato San Bartolomeo.png",
    centro_santa_chiara: "./img/bikes_forecast_10.09 Centro Santa Chiara.png",
    calliano: "./img/bikes_forecast_18.01 Calliano.png",
    cavalleggeri: "./img/bikes_forecast_12.01 Cavalleggeri.png",
    piedicastello: "./img/bikes_forecast_10.32 Piedicastello.png",
    brione: "./img/bikes_forecast_20.11 Brione.png",
    maccani: "./img/bikes_forecast_10.30 Maccani.png",
    polo_meccatronica: "./img/bikes_forecast_20.21 Polo Meccatronica.png",
    ex_marangoni: "./img/bikes_forecast_20.24 Ex Marangoni.png",
    fiera: "./img/bikes_forecast_11.03 Fiera.png",
    piscina: "./img/bikes_forecast_20.17 Piscina.png",
    gardolo: "./img/bikes_forecast_10.17 Gardolo.png",
    zona_industriale: "./img/bikes_forecast_20.05 Zona Industriale.png",
    roncafort: "./img/bikes_forecast_10.39 Roncafort.png",
    mart: "./img/bikes_forecast_20.04 Mart.png",
    volano: "./img/bikes_forecast_21.01 Volano.png",
    rosmini: "./img/bikes_forecast_20.12 Rosmini.png",
    balista: "./img/bikes_forecast_20.16 Balista.png",
    orvea: "./img/bikes_forecast_20.14 Orvea.png",
    marco: "./img/bikes_forecast_20.07 Marco.png",
    aldeno: "./img/bikes_forecast_16.01 Aldeno.png",
    municipio: "./img/bikes_forecast_13.01 Municipio.png",
    biblioteca: "./img/bikes_forecast_10.07 Biblioteca.png",
    ex_atesina_lidl: "./img/bikes_forecast_10.22 Ex Atesina - Lidl.png",
    universita: "./img/bikes_forecast_10.08 Universita.png",
    bren_center: "./img/bikes_forecast_10.01 Bren Center.png",
    bezzi: "./img/bikes_forecast_10.16 Bezzi.png",
    muse: "./img/bikes_forecast_10.15 Muse.png",
    pomarolo: "./img/bikes_forecast_22.01 Pomarolo.png",
    cartiera: "./img/bikes_forecast_20.23 Cartiera.png",
    ponte_dei_cavalleggeri: "./img/bikes_forecast_10.42 Ponte dei Cavalleggeri.png",
    isera: "./img/bikes_forecast_25.01 Isera.png",
    canova: "./img/bikes_forecast_10.31 Canova.png",
    ospedale_santa_chiara: "./img/bikes_forecast_10.37 Ospedale Santa Chiara.png",
    mattarello: "./img/bikes_forecast_10.23 Mattarello.png"
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
