<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <h2>Form 2 - Company Incorporation Form</h2>
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
      <label>Income Level</label>
      <input
        type="text"
        v-model="incomeLevel"
        name="incomeLevel"
        placeholder="Income Level"
      />
    </div>
    <div class="form-control">
      <label>Residential Address</label>
      <input
        type="text"
        v-model="residentialAddress"
        name="residentialAddress"
        placeholder="Residential Address"
      />
    </div>
    <input type="submit" value="Submit Info" class="btn btn-block"/>
  </form>
</template>
<script>
export default {
  name: 'Form2',
  props: {
    info: Object,
  },
  data() {
    return {
      name: this.info.name,
      dob: this.info.dob,
      position: this.info.position,
      incomeLevel: '',
      residentialAddress: '',
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
      if(!this.incomeLevel) {
        alert('Please add an income level')
        return
      }
      if(!this.residentialAddress) {
        alert('Please add a residential address')
        return
      }
      const person = {
        name: this.name,
        dob: this.dob,
        position: this.position,
        incomeLevel: this.incomeLevel,
        residentialAddress: this.residentialAddress
      }
      console.log(person)
      this.$emit('update-form2', person)
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