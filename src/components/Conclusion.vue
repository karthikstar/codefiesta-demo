<template>
  <div>
    <h1>End Of Demonstration</h1>
    <h3>These are the details we have captured through the inputs from the 3 forms. These can aid us in helping to auto fill repeated fields which show up in different forms, which will improve user convenience, efficiency and time required to complete the large number of forms to set up a business in Singapore. These information can be stored on the database and an API can be used to request these information when necessary.</h3>
    <br>
    <h3>Name: {{ info.name }}</h3>
    <h3>DOB: {{ info.dob }}</h3>
    <h3>Position: {{ info.position }}</h3>
    <h3>Income Level: {{ info.incomeLevel }}</h3>
    <h3>Residential Address: {{ info.residentialAddress }}</h3>
    <h3>Ordinary Shares: {{ info.ordinaryShares }}</h3>
    <h3>Preference Shares: {{ info.preferanceShares }}</h3>
    <br>
    <h3 class="refresh">Please Refresh to restart the demo!</h3>
  </div>
</template>
<script>
export default {
  name: 'Conclusion',
  props: {
    info: Object,
  },
}
</script>
<style scoped>
.refresh {
  color: green
}
</style>