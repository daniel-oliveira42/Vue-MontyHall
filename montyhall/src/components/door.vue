<template>
  <div id="door">
    <div class="doorFrame" :class ="{selected: selected && !open}">
      <Gift v-if="open && hasGift" />
    </div>
    <div class="doorBody" :class= "{open}"
    @click="selected = !selected">
      <div class="number">{{ number }}</div>
      <div class="knob" @click.stop= "open = true"></div>
      <div class="selectedText" :class ="{selected: selected && !open}">Selected</div>
    </div>
  </div>
</template>

<script>
import Gift from "./gift.vue";

export default {
  name: "Door",
  components: { Gift },
  props: {
    number: {},
    hasGift: { type: Boolean },
  },
  data: function () {
    return {
      open: false,
      selected: false,
    };
  },
};
</script>

<style>
#door {
  position: relative;
  width: 200px;
  height: 310px;
  border-bottom: 10px solid #aaa;
  margin-bottom: 20px;
  font-size: 3rem;

  display: flex;
  justify-content: center;
}

.doorFrame {
  position: absolute;
  height: 300px;
  width: 180px;

  border-left: 5px solid saddlebrown;
  border-top: 5px solid saddlebrown;
  border-right: 5px solid saddlebrown;

  display: flex;
  justify-content: center;
  align-items: flex-end;
}

.doorBody {
  position: absolute;
  top: 5px;
  height: 295px;
  width: 170px;
  background-color: sienna;

  color: yellow;
  text-align: center;

  display: flex;
  flex-direction: column;
  padding: 20px;
}

.number {

}

.doorBody .knob {
    height: 18px;
    width: 18px;
    border-radius: 50px;
    background-color: yellow;
    align-self: flex-start;
    justify-self: center;
    margin-top: 50%;
}

.doorFrame.selected {
    border-left: 5px solid yellow;
    border-top: 5px solid yellow;
    border-right: 5px solid yellow;
}

.selectedText {
    display: none;
}

.selectedText.selected {
    display: inline;
    text-transform: uppercase;
    font-size: 20px;
    font-weight: bold;
    margin-top: 50%;
    color: white;
}

.doorBody.open {
    background-color: rgb(10, 3, 3);
}

.doorBody.open .knob {
    display: none;
}

.doorBody.open .number {
    display: none;
}

</style>