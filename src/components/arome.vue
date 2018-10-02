<template>


</template>

<script>

export default {
    name: 'arome',
    props: ['itemdata', 'row'],
    template: '#item-template',
    data: function () {
        return {
        selected: this.itemdata[0]
        }
    },
    methods: {
        remove() {
            this.$emit('remove');
        }
    }
}

</script>