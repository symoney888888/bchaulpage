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
                                        <img :src="item.img" />
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
                                        <img :src="item.image" />
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
                                        <img :src="item.image" alt="">
                                    </div>
                                    <div class="sliderImg"></div>

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
export default {
    data() {
        return {
            swiper: null,
            navBarOpen: false,
            aboutUsNavBtnList: ["公司簡介", "員工技術技能簡介", "法律顧問團隊"],
            serviceList: [
                {
                    id: 1,
                    title: "頂級車輛托運",
                    img: require("@/static/image/pc/service/service1.png"),
                    des:
                        "全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。",
                },
                {
                    id: 2,
                    title: "大小車輛運輸",
                    img: require("@/static/image/pc/service/service2.png"),
                    des:
                        "全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。",
                },
                {
                    id: 3,
                    title: "重機托運",
                    img: require("@/static/image/pc/service/service3.png"),
                    des:
                        "全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。",
                },
                {
                    id: 4,
                    title: "特殊車輛運送",
                    img: require("@/static/image/pc/service/service4.png"),
                    des:
                        "全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。",
                },
                {
                    id: 5,
                    title: "重機車隊運輸",
                    img: require("@/static/image/pc/service/service5.png"),
                    des:
                        "全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。",
                },
                {
                    id: 6,
                    title: "大型車聚活動",
                    img: require("@/static/image/pc/service/service6.png"),
                    des:
                        "全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。",
                },
                {
                    id: 7,
                    title: "活動宣傳包車",
                    img: require("@/static/image/pc/service/service7.png"),
                    des:
                        "全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。",
                },
                {
                    id: 8,
                    title: "機場接車服務",
                    img: require("@/static/image/pc/service/service8.png"),
                    des:
                        "全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。",
                },
            ],
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
            caseList: [
                {
                    title: "藍寶堅尼保養後協助拖運",
                    des:
                        "寶輇車業是對於車子很愛惜的一家公司，才會專屬打造了透明車廂體，保護好客戶的愛車不被風吹雨淋，也給予客戶看的到的保障。我們的司機師傅揣著對於車子的喜愛，為客戶運送著車輛。",
                    image: require("@/static/image/pc/service/case2.png"),
                },
                {
                    title: "藍寶堅尼保養後協助拖運",
                    des:
                        "寶輇車業是對於車子很愛惜的一家公司，才會專屬打造了透明車廂體，保護好客戶的愛車不被風吹雨淋，也給予客戶看的到的保障。我們的司機師傅揣著對於車子的喜愛，為客戶運送著車輛。",
                    image: require("@/static/image/pc/service/case3.png"),
                },
                {
                    title: "藍寶堅尼保養後協助拖運",
                    des:
                        "寶輇車業是對於車子很愛惜的一家公司，才會專屬打造了透明車廂體，保護好客戶的愛車不被風吹雨淋，也給予客戶看的到的保障。我們的司機師傅揣著對於車子的喜愛，為客戶運送著車輛。",
                    image: require("@/static/image/pc/service/case4.png"),
                },
                {
                    title: "藍寶堅尼保養後協助拖運",
                    des:
                        "寶輇車業是對於車子很愛惜的一家公司，才會專屬打造了透明車廂體，保護好客戶的愛車不被風吹雨淋，也給予客戶看的到的保障。我們的司機師傅揣著對於車子的喜愛，為客戶運送著車輛。",
                    image: require("@/static/image/pc/service/case2.png"),
                },
                {
                    title: "藍寶堅尼保養後協助拖運",
                    des:
                        "寶輇車業是對於車子很愛惜的一家公司，才會專屬打造了透明車廂體，保護好客戶的愛車不被風吹雨淋，也給予客戶看的到的保障。我們的司機師傅揣著對於車子的喜愛，為客戶運送著車輛。",
                    image: require("@/static/image/pc/service/case3.png"),
                },
                {
                    title: "藍寶堅尼保養後協助拖運",
                    des:
                        "寶輇車業是對於車子很愛惜的一家公司，才會專屬打造了透明車廂體，保護好客戶的愛車不被風吹雨淋，也給予客戶看的到的保障。我們的司機師傅揣著對於車子的喜愛，為客戶運送著車輛。",
                    image: require("@/static/image/pc/service/case4.png"),
                },
            ],
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
            qaInfoList:[
                {
                    title:'Ｑ1：托運車輛到目的地後有問題該怎麼辦?',
                    des:'A：本公司在車輛到達目的地前跟接車人聯繫，到達目的地後接車人當著服務人員根據交車時的驗車照片對汽車進行檢測，如果發現問題，請當下立即與服務人員確認，本司將立即了解詳情並與接車人溝通解決問題。'
                },
                {
                    title:'Ｑ2：託運交車後多久會進行發車?',
                    des:'A：本司會根據車主要求提前安排，但是時間上另外加急的話，需要加收費用。'
                },
                {
                    title:'Ｑ3：託運時會出現損傷嗎?',
                    des:'A：正常情況下運輸過程中待托運車輛是不會出現任何損傷的情況，如果一旦出現汽車損傷，如果是小划痕或瑕疵可以直接找本司索賠，如果出現重大事故，這時候托運商業保險的作用就顯示出來了，由保險公司承擔所有損失。'
                },
                {
                    title:'Ｑ4：承諾託運時效逾期怎麼處理?',
                    des:'A：正常情況下，我司的承諾運輸時效都不會出現逾期，如果出現逾期，我司會採取減免運費的方式來解決托運時效逾期問題。當然車主也可以在簽署協議時提出要求，打比方說遲到賠付。如果出現運輸時效逾期可以要求物流公司進行索賠。'
                },
                {
                    title:'Ｑ5：價格是怎麼計算的呢?',
                    des:'A：各項收費標準採取電話報價，或至現場依照現場情況報價。'
                },
                {
                    title:'Ｑ6：請問你們是多元化支付嗎?',
                    des:'A：目前還是以收取現金為主，其他支付方式正在規劃中，造成您的不便請見諒。'
                },
                {
                    title:'Ｑ7：我要怎麼知道我車輛現在的所在位子?',
                    des:'A：我們的託運車每台都有GPS，您若是擔心您的愛車，可使用APP輸入我們給您的單子，在線上做查看，讓您時刻可以即時知道運送進度。'
                },
                {
                    title:'Ｑ8：你們發票是電子發票嗎?可以使用載具嗎?',
                    des:'A：實在抱歉，目前我們的發票是手開二聯式和手開三聯式，電子發票及載具的部分目前正在規劃中，造成您的不便請見諒。'
                },
                {
                    title:'Ｑ9：你們的託運要多久之前先預約啊',
                    des:'A：一通電話，立即叫車，讓您省去等待的時間。'
                },
            ],
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
