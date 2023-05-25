<script>

import CardComponents from './CardComponents.vue';

export default {
    props: {
        listTitle: String,
        arrCards: Array,
    },

    components: {
        CardComponents,
    },
};

</script>

<template>
    <h2>{{ listTitle }}</h2>
    <CardComponents />
</template>

<style lang="scss" scoped></style>