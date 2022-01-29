<template>
  <div class="content">
    <Page/>
    <div class="table-main-env">
      <table class = "table-main" id = "main_table">
        <thead>
        <tr>
          <th>Введите значения или нажмите на рисунок</th>
          <th>Таблица попаданий в область</th>
        </tr>
        </thead>
        <tbody>
        <tr>
          <td class = "table-main-section_input">
            <div class="div-field">
              <div id="graph">
                <svg id="graph-svg" width="360" height="360" xmlns="http://www.w3.org/2000/svg" @click="graphClick">
                  <rect id="graph-border" width="360" height="360" stroke="indianred" stroke-width="10px" x="0" y="0" fill="deepskyblue" fill-opacity="0.2" stroke-linejoin="round"></rect>
                  <line stroke="black" stroke-width="2px" x1="180" x2="180" y1="0" y2="360"></line>
                  <line stroke="black" stroke-width="2px" x1="0" x2="360" y1="180" y2="180"></line>
                  <rect id="section-1" x="105" y="182" width="75" height="150" fill-opacity="0.7"></rect>
                  <path id="section-2" d="M178,178 L107,178 A100,100 0 0,1 178,105 z"
                        fill-opacity="0.7"></path>
                  <polygon id="section-3" points="182 182, 182 257, 257 182" fill-opacity="0.7"></polygon>
                  <polygon class="graph-base" points="180 0, 185 25, 175 25" stroke="white" stroke-width="1"></polygon>
                  <polygon class="graph-base" points="360 180, 340 185, 340 175" stroke="white" stroke-width="1"></polygon>
                  <line stroke="white" stroke-width="2" x1="173" x2="187" y1="30"
                        y2="30"></line>
                  <line stroke="white" stroke-width="2" x1="173" x2="187" y1="105"
                        y2="105"></line>
                  <line stroke="white" stroke-width="2" x1="173" x2="187" y1="255"
                        y2="255"></line>
                  <line stroke="white" stroke-width="2" x1="173" x2="187" y1="331"
                        y2="331"></line>
                  <line stroke="white" stroke-width="2" x1="30" x2="30" y1="173" y2="187"></line>
                  <line stroke="white" stroke-width="2" x1="105" x2="105" y1="173"
                        y2="187"></line>
                  <line stroke="white" stroke-width="2" x1="255" x2="255" y1="173"
                        y2="187"></line>
                  <line stroke="white" stroke-width="2" x1="330" x2="330" y1="173"
                        y2="187"></line>
                  <text fill="indianred" stroke="indianred" x="193" y="35">R</text>
                  <text fill="indianred" stroke="indianred" x="193" y="110">R/2</text>
                  <text fill="indianred" stroke="indianred" x="193" y="260">-R/2</text>
                  <text fill="indianred" stroke="indianred" x="193" y="335">-R</text>
                  <text fill="indianred" stroke="indianred" x="325" y="167">R</text>
                  <text fill="indianred" stroke="indianred" x="245" y="167">R/2</text>
                  <text fill="indianred" stroke="indianred" x="100" y="167">-R/2</text>
                  <text fill="indianred" stroke="indianred" x="20" y="167">-R</text>
                </svg>
              </div>
            </div>
            <br/>
            <form id="input-form">
              <div class="div-field">
                <fieldset class="input-X">
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="-5">
                    -5
                  </label>
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="-4" >
                    -4
                  </label>
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="-3" >
                    -3
                  </label>
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="-2" >
                    -2
                  </label>
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="-1" >
                    -1
                  </label>
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="0" >
                    0
                  </label>
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="1" >
                    1
                  </label>
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="2" >
                    2
                  </label>
                  <label>
                    <input name = "xCheckbox" class="defaultBox" v-model="param_x" type="radio" value="3" >
                    3
                  </label>
                </fieldset>
              </div>
              <div class="div-field">
                <fieldset class="input-Y">
                  <label for="inputY">Выберите Y, допустимые значения от -5 до 5</label>
                  <input type="text" class="text-input" id="inputY" name="y" v-model="param_y" maxlength="17" autocomplete="off" placeholder="Введите число: (-5; 5)">
                </fieldset>
              </div>
              <div class="div-field">
                <fieldset class="input-R">
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="-5" >
                    -5
                  </label>
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="-4" >
                    -4
                  </label>
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="-3" >
                    -3
                  </label>
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="-2" >
                    -2
                  </label>
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="-1" >
                    -1
                  </label>
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="0" >
                    0
                  </label>
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="1" >
                    1
                  </label>
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="2" >
                    2
                  </label>
                  <label>
                    <input  name="rCheckbox" v-model="param_r" type="radio" value="3" >
                    3
                  </label>
                </fieldset>
              </div>
              <div class="div-field">
                <fieldset class="set">
                  <button class="set-button" id = "submit" @click="submit">
                    Проверить
                  </button>
                </fieldset>
              </div>
              <div class="div-field">
                <fieldset class="set">
                  <button class="set-button" id = "clear" @click="clearAll" >
                    Очистить
                  </button>
                </fieldset>
              </div>
              <div class="div-field">
                <fieldset class="set">
                  <button class="set-button" id = "logout" @click="logout">
                    Выйти
                  </button>
                </fieldset>
              </div>
            </form>
          </td>

          <td class = "table-main-section_output">
            <table id = "resultTable" class="result-table">
              <thead>
              <tr>
                <th>X</th>
                <th>Y</th>
                <th>R</th>
                <th>Result</th>
              </tr>
              </thead>
              <tbody id = "resultTBody">
              </tbody>
            </table>
          </td>

        </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import Page from "@/components/Page";
