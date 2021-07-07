<template>
    <button @click="onClick()" class="btn btn-primary">{{text}}</button>
</template>

<script>

export default {
    name: 'Button',
    props:['text'],
    methods: {
    onClick() {
        console.log('click')
        }
    },
}

</script>
