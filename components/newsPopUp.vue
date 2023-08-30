<template>
<div id="newsPopUp">
    <div class="popUpBg" @click="popUpClose()"></div>
    
    <div class="popUpCard">
        <div class="closeBtn" @click="popUpClose()"><img :src="require('@/static/image/pc/main/closeBtn.png')" alt="" /></div>
        <img class="newsImg" :src="newsList[popUpNum].image" />
        <div class="newsTxt">
            <p class="title">{{ newsList[popUpNum].title }}</p>
            <div class="des">{{ newsList[popUpNum].des }}</div>
            <p class="date">{{ newsList[popUpNum].date }}</p>
            <div class="height"></div>
        </div>
    </div>
</div>    
</template>
<script>
export default {
    props:[
        'popUpNum',
        'newsList'
    ],
    data() {
        return {
        }
    },
    methods: {
        popUpClose() {
            this.$emit('popUpClose')
        }
    },
}
</script>