import $ from 'jquery';

export default {
  name: "Main",
  components: {
    Page,
  },
  data(){
    return{
      param_x: [-5],
      param_y: " ",
      param_r: [1]
    }
  },
  watch:{
    param_r(val){
      if (val.length > 0 && !isNaN(val[0]) && parseFloat(val[0]) > 0 && parseFloat(val[0]) <= 3){
        this.changeDots(val);
      }
    }
  },
  methods: {
    submit(e) {
      if (this.checkR(this.param_r) && this.checkX(this.param_x) && this.checkY(this.param_y) && this.param_y !== " ") {
        this.submitForm(e, this.param_x[0], this.param_y, this.param_r[0]);
      }
    },
    changeDots(r){
      if (r == null && !this.checkR(r)){
        return;
      }
      let pointers = $(".pointer");
      let initX;
      let initY;
      let moveX;
      let moveY;
      let initR;
      let hit;
      for (let i = 0; i < pointers.length; i++) {
        initX = pointers[i].dataset.x;
        initY = pointers[i].dataset.y;
        initR = pointers[i].dataset.r;
        hit = pointers[i].dataset.hit;
        moveX = 180 + 150 * initX / Math.abs(r);
        moveY = 180 - 150 * initY / Math.abs(r);
        if (initR === r && hit === "true") {
          pointers[i].style.fill = "#A4CC84";
        } else pointers[i].style.fill = "#cca484";
        $(pointers[i]).animate({
          cx: moveX,
          cy: moveY
        }, {duration: 500, queue: false});
      }
    },

    graphClick(event) {
      const GRAPH_WIDTH = 360;
      const INDENT = 30;
      console.log("graph-click");
      if (this.param_r == null || !this.checkR(this.param_r)) {
        return;
      }
      let x = (event.offsetX - GRAPH_WIDTH / 2) / (GRAPH_WIDTH / 2 - INDENT) * this.param_r;
      let y = (GRAPH_WIDTH / 2 - event.offsetY) / (GRAPH_WIDTH / 2 - INDENT) * this.param_r;
      x = Math.round(x*100) / 100;
      y = Math.round(y*100) / 100;
      this.submitForm(event, x,y,this.param_r);
    },


    drawResult(x, y, r) {
      const GRAPH_WIDTH = 360;
      const INDENT = 30;
      let svgns = "http://www.w3.org/2000/svg"
      let graph = document.getElementById("graph-svg");
      let circle = document.createElementNS(svgns, 'circle');
      circle.setAttributeNS(null, 'cx', GRAPH_WIDTH / 2 + (GRAPH_WIDTH / 2 - INDENT) * x / Math.abs(r));
      circle.setAttributeNS(null, 'cy', GRAPH_WIDTH / 2 - (GRAPH_WIDTH / 2 - INDENT) * y / Math.abs(r));
      circle.setAttributeNS(null, 'r', 5);
      circle.setAttribute('data-x', x);
      circle.setAttribute('data-y', y);
      circle.classList.add("pointer");
      if (this.calculateHit(x, y, r))
        circle.style.fill = "#a4cc84";
      graph.appendChild(circle);
    },

    checkX(x){
      return  (x.length > 0 && !isNaN(x[0]) && parseFloat(x[0]) >= -5 && parseFloat(x[0]) <= 3)
    },
    checkY(y){
      if (!isNaN(y) && parseFloat(y) > -5 && parseFloat(y) < 5 && y !== "" && y !== null){
        return true;
      } else {
        alert("Выберите Y в правильном диапазоне");
        return false;
      }
    },
    checkR(r){
      if (r > 0 && r <= 3){
        return true;
      } else {
        alert("Выберите R в правильном диапазоне");
        return false;
      }
    },
    submitForm(event, X, Y , R) {
      event.preventDefault();
      const userDetails = localStorage.getItem("jwt");
      if (userDetails) {
        this.axios.post("http://localhost:8082/main/add", {
              x: X,
              y: Y,
              r: R
            },
            {
              headers: {"Authorization": "Bearer " + userDetails}
            }).then(() => {
          this.getPoints();
        }).catch(error => {
          if (error.response.status === 401 || error.response.status === 403) {
            this.invalidateTokenAndGoToAuthPage();
          }
        })
      } else this.invalidateTokenAndGoToAuthPage();
    },
    invalidateTokenAndGoToAuthPage() {
      localStorage.removeItem("jwt");
      this.$router.push({name: "auth"});
    },
    getPoints() {
      this.axios.get("http://localhost:8082/main/get", {
        headers: {"Authorization": "Bearer " + localStorage.getItem('jwt')}
      }).then(response => {
        if (response.data.length > 0) {
          $("#resultTBody").html("");
          $(".pointer").remove();
          response.data.forEach(e => {
            let tr = '<tr><td>' +  Math.round(e.x * 1000) / 1000 + '</td><td>' + Math.round(e.y * 1000) / 1000 + '</td><td>' + e.r +'</td><td>' + e.hit + '</td></tr>';
            $("#resultTBody").append(tr);
            this.drawAll();
          });
        }
      }).catch(error => {
        alert(error.message);
        if (error.response.status === 401 || error.response.status === 403) {
          this.invalidateTokenAndGoToAuthPage();
        }
      })
    },

    drawAll() {
      this.param_r = 1;
      let data = Array();
      $(".result-table tr").each(function (i) {
        data[i] = Array();
        $(this).children('td').each(function (ii) {
          data[i][ii] = $(this).text();
        });
      })
      for (let i = 1; i < data.length; i++) {
        if (data[i][0])
          this.drawResult(data[i][0], data[i][1], this.param_r);
      }
    },

    calculateHit(x, y, r) {
      return this.calculateSectionOne(x, y, r) || this.calculateSectionTwo(x, y, r) || this.calculateSectionThree(x, y, r);
    },

    calculateSectionOne(x, y, r) {
      return x >= 0 && y <= 0 && y >= x - r/2
    },
    calculateSectionTwo(x, y, r) {
      return x <= 0 && y >= 0 && Math.sqrt(Math.pow(x, 2) + Math.pow(y, 2)) <= r / 2;
    },
    calculateSectionThree(x, y, r) {
      return x <= 0 && y <= 0 && Math.abs(x) <= r/2  && Math.abs(y) <= r;
    },

    clearAll(){
      const userDetails = localStorage.getItem("jwt");
      if (userDetails) {
        this.axios.delete("http://localhost:8082/main/clear",
            {
              headers: {"Authorization": "Bearer " + userDetails}
            }).then(() => {
          this.getPoints();
        }).catch(error => {
          if (error.response.status === 401 || error.response.status === 403) {
            this.invalidateTokenAndGoToAuthPage();
          }
        })
      } else this.invalidateTokenAndGoToAuthPage();
    },

    logout(event) {
      event.preventDefault();
      localStorage.removeItem("jwt");
      this.$router.push( "auth");
    },
  },
  mounted() {
    if (localStorage.getItem("jwt") == null) {
      this.$router.push("auth");
    }else{
      this.getPoints();}
  }
}
</script>
