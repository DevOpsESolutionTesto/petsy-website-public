<template>
  <formio
      v-editable="blok"
      :src="blok.formsrc"
/>
</template>
<script>
export default {
  props: ['blok']
}
</script>
