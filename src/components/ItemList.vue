<template>
  <div>
    <li> {{ art.name }} </li>
  </div>
</template>

<script>
export default {
  name: 'ItemList',
  props: ['art']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css?family=Montserrat+Alternates');
  $primary-color: #f9f9f9;
  $secondary-color: #56BEC4;

  li {
    font-size: 30px;
    font-family: 'Montserrat Alternates', sans-serif;
    background: $primary-color;
    margin: 5px;
    border-radius: 2px;
    padding-left: 5px;
  }
</style>