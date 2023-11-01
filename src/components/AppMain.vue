<script>

import axios from 'axios';
import { store } from '../store.js'
import AppCardMovie from './AppCardMovie.vue';
import AppCardTv from './AppCardTv.vue';

export default {
    components: {
        AppCardMovie,
        AppCardTv
    },
    data() {
        return {
            store,
            rotate: {}
    }
  },
  
}

</script>

<template lang="">

 <div class="container">
    <div class="row card_margin">
      <div v-for="(movie, index) in store.moviesList" v-bind:key="movie.id" class="col-6 col-md-4 mt-5 mb-2 text-center">
        <AppCardMovie v-bind:myMovie="movie" @mouseover.native="rotate[index] = true" @mouseout.native="rotate[index] = false" :class="{ 'rotate': rotate[index] }"/>
      </div>
      <div v-for="(serie, index) in store.tvSeriesList" v-bind:key="serie.id" class="col-6 col-md-4 mt-5 mb-2 text-center">
        <AppCardTv v-bind:mySerie="serie" @mouseover.native="rotate[index] = true" @mouseout.native="rotate[index] = false" :class="{ 'rotate': rotate[index] }"/>
      </div>
    </div>
  </div>

    <!--carosello slide-->
    <div class="container-fluid text-center carousel_slide"> 
        <h2 class="font-weight-light text-white">I Titoli del Momento</h2> 
            <div class="row mx-auto my-auto justify-content-center"> 
                <div id="recipeCarousel" class="carousel slide" data-bs-ride="carousel"> 
                    <div class="carousel-inner" role="listbox"> 
                        <div class="carousel-item active"> 
                            <div class="col-md-2"> 
                                <div class="card">   
                                    <div class="card-img"> 
                                        <img src="https://cdn.wallpapersafari.com/59/44/o2mLkf.jpg" class="img-fluid">
                                    </div> 
                                    <div class="card-img-overlay"> 
                                    </div> 
                                </div> 
                            </div> 
                        </div> 
                        <div class="carousel-item test2"> 
                            <div class="col-md-2"> 
                                <div class="card"> 
                                    <div class="card-img"> 
                                        <img src="https://cdn.prod.mktg.evvnt.com/uploads/event_image/1939168/event_image/hero_Leo.webp" class="img-fluid">
                                    </div> 
                                    <div class="card-img-overlay"></div> 
                                </div> 
                            </div> 
                        </div> 
                        <div class="carousel-item"> 
                            <div class="col-md-2"> 
                                <div class="card"> 
                                    <div class="card-img"> <img src="https://www.greaterfool.tv/test/wp-content/uploads/2022/10/film-hd-in-streaming.jpg" class="img-fluid"> </div> <div class="card-img-overlay"></div> 
                                </div> 
                            </div> 
                        </div> 
                        <div class="carousel-item"> 
                            <div class="col-md-2"> 
                                <div class="card"> 
                                    <div class="card-img"> <img src="https://i.ytimg.com/vi/1qIvQxLcyys/maxresdefault.jpg" class="img-fluid"> </div> 
                                    <div class="card-img-overlay"></div> 
                                </div> 
                            </div> 
                        </div> 
                        <div class="carousel-item"> 
                            <div class="col-md-2"> 
                                <div class="card"> 
                                    <div class="card-img"> <img src="https://cdn.wallpapersafari.com/86/83/c7nmps.jpg" class="img-fluid"> </div> <div class="card-img-overlay"></div> 
                                </div> 
                            </div> 
                        </div> 
                        <div class="carousel-item"> 
                            <div class="col-md-2"> 
                                <div class="card"> 
                                    <div class="card-img"> <img src="https://wallpapercave.com/wp/gssEep9.jpg" class="img-fluid"> </div> <div class="card-img-overlay">Slide 6</div> 
                                </div> 
                            </div> 
                        </div>
                        <div class="carousel-item"> 
                            <div class="col-md-2"> 
                                <div class="card"> 
                                    <div class="card-img"> <img src="https://img.wallscloud.net/uploads/thumb/2845750753/one-piece-rR9L-1024x576-MM-80.webp" class="img-fluid"> </div> <div class="card-img-overlay"></div> 
                                </div> 
                            </div> 
                        </div> 
                        <div class="carousel-item"> 
                            <div class="col-md-2"> 
                                <div class="card"> 
                                    <div class="card-img"> <img src="https://wallpapercave.com/wp/Bbd3fkG.jpg" class="img-fluid"> </div> <div class="card-img-overlay"></div> 
                                </div> 
                            </div> 
                        </div> 
                    </div> 
                    <a class="carousel-control-prev bg-transparent w-aut" href="#recipeCarousel" role="button" data-bs-slide="prev"> <span class="carousel-control-prev-icon" aria-hidden="true"></span> </a> 
                    <a class="carousel-control-next bg-transparent w-aut" href="#recipeCarousel" role="button" data-bs-slide="next"> <span class="carousel-control-next-icon" aria-hidden="true"></span> </a> 
                </div> 
            </div> 
    </div>

</template>

<style lang="scss">

@media (max-width: 767px){.carousel-inner .carousel-item >div{display: none}.carousel-inner .carousel-item >div:first-child{display: block}}.carousel-inner .carousel-item.active, .carousel-inner .carousel-item-next, .carousel-inner .carousel-item-prev{display: flex}@media (min-width: 768px){.carousel-inner .carousel-item-end.active, .carousel-inner .carousel-item-next{transform: translateX(25%)}.carousel-inner .carousel-item-start.active, .carousel-inner .carousel-item-prev{transform: translateX(-25%)}}.carousel-inner .carousel-item-end, .carousel-inner .carousel-item-start{transform: translateX(0)}

.carousel_slide{
    margin-bottom: 1rem !important;
    position: fixed;
    bottom: 0;
    width: 100%;
}

.card {
  transition: transform .2s; /* Animation */
}

.card:hover {
  transform: scale(1.2); /* (150% zoom - Note: if the zoom is too large, it will go outside of the viewport) */
}

.card_margin{
    margin-top: 6rem !important;
}

</style>