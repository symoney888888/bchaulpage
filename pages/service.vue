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
                        <div class="navBtnAnime"><span @click="scrollTo('vision')">頂級車輛托運</span></div>
                        <div class="navBtnAnime"><span @click="scrollTo('ourTeam')">服務案例</span></div>
                        <div class="navBtnAnime"><span @click="scrollTo('legalTeam')">常見問題</span></div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="serviceList">
                <div class="serviceListBox">
                    <div class="serviceListContain">
                        <swiper class="swiper" :options="swiperOption"  ref="zSwiper">
                            <swiper-slide :class="`serviceList__${index + 1}`" v-for="(item, index) in serviceList" :key="'serviceList' + index" data-anime>
                                <div :class="`serviceList__${index + 1}-anime serviceListAnime`">
                                    <div class="serviceListImg">
                                        <img :src="item.img" />
                                    </div>
                                    <div class="serviceListBlur">
                                        <img :src="require('@/static/image/pc/service/rectangle.png')" />
                                    </div>
                                    <div class="serviceListTxt" >
                                        <p class="title">{{ item.title }}</p>
                                        <textarea class="des" v-model="item.des" readonly></textarea>
                                    </div>
                                </div>
                            </swiper-slide>
                            <div class="swiper-pagination" slot="button-pagination"></div>
                            <div class="swiper-button-prev" slot="button-prev"></div>
                            <div class="swiper-button-next" slot="button-next"></div>                            
                        </swiper>
                        <div class="swiper-pagination" slot="button-pagination"></div>
                        <div class="serviceItemNum">0{{ serviceList.length }} <span>/ 0{{ listCurrentNum+1 }}</span></div>
                        <div class="serviceTitleContain">
                            <div :class="`serviceListTitle serviceListTitle${index+1}`" v-for="(item, index) in serviceList" :key="'serviceListTitle' + index" @click="changeListNum(index)" >
                                <div class='title'  >
                                    <span>{{ '0'+ (index+1) }}</span> <span class="titleTxt">{{ item.title }}</span>
                                </div>
                            </div>
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
                        <div class="title2-anime-obj">服務案例</div>
                    </div>
                </div>
                <div class="exampleCard">
                    <div class="exampleCardWrap">
                        <div class="exampleImg">
                            <div class="exampleImg-anime">
                                <img :src="require('@/static/image/pc/service/exampleImage.png')" alt="">
                            </div>
                        </div>
                        <div class="exampleTxt">
                            <div class="exampleTxtTitle">藍寶堅尼保養後協助拖運</div>
                            <div class="exampleTxtDes">寶輇車業是對於車子很愛惜的一家公司，才會專屬打造了透明車廂體，保護好客戶的愛車不被風吹雨淋，也給予客戶看的到的保障。我們的司機師傅揣著對於車子的喜愛，為客戶運送著車輛。</div>
                        </div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
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
            aboutUsNavBtnList: ['公司簡介', '員工技術技能簡介', '法律顧問團隊'],
            serviceList: [
                {
                    id: 1,
                    title:'頂級車輛托運',
                    img: require('@/static/image/pc/service/service1.png'),
                    des: '全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。'
                },
                {
                    id: 2,
                    title:'大小車輛運輸',
                    img: require('@/static/image/pc/service/service2.png'),
                    des: '全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。'
                },
                {
                    id: 3,
                    title:'重機托運',
                    img: require('@/static/image/pc/service/service3.png'),
                    des: '全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。'
                },
                {
                    id: 4,
                    title:'特殊車輛運送',
                    img: require('@/static/image/pc/service/service4.png'),
                    des: '全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。'
                },
                {
                    id: 5,
                    title:'重機車隊運輸',
                    img: require('@/static/image/pc/service/service5.png'),
                    des: '全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。'
                },
                {
                    id: 6,
                    title:'大型車聚活動',
                    img: require('@/static/image/pc/service/service6.png'),
                    des: '全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。'
                },
                {
                    id: 7,
                    title:'活動宣傳包車',
                    img: require('@/static/image/pc/service/service7.png'),
                    des: '全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。'
                },
                {
                    id: 8,
                    title:'機場接車服務',
                    img: require('@/static/image/pc/service/service8.png'),
                    des: '全新打造高規格超跑專用運輸車輛，擁有運送低底盤車型適用的全貼地式載台，並全程提供車套包覆保護，獨家專業的設備及一系列保護措施使您的愛車在運輸過程中與運輸車輛牢固的結合，保護您的愛車在運輸途中避免一切可能由於道路狀況和天氣變化所帶來的風險。'
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
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev',
                },
                pagination: {
                    el: ".swiper-pagination",
                    type: "progressbar",
                },
                on:{
                    slideChange: function() {
                        const self = this;
                        self.serviceListNum = this.activeIndex
                        console.log('self.serviceListNum', self.serviceListNum)
                        let allListTitle = document.querySelectorAll(".serviceListTitle .title");
                        allListTitle.forEach((item)=>{
                            item.style.color = '#ffffff';
                        })
                        allListTitle[this.activeIndex].style.color = '#97f540'; 
                    }
                }
            },
        }
    },
    mounted(){
        const self=this;
        //window.aboutUsAnime()
        self.serviceListTitleColor()
        this.$watch(
            () => this.$refs.zSwiper.swiper.activeIndex,
            val => {
                this.listCurrentNum = val
            }
        )
    },
    // watch:{
    //     this.$refs.zSwiper.swiper.activeIndex:{
    //         handler:
    //             function (newValue){
    //                 const self = this;
    //                 self.listCurrentNum = newValue
    //                 console.log('self.listCurrentNum', self.listCurrentNum)
    //             }
    //     } 
    // },
    methods:{
        scrollTo(className) {
            const scrollEl = document.getElementsByClassName(className)[0];
            window.scrollTo({
                top: scrollEl.offsetTop,
                behavior: "smooth"
            });
        },
        changeListNum(index){
            this.$refs.zSwiper.swiper.slideTo(index, 1000, false);
        },
        serviceListTitleColor() {
            let allListTitle = document.querySelectorAll(".serviceListTitle .title");
            allListTitle[this.serviceListNum].style.color = '#97f540'; 
            console.log(this.$refs.zSwiper.swiper.activeIndex)
        }
    }
}
</script>