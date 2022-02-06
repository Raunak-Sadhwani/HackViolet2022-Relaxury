<template>
  <div class="main">
    <locFilterComponent what="Drop By" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      poll: 'LMAOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOO',

      dropby: [
        {
          company: 'chai wale',
          dropbytype: 'cafe',
          detail: ' chai peelo friends ',
          area: 'lohegaon',
          rating: 3.5,
          time: '12:00',
        },
        {
          company: 'kirana',
          dropbytype: 'shop',
          detail: ' stationary ',
          area: 'lohegaon',

        },
        {
          company: 'free massage wala',
          dropbytype: 'spa',
          detail: ' malamal massage ',
          location: 'bangcock',
          area: 'thai',
          rating: '5.5',
        },
      ],
    }
  },
}
</script>

<style>
</style>