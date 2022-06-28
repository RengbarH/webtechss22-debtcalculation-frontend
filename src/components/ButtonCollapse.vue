<template>
  <button class="btn btn-success sticky-button" data-bs-toggle="offcanvas" data-bs-target="#persons-create-offcanvas" aria-controls="#persons-create-offcanvas">
    <i class="bi bi-person-plus-fill"></i>
  </button>
  <div class="offcanvas offcanvas-end" tabindex="-1" id="persons-create-offcanvas" aria-labelledby="offcanvas-label">
    <div class="offcanvas-header">
      <h3 id="offcanvas-label">Do you want to add or redeem a new victim?</h3>
      <button type="button" id="close-offcanvas" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
    </div>
    <div class="offcanvas-body">
      <p class="offcanvas-btn-together">
        <button class="btn btn-primary1" type="button" data-bs-toggle="collapse" data-bs-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
          Add victim
        </button>
        <button class="btn btn-primary2" type="button" data-bs-toggle="collapse" data-bs-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
          reedem victim
        </button>
      </p>
      <div class="collapse" id="collapseExample">
        <div class="card card-body">
          Some placeholder content for the collapse component. This panel is hidden by default but revealed when the user activates the relevant trigger.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ButtonCollapse'
}
</script>

<style scoped>
.sticky-button {
  position: fixed;
  bottom: 20px;
  right: 20px;
  padding: 10px 15px;
  border-radius: 30px;
}

.btn-primary {
  margin: 15px;
}

#offcanvas-label {
  margin-top: 40px;

}

#close-offcanvas {
  margin-top: -70px;
}

.offcanvas-btn-together {
  margin: 70px;
}

.btn-primary1 {
  background-color: #c21f1f;
  text-align: center;
  border: none;
  color: #ffffff;
  font-family: inherit;
}
</style>
