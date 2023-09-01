<template>
    <div id="main">
        <Header @navBarOpen="navBarOpen = true" />
        <right-side-bar />
        <div class="container">
            <section class="banner">
                <div class="bannerTitle">
                    <h2 class="title">專業運輸、五星感受。</h2>
                </div>
                <div class="shadow">
                    <div class="shadow-anime">
                        <div class="shadow-anime-obj"></div>
                    </div>
                </div>
                <div class="car">
                    <div class="car-anime">
                        <div class="car-anime-obj"></div>
                    </div>
                </div>
                <div class="bgIcon">
                    <div :class="`bgIcon__${index + 1}`" v-for="(item, index) in 2" :key="'bgIcon' + index" data-anime>
                        <div :class="`bgIcon__${index + 1}-anime bgIconAnime`">
                            <div :class="`bgIcon__${index + 1}-anime-obj`"></div>
                        </div>
                    </div>
                </div>
                <div class="bgBlur">
                    <div class="bgBlur-anime">
                        <div class="bgBlur-anime-obj"></div>
                    </div>
                </div>
                <div class="subbar">
                    <div class="subbar-anime">
                        <div class="subbar-anime-obj"></div>
                    </div>
                </div>
                <div class="subtitle">
                    <div class="subtitle-anime">
                        <div class="subtitle-anime-obj"></div>
                    </div>
                </div>
                <div class="readmore">
                    <a href="/aboutUs">
                        <div class="readmore-anime">
                            <div class="readmore-anime-obj"></div>
                        </div>
                    </a>
                </div>
                <div class="reserve">
                    <a href="/">
                        <div class="reserve-anime">
                            <div class="reserve-anime-obj"></div>
                        </div>
                    </a>
                </div>
                <div class="height"></div>
            </section>
            <section class="ourVision">
                <div class="title">
                    <div class="title-anime">
                        <div class="title-anime-obj"></div>
                    </div>
                </div>
                <div class="des">
                    寶輇車業嚴格把關要求，每一位司機皆受過專業的培訓課程，<br />
                    要求重視對待客戶，以客為尊，講求親切態度與專業服務。<br />
                    客戶放心和滿意的服務，就是我們最大的動力和目標。<br />
                    快速抵達、滿意服務、齊全設備、細心流程、專業人員 <br />
                    是我們對自己最大的要求！<br />
                </div>
                <div class="mbDes">
                    寶輇車業嚴格把關要求，每一位司機皆受過<br />
                    專業的培訓課程，要求重視對待客戶，<br />
                    以客為尊，講求親切態度與專業服務。<br />
                    客戶放心和滿意的服務，<br />
                    就是我們最大的動力和目標。<br />
                    快速抵達、滿意服務、齊全設備、<br />
                    細心流程、專業人員 <br />
                    是我們對自己最大的要求！<br />
                </div>
                <div class="visionBtnContain">
                    <div class="visionBtn">
                        <div :class="`visionBtn__${index + 1}`" v-for="(item, index) in visionUrl" :key="'visionBtn' + index" data-anime>
                            <a :href="item.url">
                                <div :class="`visionBtn__${index + 1}-anime visionBtnAnime`">
                                    <div :class="`visionBtn__${index + 1}-anime-obj`"></div>
                                </div>
                            </a>
                        </div>
                    </div>
                </div>

                <div class="height"></div>
            </section>
            <section class="case">
                <div class="bgIcon">
                    <div class="bgIcon-anime">
                        <div class="bgIcon-anime-obj"></div>
                    </div>
                </div>
                <div class="title1">
                    <div class="title1-anime">
                        <div class="title1-anime-obj"></div>
                    </div>
                </div>
                <div class="title2">
                    <div class="title2-anime">
                        <div class="title2-anime-obj">實際案例</div>
                    </div>
                </div>
                <div class="subTitle">
                    <div class="subTitle-anime">
                        <div class="subTitle-anime-obj"></div>
                    </div>
                </div>
                <div class="caseContain" v-for="(item, index) in caseList" :key="'case' + index" data-anime>
                    <div v-if="index + 1 == caseNum">
                        <div class="car">
                            <div :class="`car__${index + 1}`">
                                <div :class="`car__${index + 1}-anime carAnime`">
                                    <div :class="`car__${index + 1}-anime-obj`" :style="`background-image: url(${item.caseBg})`"></div>
                                </div>
                            </div>
                        </div>
                        <div class="circle">
                            <div class="circle-anime">
                                <div class="circle-anime-obj"></div>
                            </div>
                        </div>
                        <div class="carItem">
                            <div :class="`carItem__${index + 1}`">
                                <div :class="`carItem__${index + 1}-anime carItemAnime`">
                                    <div :class="`carItem__${index + 1}-anime-obj`" :style="`background-image: url(${item.caseImg})`"></div>
                                </div>
                            </div>
                        </div>
                        <div class="caseWrap">
                            <div class="caseName">
                                <div class="caseName-anime">
                                    <div class="caseName-anime-obj">藍寶堅尼保養後協助拖運</div>
                                </div>
                            </div>
                            <div class="caseDes">
                                <div class="caseDes-anime">
                                    <textarea readonly class="caseDes-anime-obj" v-model="item.des"></textarea>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="circleItem" v-for="(item, index) in caseList" :key="'casePoint' + index" data-anime>
                    <div :class="`circleItem__${index + 1}`">
                        <div class="circlePoint">
                            <div :class="`circlePoint__${index + 1}-anime circlePointAnime`" @click="caseNum = index + 1">
                                <div :class="`circlePoint__${index + 1}-anime-obj`"></div>
                            </div>
                        </div>
                        <div class="circleTxt">
                            <div :class="`circleTxt__${index + 1}-anime circleTxtAnime`" @click="caseNum = index + 1">
                                <div :class="`circleTxt__${index + 1}-anime-obj`">{{ item.title }}</div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="readmore">
                    <div class="readmore-anime">
                        <div class="readmore-anime-obj"></div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="video">
                <div class="bgIcon">
                    <div class="bgIcon-anime">
                        <div class="bgIcon-anime-obj"></div>
                    </div>
                </div>
                <div class="title">
                    <div class="title-anime">
                        <div class="title-anime-obj"></div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="carVideo">
                <div class="carVideoBox">
                    <iframe
                        src="https://www.youtube.com/embed/JW_JhFhVEAw?si=pzS9tJb05b2rRlga"
                        title="BC Haul video"
                        frameborder="0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                        allowfullscreen
                    ></iframe>
                </div>
                <div class="height"></div>
            </section>
            <section class="news">
                <div class="newsContain">
                    <div class="bgIcon">
                        <div :class="`bgIcon__${index + 1}`" v-for="(item, index) in 2" :key="'bgIcon' + index" data-anime>
                            <div :class="`bgIcon__${index + 1}-anime bgIconAnime`">
                                <div :class="`bgIcon__${index + 1}-anime-obj`"></div>
                            </div>
                        </div>
                    </div>
                    <div class="title1">
                        <div class="title1-anime">
                            <div class="title1-anime-obj">最新消息</div>
                        </div>
                    </div>
                    <div class="title2">
                        <div class="title2-anime">
                            <div class="title2-anime-obj"></div>
                        </div>
                    </div>
                    <div class="readmore">
                        <a href="/news">
                            <div class="readmore-anime">
                                <div class="readmore-anime-obj"></div>
                            </div>
                        </a>
                    </div>
                </div>

                <div class="newsList">
                    <swiper class="swiper" :options="swiperOption">
                        <swiper-slide :class="`newsList__${index + 1} newsListBox`" v-for="(item, index) in news" :key="'newsList' + index" data-anime>
                            <div :class="`newsList__${index + 1}-anime newsListAnime`">
                                <a :href="item.url">
                                    <img class="newsImg" :src="item.image" />
                                </a>
                                <a :href="item.url">
                                    <div class="newsTxt">
                                        <p class="title">{{ item.title }}</p>
                                        <div class="des">{{ item.des }}</div>
                                        <p class="date">{{ item.date }}</p>
                                        <div class="height"></div>
                                    </div>
                                </a>
                            </div>
                        </swiper-slide>
                        <div class="swiper-button-prev" slot="button-prev"></div>
                        <div class="swiper-button-next" slot="button-next"></div>
                    </swiper>
                </div>
                <div class="height"></div>
            </section>
        </div>
        <Footer />
        <Nav-bar @navBarOpen="navBarOpen = false" v-if="navBarOpen" />
    </div>
