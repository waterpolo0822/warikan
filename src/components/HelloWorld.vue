<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      <label>合計<input v-model.number="totalPrice" type=number></label>÷
      <label>人数<input v-model.number="people" type=number></label>
    </p>
    <p>一人当たり...</p>
    <p class="unitPrice">{{ unitPrice }}<span>円</span></p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function(){
    return{
      totalPrice: '',
      people: ''
    }
  },
  computed: {
    unitPrice: function(){
      return Math.ceil(this.totalPrice/this.people);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
