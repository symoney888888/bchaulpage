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
                            <a href="javascript:void(0);">
                                <img class="newsImg" :src="require(`@/static/image${item.image}`)" />
                            </a>
                            <a href="javascript:void(0);">
                                <div class="newsTxt">
                                    <p class="title">{{ item.title }}</p>
                                    <div class="des">{{ item.des }}</div>
                                    <p class="date">{{ item.date }}</p>
                                    <div class="height"></div>
                                </div>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <Footer />
        <Nav-bar @navBarOpen="navBarOpen = false" v-if="navBarOpen" />
        <News-pop-up :news-list="newsContainList" :pop-up-num="popUpNum" v-if="popUpActive" @popUpClose="popUpActive = false" />
    </div>
</template>
<script>
import newsList from '~/assets/json/newsPageData/newsList.json'
export default {
    data() {
        return {
            navBarOpen: false,
            popUpActive: false,
            popUpNum: 0,
            // newsContainList: [
            //     {
            //         title: '寶輇車業 試營運！',
            //         des: '寶輇車業開始試營運，歡迎舊雨新知有需要服務的朋友，隨時找我們合作，謝謝。',
            //         image: require('@/static/image/pc/news/news1.png'),
            //         date: '2023.08.10',
            //         url: '/',
            //     },
            //     {
            //         title: '汽車品牌託運合作特約活動',
            //         des: '汽車品牌與託運服務業者攜手合作提供更尊榮的服務，為汽車品牌專屬優惠和合作方案，促進彼此間的合作關係。',
            //         image: require('@/static/image/pc/news/news2.png'),
            //         date: '2023.08.10',
            //         url: '/aboutUs',
            //     },
            //     {
            //         title: '車隊託運合作特約簽訂活動',
            //         des: '特定車隊與託運業者達成合作協議，提供定制合同條款和優惠價格，深化雙方間的夥伴關係。',
            //         image: require('@/static/image/pc/news/news3.png'),
            //         date: '2023.08.10',
            //         url: '/',
            //     },
            //     {
            //         title: '車商託運合作特約合作計畫',
            //         des: '車商和託運業者合作，共同制定行銷策略和協作計劃，實現雙贏的商機。',
            //         image: require('@/static/image/pc/news/news4.png'),
            //         date: '2023.08.10',
            //         url: '/aboutUs',
            //     },
            //     {
            //         title: 'VIP頂級客戶會員儲值託運方案活動',
            //         des: '專為VIP頂級客戶設計的會員儲值託運方案，提供獨家儲值優惠和高級託運服務，提升客戶滿意度。',
            //         image: require('@/static/image/pc/news/news5.png'),
            //         date: '2023.08.10',
            //         url: '/',
            //     },
            //     {
            //         title: '試營運託運合作限時活動',
            //         des: '新車型或服務推出前的試營運託運合作活動，讓消費者首先體驗特別價格或專屬服務。',
            //         image: require('@/static/image/pc/news/news6.png'),
            //         date: '2023.08.10',
            //         url: '/',
            //     },
            //     {
            //         title: '品牌車廂行銷廣告活動合作',
            //         des: '品牌和託運業者合作，透過車廂行銷廣告活動，提升品牌知名度和市場影響力。',
            //         image: require('@/static/image/pc/news/news7.png'),
            //         date: '2023.08.10',
            //         url: '/',
            //     },
            //     {
            //         title: '新款車輛機密運送合作',
            //         des: '車商和託運業者合作，共同制定行銷策略和協作計劃，實現雙贏的商機。',
            //         image: require('@/static/image/pc/news/news8.png'),
            //         date: '2023.08.10',
            //         url: '/',
            //     },
            // ],
            newsContainList:newsList.newsContainList
        }
    },
    mounted() {
        window.newsPageAnime()
        console.log(newsList)
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
