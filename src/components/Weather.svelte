<script lang="ts">
  import App from "../App.svelte";
  import Loading from "./Loading.svelte";
  import WeatherData from "./WeatherData.svelte";
  import "animate.css";

  let city: string = "";
  const key = "e0f22e9ab2a737704691fb822205682d";

  const getWeatherData = async (city: string = "mexico city") => {
    if (city.trim() === "") {
      throw new Error("debe ingresar una ciudad en la búsqueda");
    }

    const res: Response = await fetch(
      `https://api.openweathermap.org/data/2.5/weather?q=${city}&units=metric&appid=${key}`
    );

    console.log(Response);
    if (!res.ok) {
      throw new Error("No existe el valor en la base de datos");
    }

    const data = await res.json();
    console.log(data);
    return data;
  };

  let promise = getWeatherData();

  const handleSubmit = () => {
    promise = getWeatherData(city);
    city = "";
  };
</script>

<div class="container">
  <div class="row">
    <div class="animate__animated animate__bounce col-12 mb-3">
      <form on:submit|preventDefault={handleSubmit}>
        <label>
          Ciudad: <input bind:value={city} type="text" class="form-control" />
        </label>
        <button style="color: aliceblue;" type="submit" class="btn btn-danger"
          >Buscar</button
        >
      </form>
    </div>
    {#await promise}
      <Loading />
    {:then weather}
      <WeatherData {weather} />
    {:catch err}
      .
      <div
        class="animate__animated animate__shakeX alert alert-danger"
        role="alert"
      >
        <strong>{err}</strong>
      </div>
    {/await}
  </div>
</div>
