<template>
  <div class="clock">
    <div class="hour">
      <div class="hr" id="hr"></div>
    </div>
    <div class="min">
      <div class="mn" id="mn"></div>
    </div>
    <script type="application/javascript">
      const deg = 6;
      const hr = document.querySelector('#hr');
      const mn = document.querySelector('#mn');
      let date, hh, mm, ss;
      function initParam() {
        date = new Date();
        hh = date.getHours();
        mm = date.getMinutes();
        ss = date.getSeconds();
      }
      function updateTime() {
        hr.style.transform = `rotateZ(${(hh*30)+(mm*deg/12)}deg)`;
        mn.style.transform = `rotateZ(${mm*deg}deg)`;

        hh = hh < 10 ? "0" + hh : hh;
        mm = mm < 10 ? "0" + mm : mm;
        ss = ss < 10 ? "0" + ss : ss;
      }
      initParam();
      updateTime();
      setInterval(() => {
        initParam();
        updateTime();
      }, 6000);
    </script>
  </div>
</template>

<script>
export default {
  name: "Clock"
}
</script>
