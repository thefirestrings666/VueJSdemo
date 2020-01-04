<template>
    <div id=center>
        <p v-html="emoji('036-animal-track')"></p>
        <h1>Hello !</h1>
    </div>
</template>

<script>
export default {
    template: 'center/',
    methods: {
        emoji(name) {
        var out = `<img src="../../static/emoji/` + name + `.png">`
        return out
        }
    }   
}
</script>

<style>
img {
  width: 8rem; height: 8rem;

}
</style>