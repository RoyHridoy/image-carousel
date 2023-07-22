<script setup>
import { ref } from 'vue';
let currentImage = ref(0)
const images = [
    {
        thumb: "https://images.unsplash.com/photo-1559863345-02eae058c2c2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=70&q=80",
        full: "https://images.unsplash.com/photo-1559863345-02eae058c2c2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80",
        title: 'vue 3 is fun',
        description: 'Music marry as at cause party worth weeks. Saw how marianne graceful dissuade new outlived prospect followed. Uneasy no settle whence nature narrow in afraid.'
    },
    {
        thumb: "https://plus.unsplash.com/premium_photo-1688385848467-781c5394c017?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=70&q=80",
        full: "https://plus.unsplash.com/premium_photo-1688385848467-781c5394c017?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80",
        title: 'creating a slider is fun',
        description: 'Whether article spirits new her covered hastily sitting her. Money witty books nor son add. Chicken age had evening believe but proceed pretend mrs.'
    },
    {
        thumb: "https://images.unsplash.com/photo-1533228876829-65c94e7b5025?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=70&q=80",
        full: "https://images.unsplash.com/photo-1533228876829-65c94e7b5025?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80",
        title: 'javascript is awesome',
        description: 'Style too own civil out along. Perfectly offending attempted add arranging age gentleman concluded. Get who uncommonly our expression ten increasing considered occasional travelling.'
    },
    {
        thumb: "https://images.unsplash.com/photo-1529970120821-d8cf525bc023?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=70&q=80",
        full: "https://images.unsplash.com/photo-1529970120821-d8cf525bc023?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80",
        title: 'reactivity creates fun',
        description: 'In eldest be it result should remark vanity square. Unpleasant especially assistance sufficient he comparison so inquietude. Branch one shy edward stairs turned has law wonder horses.'
    },
    {
        thumb: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=70&q=80',
        full: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80',
        title: 'You make my day',
        description: 'Little afraid its eat looked now. Very ye lady girl them good me make. It hardly cousin me always. An shortly village is raising we shewing replied. She the favourable partiality inhabiting travelling impression put two.'
    }
]

function previousImage() {
    currentImage.value === 0 ? currentImage.value = images.length - 1 : --currentImage.value
}

function nextImage() {
    currentImage.value === images.length - 1 ? currentImage.value = 0 : ++currentImage.value
}

function showImage(index) {
    currentImage.value = index
}

</script>

<template>
    <section class="w-full flex items-center flex-col">
        <div class="w-full h-screen bg-gradient-to-r from-slate-300 to-slate-500">
            <div class="fade w-full h-full bg-cover bg-center overlay"
                :style="'background-image:url(' + images[currentImage].full + ')'">
                <div class="slider-nav">
                    <i @click="previousImage()"
                        class="left-3 sm:left-8 bi bi-arrow-left-circle cursor-pointer text-slate-100 transition hover:text-sky-600"></i>
                    <i @click="nextImage()"
                        class="right-3 sm:right-8 bi bi-arrow-right-circle cursor-pointer transition text-slate-100 hover:text-sky-600"></i>
                </div>
                <div class="container mx-auto text-center flex justify-center items-center h-full">
                    <div class="sm:w-5/6 md:w-2/3 px-10">
                        <h1
                            class="text-3xl sm:text-4xl md:text-6xl my-5 text-slate-100 uppercase block tracking-wide font-medium">
                            {{ images[currentImage].title }}</h1>
                        <p class="text-md md:text-xl text-slate-300 leading-6 md:leading-10">{{
                            images[currentImage].description }}</p>
                        <a href=""
                            class="rounded transition duration-300 bg-sky-500 inline-block py-2 px-5 uppercase mx-2 my-8 text-slate-50 hover:bg-sky-800 border-2 border-sky-500 hover:border-sky-800 font-medium tracking-wide">sign
                            up</a>
                        <a href=""
                            class="rounded transition duration-300 bg-slate-50 inline-block py-2 px-5 uppercase mx-2 my-8 text-slate-950 hover:bg-sky-700 hover:text-slate-50 border-2 border-slate-50 hover:border-sky-700 font-medium tracking-wide">see
                            more</a>
                    </div>
                </div>
                <div class="slider-dots">
                    <span @click="showImage(index)" v-for="(image, index) in images" :key="image.thumb" class="dot"></span>
                </div>
                <div class="flex space-x-2 thumb">
                    <div @click="showImage(index)" v-for="(image, index) in images" :key="index" class="img">
                        <img :src="image.thumb" alt="" class="cursor-pointer">
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.fade {
    transition: all 0.4s ease-out;
}

.overlay {
    position: relative;
    z-index: 1;
}

.overlay:before {
    content: "";
    background-color: #000;
    position: absolute;
    width: 100%;
    height: 100%;
    z-index: -1;
    opacity: 0.7;
}

.slider-nav i {
    font-size: 40px;
    position: absolute;
    bottom: 20px;
    /* left: 30px; */
    line-height: 30px;
    z-index: 2;
    transition: 0.3s;
}

.slider-nav i:last-child {
    /* right: 30px; */
    left: auto;
}

.slider-dots {
    position: absolute;
    z-index: 1;
    text-align: center;
    bottom: calc(50% - 20px);
    right: 20px;
}

.slider-dots .dot {
    width: 20px;
    height: 20px;
    background-color: #999999;
    display: block;
    margin-bottom: 10px;
    transition: 0.3s;
    cursor: pointer;
    border: 6px double #000000;
    border-radius: 50%;
}

.slider-dots .dot:hover {
    background-color: #eeeeee;
}

.thumb {
    position: absolute;
    left: 0;
    right: 0;
    text-align: center;
    bottom: 20px;
    justify-content: center;
}

.thumb .img {
    position: relative;
    z-index: 1;
}

.thumb div:after {
    position: absolute;
    content: "";
    background-color: #000;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    z-index: 0;
    cursor: pointer;
    opacity: 0.5;
    transition: all 0.3s ease-out;
}

.thumb .img:hover:after {
    opacity: 0.3;
}
</style>