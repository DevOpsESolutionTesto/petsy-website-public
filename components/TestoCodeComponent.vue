<template>
  <div>
    <div :id="blok.divWrapId">
      <script>
        // eslint-disable-next-line no-unused-vars
        function cmscontent () {
          // eslint-disable-next-line
          {{blok.code.content[0].content[0].text}}
        }
      </script>
    </div>
  </div>
</template>

<script>
export default {
  props: ['blok'],
  mounted () {
    let Script = document.createElement('script')
    Script.setAttribute('src', this.blok.url)
    Script.defer = true
    Script.addEventListener('load', () => {
      // eslint-disable-next-line no-undef
      cmscontent()
    })
    document.head.appendChild(Script)
  }
}
</script>
