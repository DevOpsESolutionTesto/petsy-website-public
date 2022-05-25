<template>
  <div>
    <div :id="blok.divWrapId">
      <script>
        window.onload = function () {
          {{blok.code.content[0].content[0].text}}
        };
      </script>
    </div>
  </div>
</template>

<script>
export default {
  props: ["blok"],
  mounted() {
    let Script = document.createElement("script");
    Script.setAttribute("src", this.blok.url);
    Script.defer = true;
    document.head.appendChild(Script);
  },
};
</script>
