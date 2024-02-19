<script setup>
import { Cropper } from 'vue-advanced-cropper'
import 'vue-advanced-cropper/dist/style.css'

import { ref, defineProps } from 'vue'

const props = defineProps({
    img: String
})

const image = ref('')

const change = ({coordinates, canvas}) => {
  image.value = canvas.toDataURL()
}

</script>
<template>
   <h1>Cropper</h1>
        <div style="margin: 100px;">
        <img :src="image" width="200" height="200">
        </div>

        <cropper
            :src="props.img"
            :stencil-props="{
            aspectRatio: 10/10
            }"
            @change="change"
            /> 
</template>