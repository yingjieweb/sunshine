<template>
  <div class="naruto-eyes">
    <!-- 血轮眼 -->
    <div class="blood">
      <!-- 眼睛最中间那个黑点 -->
      <div class="bloodZong">
        <!-- 三勾玉所在的圈 -->
        <div class="bloodYu">
          <!-- 三个勾玉 -->
          <span class="yu"></span>
          <span class="yu"></span>
          <span class="yu"></span>
        </div>
      </div>
    </div>

    <!-- 轮回眼 -->
    <div class="cycle">
      <!-- 眼睛最中间那个黑点 -->
      <div class="dian"></div>
      <!-- 3个轮回圈 -->
      <div class="cycleYu">
        <span class="quan" style="--r:2;"></span>
        <span class="quan" style="--r:3;"></span>
        <span class="quan" style="--r:4;"></span>
      </div>
    </div>
  </div>
</template>

<script lang="js">
export default {
  name: "NarutoEyes"
}
</script>

<style lang="scss" scoped>
.naruto-eyes {
  width: 100%;
  height: 100%;
  background-color: #091921;
  display: flex;
  align-items: center;
  justify-content: center;
}
.blood,
.cycle {
  width: 250px;
  height: 120px;
  background-color: rgb(255, 255, 255);
  border-bottom: 5px solid rgb(70, 70, 70);
  overflow: hidden;
  position: relative;
  cursor: pointer;
}

/*Blood round eye styles*/
.blood {
  transform: translateX(-50px);
  border-radius: 0 120px 0 120px;
  box-shadow: inset 3px 2px 3px rgba(17, 17, 17, 0.8);
}

.blood::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 95px;
  height: 95px;
  border-radius: 50%;
  border: 2px solid #000;
  animation: colour 2s linear forwards;
}
@keyframes colour {
  0%,
  30% {
    background-color: rgb(0, 0, 0);
  }
  100% {
    background-color: rgb(255, 4, 4);
  }
}

.bloodZong {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 0px;
  height: 0px;
  border-radius: 50%;
  background-color: rgb(0, 0, 0);
  z-index: 1;
  animation: da 3s linear forwards;
}
@keyframes da {
  100% {
    width: 15px;
    height: 15px;
  }
}

.bloodYu {
  position: absolute;
  top: -25px;
  left: -25px;
  bottom: -25px;
  right: -25px;
  border-radius: 50%;
  border: 2px solid rgb(0, 0, 0);
  animation: zhuan 2s linear 2s forwards;
  opacity: 0;
}
@keyframes zhuan {
  100% {
    opacity: 1;
    transform: rotate(720deg);
  }
}

.bloodYu .yu {
  position: absolute;
  width: 15px;
  height: 15px;
  border-radius: 50%;
  background-color: rgb(0, 0, 0);
}
.bloodYu .yu::after {
  content: "";
  position: absolute;
  top: -6px;
  left: -1px;
  width: 6px;
  height: 20px;
  border-radius: 50%;
  border-left: 6px solid rgb(0, 0, 0);
}
.bloodYu .yu:nth-child(1) {
  animation: yu1 2s ease-in 2s forwards;
}
@keyframes yu1 {
  0% {
    opacity: 0;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%) scale(0.1);
  }
  100% {
    left: 50%;
    top: -9%;
    transform: scale(1) rotate(80deg);
  }
}

.bloodYu .yu:nth-child(2) {
  animation: yu2 2s ease-in 2s forwards;
}
@keyframes yu2 {
  0% {
    opacity: 0;
    left: 50%;
    top: 50%;

    transform: translate(-50%, -50%) scale(0.1);
  }
  100% {
    top: 60%;
    left: -9%;
    transform: scale(1) rotate(-60deg);
  }
}

.bloodYu .yu:nth-child(3) {
  animation: yu3 2s ease-in 2s forwards;
}
@keyframes yu3 {
  0% {
    opacity: 0;
    right: 50%;
    top: 50%;

    transform: translate(-50%, -50%) scale(0.1);
  }
  100% {
    top: 60%;
    right: -9%;
    transform: scale(1) rotate(180deg);
  }
}

.blood::before,
.cycle::before {
  content: "";
  position: absolute;
  left: 38%;
  top: 30%;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: rgb(255, 255, 255);
  z-index: 10;
}

/*Cycle of the eye styles*/
.cycle {
  transform: translateX(50px);
  border-radius: 120px 0 120px 0;
  box-shadow: inset -3px 2px 3px rgba(17, 17, 17, 0.8);
}

.cycle::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 95px;
  height: 95px;
  border-radius: 50%;
  border: 2px solid #000;
  animation: cyclecolor 2s linear forwards;
}
@keyframes cyclecolor {
  0%,
  30% {
    background-color: rgb(0, 0, 0);
  }
  100% {
    background-color: rgb(144, 130, 183);
  }
}

.dian {
  position: absolute;
  top: 50%;
  left: 50%;
  background-color: #000;
  transform: translate(-50%, -50%);
  border-radius: 50%;
  z-index: 10;
  animation: cycleda 3s linear forwards;
}
@keyframes cycleda {
  0% {
    height: 0px;
    width: 0px;
  }
  100% {
    height: 15px;
    width: 15px;
  }
}

.cycleYu {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.quan {
  position: absolute;
  border-radius: 50%;
  border: 2px solid #000;
  z-index: calc(1 - var(--r));
  animation: zhi 2s ease-out 2s forwards;
}
@keyframes zhi {
  0% {
    top: calc(var(--r) * 1px);
    left: calc(var(--r) * 1px);
    right: calc(var(--r) * 1px);
    bottom: calc(var(--r) * 1px);
  }
  100% {
    top: calc(var(--r) * -35px);
    left: calc(var(--r) * -35px);
    right: calc(var(--r) * -35px);
    bottom: calc(var(--r) * -35px);

    background-color: rgb(187, 177, 214);
  }
}
</style>
