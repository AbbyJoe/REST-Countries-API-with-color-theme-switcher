<template>
  <div>
      <div class="container-fluid mt-5 search__field" style="display:flex; justify-content:space-between">
        <div class="form-group has-search">
            <span class="fa fa-search form-control-feedback"></span>
            <input type="text" class="form-control" placeholder="Search">
        </div>
        <div class="select-box">
            <span @click="toggleShowOption()" :class="showOption ? 'open' : ''">
                {{regionFilter ? regionFilter : 'Filter by Region'}}
                <svg xmlns='http://www.w3.org/2000/svg' width='20' height='20' viewBox='0 0 512 512'>
                <title>ionicons-v5-a</title>
                <polyline points='112 184 256 328 400 184'
                    style='fill:none;stroke:#000;stroke-linecap:round;stroke-linejoin:round;stroke-width:48px' />
                </svg>
            </span>
            <ul class="option-box">
                <li @click="changeFilterOption(option)" v-for="(option,index) in options" :key="'filter__option'+index">{{option}}</li>
            </ul>
        </div>
      </div>

      <section>
          <div class="container-fluid">
              <div class="row">
                  <div class="col-lg-3" v-for="(object, key) in countries" :key="key">
                      <div class="card__panel">
                          <img :src="object.flag" class="img-fluid" alt="">
                          <div class="content">
                                <h6>{{object.name}}</h6>
                                <p>{{object.population}}</p>
                                <p>{{object.region}}</p>
                                <p>{{object.capital}}</p>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </section>
  </div>
</template>

<script>
import axios from 'axios'
export default {
     data() {
        return {
            countries: [],
            name: '',
            regionFilter: '',
            options: ['Africa', 'Americas', 'Asia', 'Europe', 'Oceania'],
            showOption: false
        }
    },
    methods: {
        toggleShowOption() {
            this.showOption = !this.showOption;
        },
        changeFilterOption(name) {
            this.regionFilter = name;
            this.showOption = false;
        }
    },
    mounted() {
        axios.get('https://restcountries.eu/rest/v2/all').then(res => this.countries = res.data )
        .catch(err => {
            console.log('oops', err)
        })
    }
}
</script>

<style>
    body {
        font-family: 'Nunito Sans', sans-serif;
        background-color: hsl(207, 26%, 17%);
    }
    .container-fluid {
    width: 93%;
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
.content {
    padding: 20px;
    background-color: hsl(209, 23%, 22%);
}   
    .content h6 {
        color: #fff;
    }
.content p {
    color: #fff
}


</style>