<template>
    <div class="card">
        <div class="flip-card">
            <div class="flip-card-inner">
                <div class="flip-card-front">
                    <img :src="imgUrl" alt="">
                    <h2>{{ name }}</h2>
                    <p>{{ archetype }}</p>
                </div>
                <div class="flip-card-back">
                    <h2>{{ type }}</h2>
                    <h2>{{ race }}</h2>
                    <p>price:</p>
                    <h3>Card Market: {{ price[0].cardmarket_price }} &euro;</h3>
                    <h3>TCG Player: {{ price[0].tcgplayer_price }} &euro;</h3>
                    <h3>Ebay: {{ price[0].ebay_price }} &euro;</h3>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        imgUrl: String,
        name: String,
        archetype: String,
        type: String,
        race: String,
        effect: String,
        price: Array
    }
}
</script>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.card {
    width: 421px;
    margin-bottom: 20px;
    padding-bottom: 2rem;

    .flip-card {
        background-color: transparent;
        width: 421px;
        height: 808px;
        perspective: 1450px;
    }

    .flip-card-inner {
        position: relative;
        width: 100%;
        height: 100%;
        text-align: center;
        transition: transform 0.8s;
        transform-style: preserve-3d;
    }

    .flip-card:hover .flip-card-inner {
        transform: rotateY(180deg);
    }

    .flip-card-front,
    .flip-card-back {
        position: absolute;
        width: 100%;
        height: 100%;
        -webkit-backface-visibility: hidden;
        backface-visibility: hidden;
    }

    .flip-card-front {
        background-color: $main-color;
        color: black;
    }

    .flip-card-back {
        background-color: $main-color;
        color: white;
        transform: rotateY(180deg);

        p{
            margin: 7rem 0 1rem;
        }

        h3{
            text-align: left;
            margin: 5px 20px;
            font-size: 1.6rem;
        }
    }

    h2 {
        color: white;
        text-align: center;
        text-transform: uppercase;
        padding: 2rem 0;
    }

    p {
        font-size: 2rem;
        text-align: center;
    }
}
</style>