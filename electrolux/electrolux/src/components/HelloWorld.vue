<template>
  <body>
    <div class="wrapper">
    <div id="iphone">
      <div id="camera"></div>
      <div id="speaker"></div>
      <div id="calculator">
        <div class="row">
          <p class="display target0">{{ equationDisplay }}</p>
          <div class="clear"></div>
        </div>
        <div class="row">
          <div class="clearout grey">AC</div>
          <div class="polarity-button grey">+/-</div>
          <div class="pct-button percent grey">%</div>
          <div class="event-button orange">/</div>
          <div class="clear"></div>
        </div>
        <div class="row">
          <button v-on:click="equationArrayMethod(7)" class="number white">7</button>
          <button v-on:click="equationArrayMethod(8)" class="number white">8</button>
          <button v-on:click="equationArrayMethod(9)" class="number white">9</button>
          <div class="event-button orange">*</div>
          <div class="clear"></div>
        </div>
        <div class="row">
          <button v-on:click="equationArrayMethod(4)" class="number white">4</button>
          <button v-on:click="equationArrayMethod(5)" class="number white">5</button>
          <button v-on:click="equationArrayMethod(6)" class="number white">6</button>
          <div class="event-button orange">-</div>
          <div class="clear"></div>
        </div>
        <div class="row">
          <button v-on:click="equationArrayMethod(1)" class="number white">1</button>
          <button v-on:click="equationArrayMethod(2)" class="number white">2</button>
          <button v-on:click="equationArrayMethod('3')" class="number white">3</button>
          <button v-on:click="equationArrayMethod('+')" class="event-button orange">+</button>
          <div class="clear"></div>
        </div>
        <div class="row">
          <div id="zero" class="number white">0</div>
          <div class="number white">.</div>
          <div v-on:click="resolveEquation()" class="equals orange">=</div>
          <div class="clear"></div>
        </div>
      </div> <!-- End calculator div -->
      <div id="home"></div>
      <div id="screen-bottom"></div>
    </div>
    </div>
  </body>
</template>

<script>
export default {
  name: 'VueHybrid',
  data () {
    return {
      equationArray: [],
      equationDisplay: []
    }
  },
  methods: {
    equationArrayMethod: function (symbol) {
      // when we click a number, add it to an array
      this.equationArray.push(symbol)
    },
    resolveEquation: function () {
      // when we click equal, resolve everything
      // alert(this.equationArray.join(""))
      var test = eval(this.equationArray.join(""))
      this.equationDisplay = test
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
.wrapper {
    background-color: aliceblue;
    border-color: turquoise;
    padding: 10px;
    border: solid;
    border-radius: 1%;
    text-align: center;
}
h1 {
    color: darkturquoise;
    font-size: 46px;
    font-family: monospace;
    text-align: center;
    padding: 70px;
    margin: 30px;
}
p {
    color: darkturquoise;
    font-size: 22px;
    font-family: monospace;
    text-align: center;
    padding: 70px;
    margin: 30px;
}
.footer {
    color: darkturquoise;
    font-size: 16px;
    font-family: Lobster;
    padding: 0px;
    margin: 10px;
}
.button-text {
    color: darkturquoise;
    font-size: 16px;
    font-family: sans-serif;
    text-align: center;
    padding: 20px;
    margin: 10px;
}
.clear {
    clear: both;
}
#iphone {
    border: solid;
    border-color: #433f3f;
    border-style: inset;
    border-width: 3px;
    height: 450px;
    width: 210px;
    border-radius: 20px 20px 20px 20px;
    box-shadow: 0px 59px 100px -19px #212121;
    background-color: #212121;
    margin-left: 50%;
    margin-top: 50vh;
    transform: translate(-50%, -50%);
    position: absolute;
}
#camera {
  border: solid;
  border-color: #191717;
  border-style: inset;
  border-width: 1px;
  border-radius: 50%;
  height: 5.5px;
  width: 5.5px;
  margin: 20px 10px 10px 60px;
  float: left;
  background-color: #393636;
}

#speaker {
	border: solid;
	border-color: #191717;
  border-style: inset;
	border-width: 2px;
	border-radius: 4px 4px 4px 4px;
	height: 5px;
	width: 45px;
	margin: 20px 10px 10px 7px;
	float: left;
  background-color: #242222;
}
#calculator {
	margin: 50px 5px 5px 5px;
}
#home {
	border: solid;
	border-color: #433f3f;
  border-style: inset;
	border-width: 1px;
	border-radius: 50%;
	height: 40px;
	width: 40px;
	margin: auto;
  background-color: #171717;
}
.orange {
    background-color: rgb(240, 135, 66);
}
.grey {
    background-color: rgb(186, 181, 178);
}
.white {
    background-color: rgb(248, 244, 242);
}
p {
    color: white;
    font-family: helvetica;
    font-size: 48px;
    border: solid;
    margin-top: auto;
    margin-bottom: auto;
}
.number, .event-button, .clearout, .equals, .grey {
    float: left;
    font-family: helvetica;
    text-align: center;
	  padding-top: 12px;
    height: 50px;
    width: 50px;
    border: solid;
    box-sizing: border-box;    
}
.display {
    border: thin;
    border-color: black;
    box-sizing: border-box;
    height: 100px;
    width: 200px;
    float: left;
    text-align: right;
    background-color: black;
}
#zero {
    border: solid;
    box-sizing: border-box;
    height: 50px;
    width: 100px;
    padding-left: 18.75px;
    text-align: left;
    float: left;
    font-family: helvetica;
}
.highlight {
    border: solid;
    border-color: red;
}
.clicked {
    border-color: red;
}
</style>
