<template>
  <div class="container w-50 text-center">
  <form>
  <div class="form-row">
    <div class="form-group col-md-6">
      <label for="inputEmail4">Email</label>
      <input type="email" v-model.lazy="email.val" class="form-control" id="inputEmail4" placeholder="Email">
      {{email.val}}
    </div>
    <div class="form-group col-md-6">
      <label for="inputPassword4">Password</label>
      <input type="password" v-model.lazy="password" class="form-control" id="inputPassword4" placeholder="Password">
      {{password}}
    </div>
  </div>
  <div class="form-group">
    <label for="inputAddress">Address</label>
    <input type="text" v-model="adress" class="form-control" id="inputAddress" placeholder="1234 Main St">
    {{adress}}
  </div>
  <div class="form-group">
    <label for="inputAddress2">Address 2</label>
    <input type="text" v-model="adress2" class="form-control" id="inputAddress2" placeholder="Apartment, studio, or floor">
    {{adress2}}
  </div>
  <div class="form-row">
    <div class="form-group col-md-6">
      <label for="inputCity">City</label>
      <input type="text" v-model="city" class="form-control" id="inputCity">
      {{city}}
    </div>
    <div class="form-group col-md-4">
      <label for="inputState">State</label>
      <select id="inputState"
      class="form-control" v-model="regions">
        <option v-for="region in regions" :key=region>{{region}}</option>
      </select>
    </div>
    <div class="form-group col-md-2">
      <label for="inputZip">Zip</label>
      <input type="text" v-model="zip" class="form-control" id="inputZip">
      {{zip}}
    </div>
  </div>
  <div class="form-group">
    <div class="form-check">
      <input class="form-check-input" v-model="checkField" type="checkbox" id="gridCheck">
        I agree
        <span style="color: blue;">
        {{checkField}}
        </span>
    </div>
  </div>
  <button type="submit" @click.prevent="isSubmitted" class="btn btn-primary">Sign in</button>
</form>
  <div v-if="submitted" class="container border border-info text-center">
    <div class="text-center">
      <h3>Yours data</h3>
        <div class="row">
          <div class="col-6">email: {{email.val}}</div>
          <div class="col-6">adress: {{adress}}</div>
        </div>
        <div class="row">
          <div class="col-6">Zip: {{zip}}</div>
          <div class="col-6">City: {{city}}</div>
        </div>
    </div>
  </div>
</div>

</template>

<script>
export default {
  name: 'Forms',
  data() {
    return{
      errors: [],
      email: {
        required: true,
        type: String,
        default: '',
        val: '',
      },
      name: null,
      vorname: '',
      gender: '',
      password: '',
      adress: '',
      adress2: '',
      zip: '',
      checkField: 'ok',
      city: '',
      regions: ['wielkopolskie', 'lubuskie', 'mazownieckie', 'zachodniopomorskie',
      'śląskie',],
      region: '',
      submitted: false
    }
  },
  methods: {
    isSubmitted()
    {
      this.submitted = true;
    }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.container{
  background-color: grey;
}

.col-6{
  background-color: black;
  color: white;
  border-bottom: 1px white solid;
  border-right: 1px white solid;
  padding-left: 2px;
}

</style>
