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
                    <a href="/contactUs">
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
                                    <div :class="`car__${index + 1}-anime-obj`" >
                                        <img :src="require(`@/static/image${item.caseBg}`)" alt="">
                                    </div>
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
                                    <div :class="`carItem__${index + 1}-anime-obj`" >
                                        <img :src="require(`@/static/image${item.caseImg}`)" alt="">
                                    </div>
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
                    <a href="/service">
                        <div class="readmore-anime">
                            <div class="readmore-anime-obj"></div>
                        </div>
                    </a>
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
        <News-pop-up :news-list="news" :pop-up-num="popUpNum" v-if="popUpActive" @popUpClose="popUpActive = false" />
    </div>
</template>

<script>
import rightSideBar from '../components/rightSideBar.vue'
import caseListData from '~/assets/json/homePageData/caseList.json'
import newsListData from '~/assets/json/newsPageData/newsList.json'
export default {
    components: { rightSideBar },
    name: 'IndexPage',
    data() {
        return {
            caseNum: 1,
            navBarOpen: false,
            popUpNum: 0,
            popUpActive: false,
            caseList: caseListData.caseList,
            news:newsListData.newsContainList.slice(0, 6),
            visionUrl:[
                {url:'/model'},
                {url:'/news'},
                {url:'/service'},
                {url:'/contactUs'}
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
        const self = this
        this.isDevice()
        document.body.style.overflow = 'hidden'
        self.$nextTick(function () {
            var openAnimeTL = window.bannerAnime()
            openAnimeTL.play().then(() => {
                document.body.style.overflow = ''
            })
        })
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
        },
        popUpCard(index) {
            const self = this
            self.popUpActive = true
            self.popUpNum = index
        },
    },
}
</script>
