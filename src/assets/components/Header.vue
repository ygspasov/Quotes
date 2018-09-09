<template>
 <div class="row">
    
    <div class="col-sm-12">
      <h1>Number of quotes</h1>
      <div class="progress">
        <div class="progress-bar progress-bar-striped" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" :style="{width: (quoteCount/maxQuotes)*100 + '%'}">
          {{quoteCount}} / {{maxQuotes}}
        </div>
      </div>	
    </div>
 </div>
</template>

<script>
export default {
  props: ["quoteCount", "maxQuotes"]
};
</script>

<style scoped>
  .progress-bar{
    background: #5CB85C;
    font-size: 16px;
    line-height: 40px;
  }
  .progress {
    height: 40px;
  }
</style>


