<template>
<div>
  <div class="row">
    <div class="col">
      <h1 class="text-center mb-5">Promjena lozinke</h1>
    </div>
  </div>
  <div class="row">
    <div class="col"></div>
    <div class="col">
      
      <form @submit.prevent="novalozinka">

 <div class="form-group">
          <label for="newPassword">Nova lozinka</label>
          <input v-model="newPassword" type="password" class="form-control" id="newPassword" >
        </div>

        <button type="submit" class="btn btn-primary mt-5">Submit</button>
      </form>
 

    </div>
    <div class="col"></div>
  </div>
</div>
</template>


<script>
export default {
  
  data () {
    return {
      
      newPassword: ''
    }
  },
  methods: {
    novalozinka () {
 
 var user = firebase.auth().currentUser;


user.updatePassword(this.newPassword).then(function() {
  // Update successful.
}).catch(function(error) {
  // An error happened.
});




    }
  }
}
</script>
