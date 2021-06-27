<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <h2>Form 3 - Shares Allocation Form</h2>
      <label>Name</label>
      <input type="text" v-model="name" name="name" placeholder="Name" />
    </div>
    <div class="form-control">
      <label>DOB</label>
      <input
        type="text"
        v-model="dob"
        name="dob"
        placeholder="DOB"
      />
    </div>
    <div class="form-control">
      <label>Position</label>
      <input
        type="text"
        v-model="position"
        name="position"
        placeholder="Position"
      />
    </div>
    <div class="form-control">
      <label>Ordinary Shares</label>
      <input
        type="text"
        v-model="ordinaryShares"
        name="ordinaryShares"
        placeholder="Ordinary Shares e.g: 200"
      />
    </div>
    <div class="form-control">
      <label>Preference Shares</label>
      <input
        type="text"
        v-model="preferanceShares"
        name="preferanceShares"
        placeholder="Preference Shares e.g: 200"
      />
    </div>
    <input type="submit" value="Submit Info" class="btn btn-block"/>
  </form>
</template>
<script>
export default {
  name: 'Form3',
  props: {
    info: Object,
  },
  data() {
    return {
      name: this.info.name,
      dob: this.info.dob,
      position: this.info.position,
      incomeLevel: this.info.incomeLevel,
      residentialAddress: this.info.residentialAddress,
      ordinaryShares: '',
      preferanceShares: '',
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault()
      if(!this.name) {
        alert('Please add a name')
        return
      }
      if(!this.dob) {
        alert('Please add a date of birth')
        return
      }
      if(!this.position) {
        alert('Please add a position')
        return
      }
      if(!this.ordinaryShares) {
        alert('Please add allocated amount of Ordinary Shares')
        return
      }
      if(!this.preferanceShares) {
        alert('Please add allocated amount of Preference Shares')
        return
      }
      const person = {
        name: this.name,
        dob: this.dob,
        position: this.position,
        incomeLevel: this.incomeLevel,
        residentialAddress: this.residentialAddress,
        ordinaryShares: this.ordinaryShares,
        preferanceShares: this.preferanceShares,
      }
      console.log(person)
      this.$emit('update-form3', person)
    }
  }
}
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>