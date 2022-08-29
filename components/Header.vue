<template>
  <div>
    <NuxtLink to="/"> Main</NuxtLink>
    <NuxtLink to="/contacts">Contacts </NuxtLink>
    <NuxtLink to="/delivery"> Delivery</NuxtLink>
    <NuxtLink to="/promotions"> Promotions </NuxtLink>
  </div>
</template>

<script>
export default {
  mounted(){
    console.log(this.$route);
  }
};
</script>

