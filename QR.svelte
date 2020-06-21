<script>
  import {onMount, afterUpdate} from 'svelte'
  import kjua from 'kjua'

  export let value = ''
  export let color = '#333'
  export let size = 300

  let id = parseInt(Math.random() * 100000)
  var container
  var qr

  onMount(() => {
    container = document.getElementById('c-' + id)

    qr = makeQR()
    container.appendChild(qr)
  })

  afterUpdate(() => {
    container.removeChild(qr)
    qr = makeQR()
    container.appendChild(qr)
  })

  function makeQR() {
    return kjua({
      rounded: 100,
      text: value.toUpperCase(),
      fill: color,
      back: 'transparent',
      size
    })
  }
</script>

<style>
div { text-align: center; }
</style>

<div id="c-{id}"></div>

