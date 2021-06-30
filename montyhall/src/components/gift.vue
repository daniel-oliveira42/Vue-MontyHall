<template>
  <div class="gift">
      <div class="lasso"></div>
      <div class="gift">
        <div class="tie-1"></div>
        <div class="lid"></div>
        <div class="bottom"></div>
      </div>
  </div>
</template>

<script>

export default {
    name: 'Gift',

}
</script>

<style>
.gift {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 10;
}


.lid {
    width: 100px;
    height: 25px;
    background-color: aquamarine;
}

.bottom {
    width: 90px;
    height: 60px;
    background-color: blueviolet;
}

.tie-1 {
    position: absolute;
    width: 15px;
    height: 100%;
    background-color: red;
}

.lasso {
    width: 18px;
    height: 18px;
    border-radius: 50px;
    background-color: red;
}
</style>