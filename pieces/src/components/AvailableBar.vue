<template>
    <div class="availableBar">
        <span class="title" :style="{color: unitColor}">{{ $t(barTitle) }}</span>
        <span class="counter" :style="{color: unitColor}">{{props.valMin}}/{{props.valMax}}</span>
    </div>
</template>

<script setup lang="ts" name="AvailableBar">
let props = defineProps(['unitType','barTitle','valMin','valMax'])

//determine the title
let barTitle = props.barTitle

//determine the color
let unitType = props.unitType
let unitColor:string
if (unitType == 'support'){
  unitColor = '#5AFF75'
} else if (unitType == 'working'){
  unitColor = '#5667FF'
}else{
  unitColor = '#FF4949'
}
</script>

<style scoped>
.availableBar{
    position: relative;
    width: 275px;
    height: 45px;
    border: #2e2e2e 1px solid;
    border-radius: 15px;
}
.counter {
  position: absolute;
  left: 220px;
  top: 0px;
  width: 68.75px;
  height: 45px;
  font-family: Inter;
  font-size: 24px;
  font-weight: 400;
  text-align: center;
  display: flex;
  align-items: center;
}
.title {
  position: absolute;
  left: 14.52px;
  top: 10.53px;
  width: 188px;
  height: 24.2px;
  color: #2e2e2e;
  font-family: Inter;
  font-size: 20px;
  font-weight: 400;
  line-height: 24.2px;
}

</style>