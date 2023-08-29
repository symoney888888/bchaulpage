<template>
    <div>
        <Header @navBarOpen="navBarOpen = true" />
        <right-side-bar />
        <div id="newsPage">
            <div class="newsContain">
                <div class="bgIcon">
                    <div :class="`bgIcon__${index + 1}`" v-for="(item, index) in 6" :key="'bgIcon' + index" data-anime>
                        <div :class="`bgIcon__${index + 1}-anime bgIconAnime`">
                            <div :class="`bgIcon__${index + 1}-anime-obj`"></div>
                        </div>
                    </div>
                </div>
                <div class="title">
                    <div class="title-anime">
                        <div class="title-anime-obj">NEWS</div>
                    </div>
                </div>
                <div class="subTitle">
                    <div class="subTitle-anime">
                        <div class="subTitle-anime-obj">最新消息</div>
                    </div>
                </div>
                <div class="height"></div>
            </div>
            <div class="newsList">
                <div class="newsListWrap">
                    <div :class="`newsList__${index + 1} newsListCard`" v-for="(item, index) in newsContainList" :key="'newsList' + index" data-anime>
                        <div :class="`newsList__${index + 1}-anime newsListAnime`" @click="popUpCard(index)">
                            <img class="newsImg" :src="item.image" />
                            <div class="newsTxt">
                                <p class="title">{{ item.title }}</p>
                                <div class="des">{{ item.des }}</div>
                                <p class="date">{{ item.date }}</p>
                                <div class="height"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <Footer />
        <Nav-bar @navBarOpen="navBarOpen = false" v-if="navBarOpen" />
        <News-pop-up :pop-up-num="popUpNum" v-if="popUpActive" @popUpClose="popUpActive = false" />
    </div>
</template>
<script>
export default {
    data() {
        return {
            navBarOpen: false,
            popUpActive: false,
            popUpNum: 0,
            newsContainList: [
                {
                    title: '寶輇車業 試營運！',
                    des: '寶輇車業開始試營運，歡迎舊雨新知有需要服務的朋友，隨時找我們合作，謝謝。',
                    image: require('@/static/image/pc/main/12-copy.png'),
                    date: '2023.08.03',
                    url: '/',
                },
                {
                    title: '汽車品牌託運合作特約活動',
                    des: '汽車品牌與託運服務業者攜手合作提供更尊榮的服務，為汽車品牌專屬優惠和合作方案，促進彼此間的合作關係。',
                    image: require('@/static/image/pc/main/14-copy.png'),
                    date: '2023.08.03',
                    url: '/aboutUs',
                },
                {
                    title: '車隊託運合作特約簽訂活動',
                    des: 'testtesttesttest',
                    image: require('@/static/image/pc/main/12-copy.png'),
                    date: '2023.08.03',
                    url: '/',
                },
                {
                    title: '車商託運合作特約合作計畫',
                    des: 'testtesttesttest',
                    image: require('@/static/image/pc/main/14-copy.png'),
                    date: '2023.08.03',
                    url: '/aboutUs',
                },
                {
                    title: 'VIP頂級客戶會員儲值託運方案活動',
                    des: 'testtesttesttest',
                    image: require('@/static/image/pc/main/12-copy.png'),
                    date: '2023.08.03',
                    url: '/',
                },
                {
                    title: '試營運託運合作限時活動',
                    des: 'testtesttesttest',
                    image: require('@/static/image/pc/main/14-copy.png'),
                    date: '2023.08.03',
                    url: '/',
                },
                {
                    title: '品牌車廂行銷廣告活動合作',
                    des: 'testtesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttestesttesttesttesttesttesttesttesttestesttesttesttesttesttesttesttesttestesttesttesttesttesttesttesttesttestesttesttesttesttesttesttesttesttest',
                    image: require('@/static/image/pc/main/12-copy.png'),
                    date: '2023.08.03',
                    url: '/',
                },
                {
                    title: '新款車輛機密運送合作',
                    des: 'testtesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttesttestesttesttesttesttesttesttesttesttestesttesttesttesttesttesttesttesttestesttesttesttesttesttesttesttesttestesttesttesttesttesttesttesttesttest',
                    image: require('@/static/image/pc/main/12-copy.png'),
                    date: '2023.08.03',
                    url: '/',
                },
            ],
        }
    },
    mounted() {
        window.newsPageAnime()
    },
    methods: {
        popUpCard(index) {
            const self = this
            self.popUpActive = true
            self.popUpNum = index
        },
    },
}
</script>