</template>

<script>
import rightSideBar from '../components/rightSideBar.vue'
export default {
    components: { rightSideBar },
    name: 'IndexPage',
    data() {
        return {
            caseNum: 1,
            navBarOpen: false,
            caseList: [
                {
                    title: '保養運送',
                    caseImg: require('@/static/image/pc/main/circlepic-1.png'),
                    caseBg: require('@/static/image/pc/main/car-background-1.png'),
                    des: '寶輇車業是對於車子很愛惜的一家公司，才會專屬打造了透明車廂體，保護好客戶的愛車不被風吹雨淋，也給予客戶看的到的保障。我們的司機師傅揣著對於車子的喜愛，為客戶運送著車輛。',
                },
                {
                    title: '超跑運載',
                    caseImg: require('@/static/image/pc/main/circlepic-2.png'),
                    caseBg: require('@/static/image/pc/main/car-background-2.png'),
                    des: '特別謹慎處理，上車時的角度幾乎貼近地面，一點都不用擔心會刮傷車輛，提供6個角度的即時影像，隨時可以看到愛車在車廂狀況以及到目的地下載的視訊狀況甚至可以監控到司機駕駛中的情況，非常安心。',
                },
                {
                    title: '車測運送',
                    caseImg: require('@/static/image/pc/main/circlepic-3.png'),
                    caseBg: require('@/static/image/pc/main/car-background-3.png'),
                    des: '為確保車輛安全到達測試場地，提供可靠的運輸，確保車輛狀態不受損，有助於順利進行測試流程，司機貼心現場等候測試完成後載回車輛，完成整個服務。',
                },
                {
                    title: '車隊運送',
                    caseImg: require('@/static/image/pc/main/circlepic-4.png'),
                    caseBg: require('@/static/image/pc/main/car-background-4.png'),
                    des: '提供高效率的多輛運輸，幫助車隊在不同地點間快速調度車輛，降低成本，確保整個運輸過程無縫協調。',
                },
            ],
            news: [
                {
                    title: '寶輇車業 試營運！',
                    des: '寶輇車業開始試營運，歡迎舊雨新知有需要服務的朋友，隨時找我們合作，謝謝。',
                    image: require('@/static/image/pc/news/news1.png'),
                    date: '2023.08.10',
                    url: '/news',
                },
                {
                    title: '汽車品牌託運合作特約活動',
                    des: '汽車品牌與託運服務業者攜手合作提供更尊榮的服務，為汽車品牌專屬優惠和合作方案，促進彼此間的合作關係。',
                    image: require('@/static/image/pc/news/news2.png'),
                    date: '2023.08.10',
                    url: '/news',
                },
                {
                    title: '車隊託運合作特約簽訂活動',
                    des: '特定車隊與託運業者達成合作協議，提供定制合同條款和優惠價格，深化雙方間的夥伴關係。',
                    image: require('@/static/image/pc/news/news3.png'),
                    date: '2023.08.10',
                    url: '/news',
                },
                {
                    title: '車商託運合作特約合作計畫',
                    des: '車商和託運業者合作，共同制定行銷策略和協作計劃，實現雙贏的商機。',
                    image: require('@/static/image/pc/news/news4.png'),
                    date: '2023.08.10',
                    url: '/news',
                },
                {
                    title: 'VIP頂級客戶會員儲值託運方案活動',
                    des: '專為VIP頂級客戶設計的會員儲值託運方案，提供獨家儲值優惠和高級託運服務，提升客戶滿意度。',
                    image: require('@/static/image/pc/news/news5.png'),
                    date: '2023.08.10',
                    url: '/news',
                },
                {
                    title: '試營運託運合作限時活動',
                    des: '新車型或服務推出前的試營運託運合作活動，讓消費者首先體驗特別價格或專屬服務。',
                    image: require('@/static/image/pc/news/news6.png'),
                    date: '2023.08.10',
                    url: '/news',
                },
                {
                    title: '品牌車廂行銷廣告活動合作',
                    des: '品牌和託運業者合作，透過車廂行銷廣告活動，提升品牌知名度和市場影響力。',
                    image: require('@/static/image/pc/news/news7.png'),
                    date: '2023.08.10',
                    url: '/news',
                },
                {
                    title: '新款車輛機密運送合作',
                    des: '車商和託運業者合作，共同制定行銷策略和協作計劃，實現雙贏的商機。',
                    image: require('@/static/image/pc/news/news8.png'),
                    date: '2023.08.10',
                    url: '/news',
                },
            ],
            visionUrl:[
                {url:'/model'},
                {url:'/news'},
                {url:'/model'},
                {url:'/news'}
            ],
            swiperOption: {
                autoplay: 2000,
                // speed: 300,
                loop: false,
                slidesPerView: 3,
                spaceBetween: 0,
                breakpoints: {
                    1024: {
                        slidesPerView: 2,
                    },
                    768: {
                        slidesPerView: 1,
                        spaceBetween: 100,
                    },
                    375: {
                        slidesPerView: 1,
                        spaceBetween: 100,
                    },
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev',
                },
            },
            isMobile: false,
        }
    },
    mounted() {
        this.isDevice()
        window.bannerAnime()
        window.scrollAnime(this.isMobile)
        addEventListener('resize',()=>{
            this.isDevice()
        })
        
    },
    methods: {
        isDevice (){
            if(window.innerWidth < 768){
                this.isMobile = true
            } else {
                this.isMobile = false
            }
        }
    },
}
</script>
