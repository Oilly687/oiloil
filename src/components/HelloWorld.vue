<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ msg1 }}</h2>
    <input type="text" v-model="message" placeholder="enter">
    <p>Message is : {{message}}</p>
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    msg1:String
  },
  data() {
    return {
      message:''
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
