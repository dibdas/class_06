<template>
    <div>
        <button v-on:click="onClick">Click Me</button>
    </div>
</template>

<script>
export default {
    methods: {
        onClick(){
            this.$emit("myEvent");
        }
    }
}
</script>
