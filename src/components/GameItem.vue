<template>
  <div class="about">
      <li>{{ game.title}}</li>
  </div>
</template>

<script>
export default {
  name: 'GameItem',
  props: ['game'],
  data () {
    return {

    }
  }
}
</script>
