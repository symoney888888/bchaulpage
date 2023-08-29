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
            <!-- <section class="ourTeam">
                <div class="bgIcon">
                    <div :class="`bgIcon__${index + 1}`" v-for="(item, index) in 2" :key="'bgIcon' + index" data-anime>
                        <div :class="`bgIcon__${index + 1}-anime bgIconAnime`">
                            <div :class="`bgIcon__${index + 1}-anime-obj`"></div>
                        </div>
                    </div>
                </div>
                <div class="title">
                    <div class="title-anime">
                        <div class="title-anime-obj"></div>
                    </div>
                </div>
                <div class="teamBox">
                    <div class="teamBtn">
                        <swiper class="swiper" :options="swiperOption">
                            <swiper-slide :class="`teamBtn__${index + 1}`" v-for="(item, index) in teamList" :key="'teamBtn' + index" data-anime>
                                <div :class="`teamBtn__${index + 1}-anime modelListAnime`">
                                    <div class="teamBtnImg">
                                        <img :src="item.img" />
                                    </div>
                                    <div class="teamBtnTxt">
                                        <div class="teamBtnTxtWrap">
                                            <p class="name">{{ item.name }}</p>
                                            <p class="enName">{{ item.enName }}</p>
                                            <p class="des" readonly> {{ item.des }}</p>
                                        </div>
                                    </div>
                                    
                                </div>
                            </swiper-slide>
                            <div class="swiper-button-prev" slot="button-prev"></div>
                            <div class="swiper-button-next" slot="button-next"></div>
                        </swiper>
                    </div>
                </div>
                <div class="height"></div>
            </section> -->
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
            navBarOpen: false,
            aboutUsNavBtnList: ['公司簡介', '員工技術技能簡介', '法律顧問團隊'],
            serviceTxt: [
                {
                    url:'',
                    txt:'實際案例'
                },
                {
                    url:'',
                    txt:'超跑拖吊'
                },
                {
                    url:'',
                    txt:'車種介紹'
                }
            ],
            teamList:[
                {
                    name: '總經理 -吳宗達',
                    enName: 'CEO-ZONG DA WU',
                    des: '寶輇團隊隊長，多年駕駛多款跑車經驗，了解頂級客群對於車輛託運的需求與擔心，擁有職業大貨車駕照及多次跑車運載經驗。',
                    img: require('@/static/image/pc/aboutUs/person1.png')
                },
                {
                    name: '協理-彭彥鈞',
                    enName: 'Assistant Manager-PENG YAN JUN',
                    des: '仔細且謹慎熱情的服務精神，謹守紀律的特質，持有合格職業大貨車駕照，並擁有4年以上託運超跑運載經驗。熟悉各種頂級車輛特性與車主的需求。',
                    img: require('@/static/image/pc/aboutUs/person2.png')
                },
                {
                    name: '運輸工程師-簡上捷',
                    enName: 'Transportation Engineer- SHANG JIE JIAN',
                    des: '個性警慎，謹守紀律的特質，持有合格職業大貨車駕照，並擁有3年以上大貨車跑車、豪車託運豐富經驗。',
                    img: require('@/static/image/pc/aboutUs/person3.png')
                },
                {
                    name: '運輸工程師-游健勳',
                    enName: 'Transportation Engineer- YOU JIANXUN',
                    des: '個性務實，謹守紀律的特質，持有合格職業大貨車駕照，並擁有6年以上大貨車跑車、豪車託運豐富經驗。',
                    img: require('@/static/image/pc/aboutUs/person4.png')
                },
            ],
            swiperOption: {
                autoplay: 2000,
                // speed: 300,
                loop: true,
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
            },
        }
    },
    // mounted(){
    //     window.aboutUsAnime()
    // },
    // methods:{
    //     scrollTo(className) {
    //         const scrollEl = document.getElementsByClassName(className)[0];
    //         window.scrollTo({
    //             top: scrollEl.offsetTop,
    //             behavior: "smooth"
    //         });
    //     }
    // }
}
</script>