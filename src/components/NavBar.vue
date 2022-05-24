<template>
  <nav class="navbar navbar-expand-lg bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Who's the jerk?</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup"
              aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <router-link class="nav-link active" aria-current="page" to="/">Home</router-link>
          <router-link class="nav-link active" aria-current="page" to="/about">About</router-link>
          <router-link class="nav-link active" aria-current="page" to="victim">Victim</router-link>

          <!--          <a class="nav-link active" aria-current="page" href="#">Home</a>
                    <a class="nav-link active" href="#">About</a>
                    <a class="nav-link active" href="#">jerk's victim</a>-->
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavBar'
}
</script>

<style scoped>
</style>
