# Bike Sharing Predictions for Trento

<img src="./img/logo.png" alt="Hopsworks Logo" width="120" />

---

## Station selection

<select id="stationSelect" onchange="updateStation()">
<option value="top_center">Top Center</option>
<option value="noriglio">Noriglio</option>
<option value="sacco">Sacco</option>
<option value="vannetti">Vannetti</option>
<option value="ospedale_san_giovanni">Ospedale San Giovanni</option>
<option value="azienda_sanitaria">Azienda Sanitaria</option>
<option value="mori">Mori</option>
<option value="studentato_mayer">Studentato Mayer</option>
<option value="palatrento">PalaTrento</option>
<option value="quercia">Quercia</option>
<option value="cimitero_villazzano">Cimitero Villazzano</option>
<option value="verona">Verona</option>
<option value="lizzanella">Lizzanella</option>
<option value="nomi">Nomi</option>
<option value="paoli">Paoli</option>
<option value="gorizia">Gorizia</option>
<option value="madonna_bianca">Madonna Bianca</option>
<option value="clarina">Clarina</option>
<option value="villa_lagarina">Villa Lagarina</option>
<option value="ospedale">Ospedale</option>
<option value="piazza_di_centa">Piazza di Centa</option>
<option value="borgata">Borgata</option>
<option value="stazione_tn_male">Stazione TN-Male</option>
<option value="barbacovi">Barbacovi</option>
<option value="lizzana">Lizzana</option>
<option value="gardolo_ex_segheria">Gardolo - ex segheria</option>
<option value="grazioli">Grazioli</option>
<option value="besenello">Besenello</option>
<option value="cimitero">Cimitero</option>
<option value="stazione_autocorriere">Stazione Autocorriere</option>
<option value="piazza_venezia">Piazza Venezia</option>
<option value="stazione_fs">Stazione F.S.</option>
<option value="pressano">Pressano</option>
<option value="mach">Mach</option>
<option value="campo_coni">Campo CONI</option>
<option value="piedicastello_ex_italcementi">Piedicastello - Ex Italcementi</option>
<option value="studentato_san_bartolomeo">Studentato San Bartolomeo</option>
<option value="centro_santa_chiara">Centro Santa Chiara</option>
<option value="calliano">Calliano</option>
<option value="cavalleggeri">Cavalleggeri</option>
<option value="piedicastello">Piedicastello</option>
<option value="brione">Brione</option>
<option value="maccani">Maccani</option>
<option value="polo_meccatronica">Polo Meccatronica</option>
<option value="ex_marangoni">Ex Marangoni</option>
<option value="fiera">Fiera</option>
<option value="piscina">Piscina</option>
<option value="gardolo">Gardolo</option>
<option value="zona_industriale">Zona Industriale</option>
<option value="roncafort">Roncafort</option>
<option value="mart">Mart</option>
<option value="volano">Volano</option>
<option value="rosmini">Rosmini</option>
<option value="balista">Balista</option>
<option value="orvea">Orvea</option>
<option value="marco">Marco</option>
<option value="aldeno">Aldeno</option>
<option value="municipio">Municipio</option>
<option value="biblioteca">Biblioteca</option>
<option value="ex_atesina_lidl">Ex Atesina - Lidl</option>
<option value="universita">Universita</option>
<option value="bren_center">Bren Center</option>
<option value="bezzi">Bezzi</option>
<option value="muse">Muse</option>
<option value="pomarolo">Pomarolo</option>
<option value="cartiera">Cartiera</option>
<option value="ponte_dei_cavalleggeri">Ponte dei Cavalleggeri</option>
<option value="isera">Isera</option>
<option value="canova">Canova</option>
<option value="ospedale_santa_chiara">Ospedale Santa Chiara</option>
<option value="mattarello">Mattarello</option>
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
