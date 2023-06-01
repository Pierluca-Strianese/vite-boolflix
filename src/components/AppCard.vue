<script>
export default {
    name: "AppCard",
    props: {
        image: String,
        titleOriginal: String,
        titleTranslated: String,
        language: String,
        vote: Number
    }
}
</script>

<template>
    <div class="col mb-4">
        <div class="pg-card d-flex flex-column text-white position-relative overflow-hidden">

            <div class="container-img w-100">
                <img class="object-fit-fill w-100 h-100" :src="`https://image.tmdb.org/t/p/w500${image}`" alt="">
            </div>

            <div class="card-text position-absolute w-100 h-100 p-2">

                <div class="container-title">
                    <h3 class="fs-5 p-1">Titolo originale: {{ titleOriginal }}</h3>
                    <h4 class="fs-5 p-1">Titolo italiano: {{ titleTranslated }}</h4>
                </div>

                <div class="container-language">
                    <span>Lingua:</span>
                    <img :src="`flags/language-${language}.svg`" :alt="language">
                </div>

                <div class="container-votes">
                    <span>Media voti:</span>
                    <span v-for="star in vote" :key="star"><i class="fa-solid fa-star" style="color: goldenrod;"></i></span>
                </div>

            </div>


        </div>
    </div>
</template>


<style lang="scss" scoped>
@use '../style/general.scss' as *;

.pg-card {
    .container-img {
        transition: all .5s;
    }

    .card-text {
        top: 100%;
        transition: all .6s;
    }

    &:hover {
        cursor: pointer;

        .card-text {
            top: 0;
        }

        .container-img {
            opacity: 30%;
        }
    }

    .container-language {
        img {
            width: 20px;
            margin-left: 3px;
        }
    }
}
</style>