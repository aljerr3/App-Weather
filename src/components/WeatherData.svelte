<script lang="ts">
  export let weather;
</script>

<div class="animate__animated animate__fadeInUp col-12 col-md-6">
  <div class="card border-0 shadow-sm p-3 mb-5 bg-white rounded">
    <div class="card-body">
      <h1 class="card-title">Temperatura</h1>
      <hr />
      <h1>{weather.main.temp} C°</h1>
      <h4>
        Ciudad: <span class="fw-bold">{weather.name} {weather.sys.country}</span
        >
      </h4>
      <h4>
        Clima: <span class="fw-bold">{weather.weather[0].description}</span>
      </h4>
    </div>
  </div>
</div>

<div class="animate__animated animate__fadeInUp col-12 col-md-6">
  <div class="card border-0 shadow-sm p-3 mb-5 bg-white rounded">
    <div class="card-body">
      <h1 class="card-title">Max & Min</h1>
      <hr />
      <h4>
        Temperatura Max: <span class="fw-bold text-danger"
          >{weather.main.temp_min} °C</span
        >
      </h4>
      <h4>
        Temperatura Min: <span class="fw-bold text-primary"
          >{weather.main.temp_max} °C</span
        >
      </h4>
    </div>
  </div>
</div>

<style>
  .card-title {
    background-color: rgb(181, 8, 123);
    color: aliceblue;
    border-radius: 0.7rem;
  }

  .card-body {
    height: 260px;
    text-align: center;
    vertical-align: auto;
    background-color: rgb(242, 224, 246);
    border-radius: 0.7rem;
    border: 0px;
    color: rgb(53, 53, 53);
  }
  .card-body:hover {
    background-color: rgb(32, 0, 39);
    color: aliceblue;
  }
</style>
