<template>
  <header class="main-header">
    <div class="content">
      <h1>Timeline</h1>
      <div>
        <nav>{{description}}</nav>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  props: ['name', 'description']
}
</script>

<style scoped>
  .main-header {
    height: 150px;
    background: #4267b2;
    position: relative;
    z-index: 1;
  }

  .main-header .content {
    display: flex;
    flex-direction: column;
    align-items: left;
    justify-content: center;
    height: 100%;
  }

  .main-header .content h1 {
    color: #ffffff;
    font-size: 40px;
  }

  .main-header .content nav {
    color: lightgrey;
    font-size: 12px;
    font-style: italic;
  }
</style>
