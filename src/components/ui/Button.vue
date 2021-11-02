<template>
    <button class="button">
        {{text}}
    </button>
</template>

<script>
    export default {
        name: "Button",
        props: {
            text: {
                type: [Number, String],
                require: false
            }
         }
    }

</script>


