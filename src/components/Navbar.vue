<template>
  <div class="navbar">
      <div class="container header">
          <h3>Where in the world?</h3>
          <div class="switch">
              <span>Dark Mode</span>
          </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .navbar {
        background-color: hsl(209, 23%, 22%);
        color: #fff;
    }
    .container {
        padding: 10px 10px;
        /* background-color: #f3f3f3; */
    }
    .header {
        display: flex;
        justify-content: space-between;
    }
    .header h3 {
        font-size: 21px;
        font-family: 'Nunito Sans', sans-serif;
        font-weight: 800;
    }
    .header span {
        font-size: 17px;
        font-family: 'Nunito Sans', sans-serif;
    }
</style>