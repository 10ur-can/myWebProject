<template>
    <div class="iconLogos">
    <iconInstegram></iconInstegram>
    <iconFacebook></iconFacebook>
    <iconYoutube></iconYoutube>
    </div>
</template>

<script setup>
import iconFacebook from '@/components/atoms/a-icon-facebook.vue'
import iconInstegram from '@/components/atoms/a-icon-instegram.vue'
import iconYoutube from '@/components/atoms/a-icon-youtube.vue'

</script>

<style scoped>
 .iconLogos{
    display:inline-block;
    background-color :	#151B54;
    width: auto;
    margin-right: 10px;
    display:flex;
    justify-content: flex-end;
 }

</style>