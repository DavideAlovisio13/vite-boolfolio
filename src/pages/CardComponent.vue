<template>
    <div class="card" style="width: 18rem;">
        <div class="card-body">
            <h5 class="card-title">{{ name }}</h5>
            <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's
                content.</p>
            <a href="#" class="card-link">Card link</a>
            <a href="#" class="card-link">Another link</a>
        </div>
    </div>
</template>

<script>
import { store } from '@/components/store';

export default {
    name: 'CardComponent',

    props: ['name'],

    data() {
        return {
            store
        }
    },
}
</script>

<style lang="scss" scoped></style>