<script>
import "/node_modules/flag-icons/css/flag-icons.min.css";

export default {
    props: {
        mySerie: Object
    },
    methods: {
        getFlagCode(language) {
            switch (language) {
                case 'en':
                    return 'gb'; // per la Gran Bretagna
                case 'us':
                    return 'us'; // per gli Stati Uniti
                default:
                    return language; // per tutte le altre lingue
            }
        }
    }
}
</script>

<template>
    <div class="flip-card">
        <div class="flip-card-inner" :class="{ 'prevent-rotate': !mySerie.poster_path }">
            <div class="flip-card-front">
                <img v-if="mySerie.poster_path" :src="`https://image.tmdb.org/t/p/w342/${mySerie.poster_path}`" class="serie-poster">
                <div v-else class="fallback-cover text-white">Cover non disponibile</div>
            </div>
            <div class="flip-card-back mt-5" :class="{ 'fallback-cover-back': !mySerie.poster_path }">
                <ul>
                    <li>Titolo Serie:<br> <strong>{{ mySerie.name }}</strong></li>
                    <li class="mt-2">Titolo Originale:<br> <strong>{{ mySerie.original_name }}</strong></li>
                    <li class="mt-2">Lingua: 
                        <span :class="`fi fi-${getFlagCode(mySerie.original_language)}`"></span>
                    </li>
                    <li class="mt-2">Voto: <strong>{{parseInt(Math.round(mySerie.vote_average / 2))}}</strong></li>
                </ul>
            </div>
        </div>
    </div>
</template>

<style scoped>

.flip-card {
    background-color: transparent;
    perspective: 1000px;
    margin-bottom: 650px;
    filter: drop-shadow(0 0 20px rgba(0,0,255,0.5));
}

.flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
}

.flip-card-back {
    background-color: #000; 
    color: white;
    transform: rotateY(180deg);
    font-size: 17px;
}

.flip-card:hover .flip-card-front img {
    filter: brightness(0%);
}

.flip-card-back ul {
    list-style-type: none; 
    padding: 0; 
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center; 
    height: 100%; 
    padding-top: 20%; 
    width: 300px; 
    overflow-wrap: break-word;
    margin: auto;
}

.fallback-cover {
    color: red;
    font-size: 20px;
    padding-bottom: 50px;
    padding-top: 50px;
    background-color: rgb(255, 66, 66);
}

.flip-card:hover .fallback-cover {
    opacity: 0;
}

.flip-card:hover .flip-card-back img{
    filter: brightness(0%);
    padding: 50px;
    background-color: red;
}

.fallback-cover-back {
    color: white;
    font-size: 18px;
    padding-bottom: 350px;
    background-color: rgb(255, 66, 66);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

</style>
