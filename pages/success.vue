<script lang="ts" setup>
import { useCartStore } from "../stores/cart-store";
const store = useCartStore();
const cartItems: Ref<number[]> = ref([]);
//@ts-ignore
cartItems.value.push(...store.cart);

onMounted(() => {
  store.cart = [];
  setTimeout(() => {
    navigateTo("/");
  }, 4000);
});
</script>

<template>
  <div class="h-screen w-screen flex justify-center">
    <span class="mt-20"
      >Your order was succesfully placed, you will be redirected to the home
      page..</span
    >
  </div>
</template>
