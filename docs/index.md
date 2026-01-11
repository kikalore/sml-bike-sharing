# Bike Sharing Predictions for Trento

<img src="./img/logo.png" alt="Hopsworks Logo" width="120" />

---

## Station selection

<select id="stationSelect" onchange="updateStation()">
  <option value="bren_center">Bren Center</option>
  <option value="piazza_fiera">Piazza Fiera</option>
  <option value="stazione_fs">Stazione FS</option>
  <option value="universita">Università</option>
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
    piazza_fiera: "./img/bikes_forecast_10.01 Piazza Fiera.png",
    stazione_fs: "./img/bikes_forecast_10.01 Stazione FS.png",
    universita: "./img/bikes_forecast_10.01 Universita.png",
  };

  const hindcastMap = {
    bren_center: "./img/bikes_hindcast_1day_10.01 Bren Center.png",
    piazza_fiera: "./img/bikes_hindcast_1day_10.01 Piazza Fiera.png",
    stazione_fs: "./img/bikes_hindcast_1day_10.01 Stazione FS.png",
    universita: "./img/bikes_hindcast_1day_10.01 Universita.png",
  };

  document.getElementById("forecastImg").src = forecastMap[station];
  document.getElementById("hindcastImg").src = hindcastMap[station];
}
</script>
