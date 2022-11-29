<template>
  <v-container class="container">
    <div>
      <p class="nTheme chColor">1 2 3</p>
      <div class="title" style="margin-bottom:30px">
        <span class="calc chColor">calc</span>
        <span class="theme chColor">THEME</span>

        <div class="radio">
          <input class="button" type="radio" name="toggle" id="one" />
          <input class="button" type="radio" name="toggle" id="two" />
          <input class="button" type="radio" name="toggle" id="three" />
        </div>

      </div>
      <div class="row result">
        <p class="chColor">{{num}}</p>
      </div>
      <div class="row operations">
          <div class="btns">7</div>
          <div class="btns">8</div>
          <div class="btns">9</div>
          <div class="bluBtn">DEL</div>
          <div class="btns">4</div>
          <div class="btns">5</div>
          <div class="btns">6</div>
          <div class="btns">+</div>
          <div class="btns">1</div>
          <div class="btns">2</div>
          <div class="btns">3</div>
          <div class="btns">-</div>
          <div class="btns">.</div>
          <div class="btns">0</div>
          <div class="btns">/</div>
          <div class="btns">x</div>
          <div class="bluBtn difBtn">RESET</div>
          <div class="redBtn difBtn">=</div>
      </div>
    </div>
  </v-container>
</template>

<script>
  export default {
    name: 'calc',

    data(){
      return{
        num:0.01,
      }
    },
    mounted(){
      var buttons = document.getElementsByClassName("button");
      var arr = [...buttons];
      const letters = document.getElementsByClassName('chColor')
      const btns = document.getElementsByClassName('btns')
      const blueBtns = document.getElementsByClassName('bluBtn')
      const inputs = document.getElementsByClassName('button')


      arr.forEach((element, index) => {
        element.addEventListener("click", () => {
        element.style.opacity = "1";
    if (index == 0) {
      document.getElementsByClassName("result")[0].style.backgroundColor = "hsl(224, 37%, 12%)";
      document.getElementsByClassName("result")[0].style.color = "white";
      document.getElementsByClassName("operations")[0].style.backgroundColor = "hsl(223, 31%, 20%)";
      document.getElementsByClassName("redBtn")[0].style.backgroundColor = "hsl(6, 63%, 50%)";
      document.getElementsByClassName("redBtn")[0].style.borderColor =  "hsl(6, 70%, 34%)";
      document.getElementsByClassName("radio")[0].style.backgroundColor = "hsl(223, 31%, 20%)";
      document.getElementsByTagName("input")[1].style.backgroundColor =  "hsl(6, 63%, 50%)";
      for(var i = 0; i < letters.length; i++){
        letters[i].style.color = "white"
      }
      for(var i = 0; i < btns.length; i++){
        btns[i].style.backgroundColor = "hsl(30, 25%, 89%)"
        btns[i].style.borderColor = "hsl(28, 16%, 65%)"
        btns[i].style.color = "hsl(221, 14%, 31%)"
      }
      for(var i = 0; i < blueBtns.length; i++){
        blueBtns[i].style.backgroundColor = "hsl(225, 21%, 49%)"
        blueBtns[i].style.borderColor = "hsl(224, 28%, 35%)"
      }
      this.$emit('index', "0");
    } else if (index == 1) {
      document.getElementsByClassName("result")[0].style.backgroundColor = "hsl(0, 0%, 93%)";
      document.getElementsByClassName("result")[0].style.color = "hsl(60, 10%, 19%)";
      document.getElementsByClassName("operations")[0].style.backgroundColor = "hsl(0, 5%, 81%)";
      document.getElementsByClassName("redBtn")[0].style.backgroundColor = "hsl(25, 98%, 40%)";
      document.getElementsByClassName("redBtn")[0].style.borderColor =  "hsl(25, 99%, 27%)";
      document.getElementsByClassName("radio")[0].style.backgroundColor = "hsl(0, 5%, 81%)";
      document.getElementsByTagName("input")[1].style.backgroundColor =  "hsl(25, 98%, 40%)";
      for(var i = 0; i < letters.length; i++){
        letters[i].style.color = "hsl(60, 10%, 19%)"
      }
      for(var i = 0; i < btns.length; i++){
        btns[i].style.backgroundColor = "hsl(45, 7%, 89%)"
        btns[i].style.borderColor = "hsl(35, 11%, 61%)"
        btns[i].style.color = "hsl(60, 10%, 19%)"
      }
      for(var i = 0; i < blueBtns.length; i++){
        blueBtns[i].style.backgroundColor = "hsl(185, 42%, 37%)"
        blueBtns[i].style.borderColor = "hsl(185, 58%, 25%)"
      }
      this.$emit('index', "1");
    } else {
      document.getElementsByClassName("result")[0].style.backgroundColor = "hsl(268, 71%, 12%)";
      document.getElementsByClassName("result")[0].style.color = "white";
      document.getElementsByClassName("operations")[0].style.backgroundColor = "hsl(268, 71%, 12%)";
      document.getElementsByClassName("redBtn")[0].style.backgroundColor = "hsl(176, 100%, 44%)";
      document.getElementsByClassName("redBtn")[0].style.borderColor = "hsl(177, 92%, 70%)";
      document.getElementsByClassName("radio")[0].style.backgroundColor = "hsl(268, 71%, 12%)";
      document.getElementsByTagName("input")[2].style.backgroundColor =  "hsl(176, 100%, 44%)";
      for(var i = 0; i < letters.length; i++){
        letters[i].style.color = " hsl(52, 100%, 62%)"
      }
      for(var i = 0; i < btns.length; i++){
        btns[i].style.backgroundColor = "hsl(268, 47%, 21%)"
        btns[i].style.borderColor = "hsl(290, 70%, 36%)"
        btns[i].style.color = "hsl(52, 100%, 62%)"
      }
      for(var i = 0; i < blueBtns.length; i++){
        blueBtns[i].style.backgroundColor = "hsl(281, 89%, 26%)"
        blueBtns[i].style.borderColor = "hsl(285, 91%, 52%)"
      }
      this.$emit('index', "2");
    }

          arr
            .filter(function (item) {
              return item != element;
            })
            .forEach((item) => {
              item.style.opacity = "0";
            });
        });
      });

    },
    methods:{
      
    }
  }
