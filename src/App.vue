<template>
    <div class="container">
      <Header class="header" title="Biz Start - Demonstration of Auto Form Fill Feature"/>
      <Form @update-person="updatePerson" :class="form1 === true ? 'hide' : ''"/>
      <Form2 v-if="form1" :info="info" @update-form2="updateForm2"  :class="form2 === true ? 'hide' : ''"/>
      <Form3 v-if="form2" :info="info" @update-form3="updateForm3" :class="form3 === true ? 'hide' : ''"/>
      <Conclusion v-if="form3" :info="info" />
      <div class="details-captured" :class="form3 === true ? 'hide' : ''">
        Details that we have captured so far which will aid auto form filling future forms:
        <br>
        {{ info }}
      </div>
    </div>
</template>
<script>
import Header from './components/Header.vue'
import Form from './components/Form.vue'
import Form2 from './components/Form2.vue'
import Form3 from './components/Form3.vue'
import Conclusion from './components/Conclusion.vue'

export default {
  name: 'App',
  components: {
    Header,
    Form,
    Form2,
    Form3,
    Conclusion,
  },
  data() {
    return {
      info: {},
      form1: false,
      form2: false,
      form3: false,
    }
  },
  methods: {
    updatePerson(person) {
      this.info = person
      this.form1 = true
    },
    updateForm2(person) {
      this.info = person
      this.form2 = true
    },
    updateForm3(person) {
      this.info = person
      this.form3 = true
    },
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 700px;
  margin: 30px auto;
  overflow: auto;
  min-height: 500px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.header{
  color: purple
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
.hide {
  display: none;
}
</style>
