<template>
    <div class="tag"
         v-on:click="onClick"
         :class="{ 'active': value }"
    >
        {{text}}
    </div>
</template>

<script>
    export default {
        name: "Tag",
        data: () => ({
            value: Boolean
        }),
        props: {
            text: {
                type: [Number, String],
                require: false
            }
        },
        methods: {
            onClick () {
                this.value = !this.value
                this.$emit()
            }
        }
    }
</script>