</script>

<style>
.nTheme{
  color: white;
  text-align: right;
  margin-right: 4px;
  letter-spacing: 5px;
  transform: translateY(15px);
}
.theme{
  color: white;
  transform: translateX(90px);
  font-size: 12px;
  letter-spacing: 1px;
  font-family: 'League Spartan', sans-serif;
}
.title{
  display: flex;
  justify-content: space-between;
}
input[type=radio]{
  height: 20px;
  width: 20px;
  appearance: none;
  background-color: hsl(6, 63%, 50%);
  border-radius: 30px;
  opacity: 0;
}
input:hover {
  cursor: pointer;
}
#one {
  opacity: 1;
}
.radio{
  background-color: hsl(223, 31%, 20%);
  border-radius: 30px;
  width: 70px;
  display: flex;
  justify-content: center;
  padding-top: 5px;
}
.calc{
  color: white;
  font-size: 30px;
  font-family: 'League Spartan', sans-serif;
}
.container{
  display: flex;
  align-items: center;
  justify-content: center;
  margin: auto;
}
.result{
  margin-bottom: 10px;
  height: 100px;
  width: 400px;
  border-radius: 10px;
  background-color:hsl(224, 37%, 12%);
  color: white;
  text-align: right !important;
  flex-direction: row-reverse;
  font-size: 40px;
  padding-top: 25px;
  padding-right: 25px;
}
.operations{
  margin-top: 5px;
  height: 340px;
  width: 400px;
  padding: 10px;
  border-radius: 10px;
  background-color: hsl(223, 31%, 20%);
}
.btns{
  margin: 5px;
  width: 22%;
  height: 45px;
  background-color: hsl(30, 25%, 89%);
  text-align: center;
  border-radius: 10px;
  border-bottom: 4px solid hsl(28, 16%, 65%);
  font-size: 25px;
  color: hsl(221, 14%, 31%);
  padding-top: 5px;
}
.difBtn{
  padding-top: 5px;
  margin: 5px;
  width: 47% !important;
  height: 45px;
  background-color: hsl(30, 25%, 89%);
  text-align: center;
  border-radius: 10px;
  border-bottom: 4px solid hsl(28, 16%, 65%);
  font-size: 25px;
  color: hsl(221, 14%, 31%);
}
.bluBtn{
  margin: 5px;
  width: 22%;
  height: 45px;
  background-color: hsl(225, 21%, 49%);
  text-align: center;
  border-radius: 10px;
  color: white;
  border-bottom: 4px solid hsl(224, 28%, 35%);
  font-size: 25px;
  padding-top: 5px;
}
.redBtn{
  background-color: hsl(6, 63%, 50%);
  color: white;
  border-bottom: 4px solid  hsl(6, 70%, 34%);
}
</style>