<template>
    <div>
        <Header @navBarOpen="navBarOpen = true" />
        <right-side-bar />
        <div id="servicePage">
            <section class="banner">
                <div class="bgImg">
                    <div class="bgImg-anime">
                        <div class="bgImg-anime-obj"></div>
                    </div>
                </div>
                <div class="title">
                    <div class="title-anime">
                        <div class="title-anime-obj">SERVICE</div>
                    </div>
                </div>
                <div class="subTitle">
                    <div class="subTitle-anime">
                        <div class="subTitle-anime-obj">服務項目</div>
                    </div>
                </div>
                <div class="navBtn">
                    <div class="navBtnWrap">
                        <div class="navBtnAnime">
                            <span @click="scrollTo('serviceList')">頂級車輛托運</span>
                        </div>
                        <div class="navBtnAnime">
                            <span @click="scrollTo('case')">服務案例</span>
                        </div>
                        <div class="navBtnAnime">
                            <span @click="scrollTo('QAList')">常見問題</span>
                        </div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="serviceList">
                <div class="serviceListBox">
                    <div class="serviceListContain">
                        <swiper
                            class="ServiceSwiper"
                            :options="swiperOption"
                            ref="zSwiper"
                        >
                            <swiper-slide
                                :class="`serviceList__${index + 1}`"
                                v-for="(item, index) in serviceList"
                                :key="'serviceList' + index"
                                data-anime
                            >
                                <div
                                    :class="`serviceList__${
                                        index + 1
                                    }-anime serviceListAnime`"
                                >
                                    <div class="serviceListImg">
                                        <img :src="require(`@/static/image${item.image}`)" />
                                    </div>
                                    <div class="serviceListBlur">
                                        <img
                                            :src="
                                                require('@/static/image/pc/service/rectangle.png')
                                            "
                                        />
                                    </div>
                                    <div class="serviceListTxt">
                                        <p class="title">{{ item.title }}</p>
                                        <textarea
                                            class="des"
                                            v-model="item.des"
                                            readonly
                                        ></textarea>
                                    </div>
                                </div>
                            </swiper-slide>
                            <div class="swiper-pagination" slot="button-pagination"></div>
                            <div class="swiper-button-prev" slot="button-prev"></div>
                            <div class="swiper-button-next" slot="button-next"></div>
                        </swiper>
                        <div class="swiper-pagination" slot="button-pagination"></div>
                        <div class="serviceItemNum">
                            0{{ serviceList.length
                            }}<span>/0{{ listCurrentNum + 1 }}</span>
                        </div>
                        <div class="serviceTitleContain">
                            <div
                                :class="`serviceListTitle serviceListTitle${index + 1}`"
                                v-for="(item, index) in serviceList"
                                :key="'serviceListTitle' + index"
                                @click="changeListNum(index)"
                            >
                                <div class="title">
                                    <span>{{ "0" + (index + 1) }}</span>
                                    <span class="titleTxt">{{ item.title }}</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="case">
                <div class="bgIcon">
                    <div
                        :class="`bgIcon__${index + 1}`"
                        v-for="(item, index) in 4"
                        :key="'bgIcon' + index"
                        data-anime
                    >
                        <div :class="`bgIcon__${index + 1}-anime bgIconAnime`">
                            <div :class="`bgIcon__${index + 1}-anime-obj`"></div>
                        </div>
                    </div>
                </div>
                <div class="title1">
                    <div class="title1-anime">
                        <div class="title1-anime-obj"></div>
                    </div>
                </div>
                <div class="title2">
                    <div class="title2-anime">
                        <div class="title2-anime-obj">服務案例</div>
                    </div>
                </div>
                <div class="caseSlider">
                    <swiper class=" swiper caseSwiper1"  :options="swiperCase1Option" ref="swiperTop">
                            <swiper-slide
                                :class="`caseList__${index + 1} caseListAnime`"
                                v-for="(item, index) in caseList"
                                :key="'caseList' + index"
                            >   
                                <div :class="`caseList__${index + 1}-anime caseListAnime`">
                                    <div class="caseList1Img">
                                        <img :src="require(`@/static/image${item.image}`)" />
                                    </div>
                                    <div class="caseList1Txt">
                                        <div class="caseList1TxtWrap">
                                            <p class="name">{{ item.title }}</p>
                                            <p class="des" readonly>{{ item.des }}</p>
                                        </div>
                                    </div>
                                </div>
                            </swiper-slide>
                            <div class="swiper-button-prev slide-one-button-prev caseSwiper1-button-prev" slot="button-prev"></div>
                            <div class="swiper-button-next slide-one-button-next caseSwiper1-button-next" slot="button-next"></div>
                    </swiper>
                    <swiper class="swiper caseSwiper2" :options="swiperCase2Option" ref="swiperThumbs">
                            <swiper-slide
                                :class="`caseList2__${index + 1} caseList2Anime`"
                                v-for="(item, index) in caseList"
                                :key="'caseList2' + index"
                            >
                                <div class="sliderWrap">
                                    <div class="sliderImg">
                                        <img :src="require(`@/static/image${item.image}`)" alt="">
                                    </div>
                                </div>
                            </swiper-slide>
                    </swiper>
                    <div class="swiper-button-prev slide-one-button-prev caseSwiper2-button-prev" slot="button-prev"></div>
                    <div class="swiper-button-next slide-one-button-next caseSwiper2-button-next" slot="button-next"></div>
                </div>
                <div class="height"></div>
            </section>
            <section class="QAList">
                <div class="bgIcon">
                    <div
                        :class="`bgIcon__${index + 1}`"
                        v-for="(item, index) in 4"
                        :key="'bgIcon' + index"
                        data-anime
                    >
                        <div :class="`bgIcon__${index + 1}-anime bgIconAnime`">
                            <div :class="`bgIcon__${index + 1}-anime-obj`"></div>
                        </div>
                    </div>
                </div>
                <div class="title1">
                    <div class="title1-anime">
                        <div class="title1-anime-obj"></div>
                    </div>
                </div>
                <div class="title2">
                    <div class="title2-anime">
                        <div class="title2-anime-obj">常見問題</div>
                    </div>
                </div>
                
                <div class="height"></div>
            </section>
            <div class="QAInfo">
                <div class="QAInfoWrap">
                    <div :class="`infoList__${index + 1} infoList`"
                        v-for="(item, index) in qaInfoList"
                        :key="'infoList' + index">
                        <div class="infoTitleContain" @click="infoOpenChange(index)">
                            <div :class="`infoListTitle__${index + 1}`">
                                {{ item.title }}
                            </div>
                            <div :class="`infoListTitleIcon__${index + 1}`"></div>
                        </div>
                        <transition>
                            <div :class="`infoListDes__${index + 1} infoListDesContain`" v-if="infoOpen == index">
                                {{ item.des }}
                            </div>
                        </transition>
                    </div>
                    <div class="infoTxt">若有任何問題歡迎撥打客服專線<span>0800-234-222</span></div>
                </div>
            </div>
        </div>
        <Footer />
        <Nav-bar @navBarOpen="navBarOpen = false" v-if="navBarOpen" />
    </div>
</template>
<script>
import serviceListData from '~/assets/json/servicePageData/serviceList.json'
export default {
    data() {
        return {
            swiper: null,
            navBarOpen: false,
            aboutUsNavBtnList: ["公司簡介", "員工技術技能簡介", "法律顧問團隊"],
            serviceList: serviceListData.serviceList,
            serviceListNum: 0,
            listCurrentNum: 0,
            swiperOption: {
                autoplay: 2000,
                // speed: 300,
                loop: false,
                slidesPerView: 1,
                spaceBetween: 0,
                breakpoints: {
                    1024: {
                        slidesPerView: 1,
                    },
                    768: {
                        slidesPerView: 1,
                    },
                },
                navigation: {
                    nextEl: ".swiper-button-next",
                    prevEl: ".swiper-button-prev",
                },
                pagination: {
                    el: ".swiper-pagination",
                    type: "progressbar",
                },
                on: {
                    slideChange: function () {
                        const self = this;
                        self.serviceListNum = this.activeIndex;
                        console.log("self.serviceListNum", self.serviceListNum);
                        let allListTitle = document.querySelectorAll(
                            ".serviceListTitle .title"
                        );
                        allListTitle.forEach((item) => {
                            item.style.color = "#ffffff";
                        });
                        allListTitle[this.activeIndex].style.color = "#97f540";
                    },
                },
            },
            caseList: serviceListData.caseList,
            swiperCase1Option:{
                loop:true,
                loopedSlides: 6,
                spaceBetween: 10,
                thumbs:{
                    swiper: {
                        el:'.caseSwiper2',
                        loopedSlides: 6,
                        spaceBetween: 35,
                        slidesPerView: 6,
                        touchRatio:0.2,
                        slideToClickedSlide:true
                    }
                },
                navigation: {
                    nextEl: '.caseSwiper1-button-next',
                    prevEl: '.caseSwiper1-button-prev'
                },

            },
            swiperCase2Option:{
                loop:true,
                loopedSlides: 6,
                spaceBetween: 35,
                slidesPerView: 3,
                touchRatio:0.2,
                freeMode: true,
                centeredSlides: true,
                slideToClickedSlide:true,
                navigation: {
                    nextEl: '.caseSwiper2-button-next',
                    prevEl: '.caseSwiper2-button-prev'
                },
            },
            qaInfoList:serviceListData.qaInfoList,
            infoOpen: null
        };
    },
    mounted() {
        const self = this;
        window.serviceAnime()
        
        this.$nextTick(() => {
            const swiperTop = this.$refs.swiperTop.swiper
            const swiperThumbs = this.$refs.swiperThumbs.swiper
            console.log('swiperTop', swiperTop)
            console.log('swiperThumbs', swiperThumbs)
            swiperTop.controller.control = swiperThumbs
            swiperThumbs.controller.control = swiperTop
        })
        self.serviceListTitleColor();
        this.$watch(
            () => this.$refs.zSwiper.swiper.activeIndex,
            (val) => {
                this.listCurrentNum = val;
            }
        );
        
    },
    methods: {
        scrollTo(className) {
            const scrollEl = document.getElementsByClassName(className)[0];
            window.scrollTo({
                top: scrollEl.offsetTop,
                behavior: "smooth",
            });
        },
        changeListNum(index) {
            this.$refs.zSwiper.swiper.slideTo(index, 1000, false);
        },
        serviceListTitleColor() {
            let allListTitle = document.querySelectorAll(".serviceListTitle .title");
            allListTitle[this.serviceListNum].style.color = "#97f540";
        },
        infoOpenChange(index){
            if(this.infoOpen === index){
                this.infoOpen = null
            }else {
                this.infoOpen = index
            }
        }
    },
};
</script>
