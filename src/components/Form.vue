<template>
  <form @submit="onSubmit" class="add-form">
    <h2>Form 1 - Basic Personal Particulars Form</h2>
    <div class="form-control">
      <label>Name</label>
      <input type="text" v-model="name" name="name" placeholder="Name" />
    </div>
    <div class="form-control">
      <label>DOB</label>
      <input
        type="text"
        v-model="dob"
        name="dob"
        placeholder="DOB (dd/mm/yyyy)"
      />
    </div>
    <div class="form-control">
      <label>Position</label>
      <input
        type="text"
        v-model="position"
        name="position"
        placeholder="Position in Company e.g Director"
      />
    </div>
    <input type="submit" value="Submit Info" class="btn btn-block"/>
  </form>
</template>
<script>
export default {
  name: 'Form',
  data() {
    return {
      name: '',
      dob: '',
      position: '',
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
      const person = {
        name: this.name,
        dob: this.dob,
        position: this.position,
      }
      console.log(person)
      this.$emit('update-person', person)
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