<script setup lang="ts">
const props = defineProps({
  title:{
    type: String,
    required: true
  },
  visible:{
    type: Boolean,
    required: true
  }

})
const closePanel = () => {
  emit('update:visible', false)

}
const emit = defineEmits(['update:visible'])
</script>

<template>
  <div class="panel-wrap" :class="{visible: visible}">
  <div class="panel">
    <div class="">
      <button class="btn error--outline" @click="closePanel">Fechar</button>
      <h2>{{ props.title }}</h2>
    </div>
  </div>
</div>

  <slot name="content"></slot>

</template>

<style lang="scss" scoped>
.panel {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  width: 100em;
  background-color: #333;
  color: #eee;
  overflow: auto;
  padding: 1em;

  &-wrap{
    position: fixed;
    top: 0;
    bottom: 0;
    left: 70em;
    right: 0;
    width: 30em;
    transform: translateX(100%);
    transition: 1s ease-out;
    &.visible {
      transform: translateX(0%);
    }
  }



}

</style>
