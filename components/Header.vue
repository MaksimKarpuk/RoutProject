<template>
  <div :class="$style.links">
    <NuxtLink to="/"> <Main /> </NuxtLink>
    <NuxtLink to="/contacts"> <Contacts /> </NuxtLink>
    <NuxtLink to="/delivery"> <Delivery /> </NuxtLink>
    <NuxtLink to="/promotions"> <Promotions /> </NuxtLink>
  </div>
</template>

<script>
import Delivery from "../components/Delivery";
import Contacts from "../components/Contacts";
import Main from "../components/Main";
import Promotions from "../components/Promotions";
export default {
  components: {
    Main,
    Delivery,
    Promotions,
    Contacts,
  },
};
</script>

