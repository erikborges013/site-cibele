<template>
  <a class="ancora-whatsapp" href="https://wa.me/+5513981799604">
    <img
      class="icone-whatsapp"
      src="@/assets/icone-whatsapp.png"
      alt="icone-do-whatsapp"
    />
  </a>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BotaoWhatsapp",
});
</script>

<style scoped>
.icone-whatsapp {
  position: fixed;
  width: 4rem;
  bottom: 0;
  right: 0;
}
</style>
