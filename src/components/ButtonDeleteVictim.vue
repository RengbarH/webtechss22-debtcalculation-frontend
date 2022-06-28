<template>
  <button class="btn btn-success sticky-button" data-bs-toggle="offcanvas" data-bs-target="#persons-create-offcanvas" aria-controls="#persons-create-offcanvas">
    <i class="bi bi-person-dash-fill"></i>
  </button>
  <div class="offcanvas offcanvas-end" tabindex="-1" id="persons-create-offcanvas" aria-labelledby="offcanvas-label">
    <div class="offcanvas-header">
      <h5 id="offcanvas-label">Delete the Victim</h5>
      <button type="button" id="close-offcanvas" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
    </div>
    <div class="offcanvas-body">
      <form class="text-start">
        <div class="mb-3">
          <label for="test" class="form-label">test</label>
          <input type="number" class="form-control" id="test" placeholder="test">
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ButtonDeleteVictim'
}
</script>

<style scoped>
.sticky-button {
  position: fixed;
  bottom: 80px;
  right: 20px;
  padding: 10px 15px;
  border-radius: 30px;
}

.btn-success{
  background-color: red;
  border: none;
}
.btn-success:focus {
  background-color: red;
}
.btn-success:hover {
  background-color: red;
}

</style>
