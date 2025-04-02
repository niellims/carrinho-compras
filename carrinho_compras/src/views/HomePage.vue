<script setup lang="ts">
import SlidePanel from '@/components/modules/shared/SlidePanel.vue';
import { ref } from 'vue';

const cartVisible = ref(false);

const changeCartVisibility = () => {
  cartVisible.value = !cartVisible.value;
  console.log(cartVisible.value)
}


</script>

<template>
  <main>
    <h1>Shopping</h1>

    <button class="btn sucess"> Adicionar ao Carrinho</button>
    <button class="btn error ml-1"> Limpar Carrinho</button>
    <button class="btn error ml-1" @click="changeCartVisibility">
      Abrir carrinho
    </button>
    <SlidePanel
    title="Cart"
    :visible="cartVisible"
    @update:visible="changeCartVisibility"
    v-if="cartVisible"
    >

    </SlidePanel>
  </main>
</template>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
.btn {
  padding: 10px;
  border-radius: 5px;

  font-family: "Poppins", sans-serif;
  font-weight: 700;
  font-style: normal;

  &.primary{
    background-color: #98fff6;
    color: #fff;
    &:hover{
      background-color: #fff;
      color: #000;
    }
  }
  &.sucess{
    background-color: #77ff77;
    color: #000;
    &:hover{
      background-color: #8ef98e;
      color: #000;
    }
  }
  &.error {
    background-color: #ff7777;
    color: #fff;
    &:hover{
      background-color: #fa9b9b;
      color: #000;
    }
    &--outline{
      background-color: transparent;
      color: #ff7777;

      &:hover {
        background-color: #ff7777;
        border: 1px solid #ff7777 ;
        color: #fff;
      }
    }
  }
}

.ml-1 {
  margin-left: 1rem;
}
</style>

