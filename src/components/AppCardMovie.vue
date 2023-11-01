<script>

export default {
    props: {
        myMovie: Object
    },
}

</script>

<template lang="">

    <div class="flip-card">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img :src="`https://image.tmdb.org/t/p/w342/${myMovie.poster_path}`">
            </div>
            <div class="flip-card-back mt-5">
                <ul>
                    <li>Titolo Film:<br> <strong>{{ myMovie.title }}</strong></li>
                    <li class="mt-2">Titolo Originale:<br> <strong>{{ myMovie.original_title }}</strong></li>
                    <li class="mt-2">Lingua: <strong>{{ myMovie.original_language }}</strong></li>
                    <li class="mt-2">Voto: <strong>{{parseInt(Math.round(myMovie.vote_average / 2))}}</strong></li>
                </ul>
            </div>
        </div>
    </div>

</template>

<style scoped>
.flip-card {
    background-color: transparent;
    perspective: 1000px;
    margin-bottom: 650px; /* Aggiungi margini attorno alla card */
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
.flip-card {
    filter: drop-shadow(0 0 20px rgba(0,0,255,0.5)); /* Aggiunge un bordo sfocato blu */
}
</style>