<script>
  import {onMount} from 'svelte'
  import kjua from 'kjua'

  export let value = ''
  export let color = '#333'
  export let size = 300

  let id = parseInt(Math.random() * 100000)

  onMount(() => {
    let el = kjua({
      rounded: 100,
      text: value.toUpperCase(),
      fill: color,
      back: 'transparent',
      size
    })

    document.getElementById('c-' + id).appendChild(el)
  })
</script>

<div id="c-{id}"></div>

