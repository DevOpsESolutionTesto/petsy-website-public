<template>
  <div>
    <div :id="blok.divWrapId">
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
    let ScriptCms = document.createElement('script')
    ScriptCms.text = 'function cmscontent(){' + this.blok.code.content[0].content[0].text + '}'

    document.head.appendChild(ScriptCms)
  }
}
</script>
