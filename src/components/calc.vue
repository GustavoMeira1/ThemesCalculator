<template>
  <v-container class="container">
    <div>
      <p class="nTheme">1 2 3</p>
      <div class="title" style="margin-bottom:30px">
        <span class="calc">calc</span>
        <span class="theme">THEME</span>
        <div class="radio">
          <input class="button" type="radio" name="toggle" id="one" />
          <input class="button" type="radio" name="toggle" id="two" />
          <input class="button" type="radio" name="toggle" id="three" />
        </div>
      </div>
      <div class="row result">
        <p>{{num}}</p>
      </div>
      <div class="row operations">
          <div class="btns">7</div>
          <div class="btns">8</div>
          <div class="btns">9</div>
          <div class="bluBtn btns">DEL</div>
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
        num:399.981
      }
    },
    mounted(){
      var buttons = document.getElementsByClassName("button");
var arr = [...buttons];

arr.forEach((element, index) => {
  element.addEventListener("click", () => {
    element.style.opacity = "1";

    arr
      .filter(function (item) {
        return item != element;
      })
      .forEach((item) => {
        item.style.opacity = "0";
      });
  });
});
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
  background-color: hsl(223, 31%, 20%) !important;
  border-radius: 30px;
  width: 70px;
  display: flex;
  justify-content: center;
  padding-top: 5px;
}
.calc{
  color: white;
  font-size: 30px;
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
  width: 47%;
  height: 45px;
  background-color: hsl(30, 25%, 89%);
  text-align: center;
  border-radius: 10px;
  border-bottom: 4px solid hsl(28, 16%, 65%);
  font-size: 25px;
  color: hsl(221, 14%, 31%);
}
.bluBtn{
  background-color: hsl(225, 21%, 49%);
  color: white;
  border-bottom: 4px solid hsl(224, 28%, 35%);
}
.redBtn{
  background-color: hsl(6, 63%, 50%);
  color: white;
  border-bottom: 4px solid  hsl(6, 70%, 34%);
}
</style>