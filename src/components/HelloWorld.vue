<template>
<div>

  <div id="container-article" v-if="items != null">
    <figure v-for="(item, index) in items.data.articles" :key="index">
      <img :src="item.urlToImage" :alt="item.description">
      <figcaption>{{ item.title }}</figcaption> 
      <a class="myButton" :href="item.url">Lire l'article</a>
    </figure>
  </div>
  <div v-else>
    <center>
      <img src="../assets/loading.gif" alt="drapeau de france">
    </center>
  </div>

</div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data() {
    return {
      items: null,
    }
  },
  mounted () {
    axios
      .get('https://newsapi.org/v2/top-headlines?country=fr&apiKey=7d23d62c463d4805ace6aa208b623298')
      .then(response => (this.items = response))
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .myButton {
	background:-webkit-gradient(linear, left top, left bottom, color-stop(0.05, #63b8ee), color-stop(1, #468ccf));
	border-radius:6px;
	border:1px solid #3866a3;
	display:inline-block;
	cursor:pointer;
	color:#14396a;
	font-family:Arial;
	font-size:15px;
	font-weight:bold;
	padding:6px 24px;
	text-decoration:none;
	text-shadow:0px 1px 0px #7cacde;
  margin-top: 10px;
}
.myButton:hover {
	background:-webkit-gradient(linear, left top, left bottom, color-stop(0.05, #468ccf), color-stop(1, #63b8ee));
	filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#468ccf', endColorstr='#63b8ee',GradientType=0);
	background-color:#468ccf;
}
.myButton:active {
	position:relative;
	top:1px;
}


  #container-article{
    display: grid;
    grid-gap: 10px;
    grid-template-columns: repeat(3, 1fr);
  }

  figure {
    background: #b4b4b4;
    border: solid 2px #000;
    border-radius: 15px;
    padding: 20px;
  }

  figure >img {
    width: 100%;
  }

  @media screen and (max-width: 800px) {
    #container-article{
      display: grid;
      grid-gap: 10px;
      grid-template-columns: repeat(2, 1fr);
    }
  }

  @media screen and (max-width: 400px) {
    #container-article{
      display: grid;
      grid-gap: 10px;
      grid-template-columns: repeat(1, 1fr);
    
  }
}
</style>
