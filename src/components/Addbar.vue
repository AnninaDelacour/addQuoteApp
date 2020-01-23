<template>
  <div class="row">
    <div class="col-12">
      
        <div class="progress">
          <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="50"
          :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
            {{ quoteCount }} / {{ maxQuotes }}
          </div>
        </div>
      
    </div>
  </div>
</template>

<script>
export default {
  name: "Addbar",
  props: ['quoteCount', 'maxQuotes']
};
</script>

<style lang="scss" scoped>
</style>
