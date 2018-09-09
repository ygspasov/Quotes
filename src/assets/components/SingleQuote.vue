<template>
  <div class="col-sm-6 sol-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>  
</template>

<script>
export default {};
</script>

<style>
.panel-body {
  font-family: 'Gamja Flower', cursive;
  font-size: 24px;
  color: #6e6e6e;
}

.quote {
  cursor: pointer;
}
.quote:hover {
  background: #DFF0D8;
  transition: background 1s;
}
</style>
