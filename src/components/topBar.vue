<template>
    <div id=topBar>
        <v-button :onClick="consoleClick" id="HomeButton"> Home </v-button>
    </div>
</template>

<script>
import Button from './Button'

export default {
    template: 'topBar/',
    components: {
        'v-button': Button
    },
    methods: {
        consoleClick() {
            console.log('Button clicked')
        }
    }
}
</script>

<style>
#topBar{
    height: 4rem;
    background-color:moccasin;
    padding: 0rem;
    display: flex;
    align-items: center;
    justify-content:end;
}

#HomeButton {
max-width: 50%;
margin: 1em;
}

#mainImage{
}

</style>