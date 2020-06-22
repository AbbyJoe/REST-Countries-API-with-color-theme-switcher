<template>
  <div>
      <div class="container mt-5 search__field" style="display:flex; justify-content:space-between">
        <div class="form-group has-search">
            <span class="fa fa-search form-control-feedback"></span>
            <input type="text" class="form-control" placeholder="Search">
        </div>
        <select name="filters" id="">
            <option value="">Ma</option>
            <option value="">gdg</option>
            <option value="">hh</option>
            <option value="">kdk</option>
            <option value="">jdj</option>
        </select>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
    body {
        font-family: 'Nunito Sans', sans-serif;
        background-color: hsl(207, 26%, 17%);
    }
    .has-search .form-control {
        padding-left: 2.375rem;
    }
.has-search .form-control-feedback {
    position: absolute;
    z-index: 2;
    display: block;
    width: 2.375rem;
    height: 2.375rem;
    line-height: 2.375rem;
    text-align: center;
    pointer-events: none;
    color: #aaa;
}
</style>