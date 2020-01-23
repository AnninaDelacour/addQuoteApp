<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Quote",
  props: ["quotes"]
};
</script>

<style lang="scss" scoped>
.panel-body {
  font-family: "Indie Flower", cursive;
  font-size: 20px;
  color: #403f3f;
  border-radius: 5px;
}

.quote {
  color: #ffffff;
  background: #007065;
  transition: 0.2s linear;
  padding: 1rem;
  cursor: pointer;
  margin: 0.5rem;
}
</style>
