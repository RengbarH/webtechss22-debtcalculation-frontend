<template>
  <button class="btn btn-success sticky-button" data-bs-toggle="offcanvas" data-bs-target="#persons-create-offcanvas" aria-controls="#persons-create-offcanvas">
    <i class="bi bi-person-plus-fill"></i>
  </button>
  <div class="offcanvas offcanvas-end" tabindex="-1" id="persons-create-offcanvas" aria-labelledby="offcanvas-label">
    <div class="offcanvas-header">
      <h5 id="offcanvas-label">New Person</h5>
      <button type="button" id="close-offcanvas" class="btn-close text-reset" data-bs-dismiss="offcanvas" aria-label="Close"></button>
    </div>
    <div class="offcanvas-body">
      <form class="text-start">
        <div class="mb-3">
          <label for="first-name" class="form-label">First name</label>
          <input type="text" class="form-control" id="first-name" placeholder="Enter your first name" v-model="firstName">
        </div>
        <div class="mb-3">
          <label for="last-name" class="form-label">Last name</label>
          <input type="text" class="form-control" id="last-name" placeholder="Enter your last name" v-model="lastName">
        </div>
        <div class="col-md-4">
          <label for="gender" class="form-label">Gender</label>
          <select id="gender" class="form-select" v-model="gender">
            <option value="" selected disabled>Choose your gender</option>
            <option value="MALE">Male</option>
            <option value="FEMALE">Female</option>
            <option value="DIVERSE">Diverse</option>
          </select>
        </div>
        <div class="mt-5">
          <button class="btn btn-primary me-3" type="submit" @click="createPerson">Create</button>
          <button class="btn btn-danger" type="reset">Reset</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name: 'ButtonCollapse',
  data () {
    return {
      firstName: '',
      lastName: '',
      gender: ''
    }
  },
  methods: {
    createPerson () {
      const endpoint = process.env.VUE_APP_BACKEND_BASE_URL + '/api/v1/creditor'

      const headers = new Headers()
      headers.append('Content-Type', 'application/json')

      const payload = JSON.stringify({
        firstName: this.firstName,
        lastName: this.lastName,
        gender: this.gender
      })

      const requestOptions = {
        method: 'POST',
        headers: headers,
        body: payload,
        redirect: 'follow'
      }

      fetch(endpoint, requestOptions)
        .catch(error => console.log('error', error))
    }
  }
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

#offcanvas-label {
  margin-top: 40px;
}

#close-offcanvas {
  margin-top: -70px;
}

.col-md-4{
  width: 220px;
}
</style>
