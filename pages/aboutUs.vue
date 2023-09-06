<template>
    <div>
        <Header @navBarOpen="navBarOpen = true" />
        <right-side-bar />
        <div id="aboutUsPage">
            <section class="banner">
                <div class="bgImg">
                    <div class="bgImg-anime">
                        <div class="bgImg-anime-obj"></div>
                    </div>
                </div>
                <div class="title">
                    <div class="title-anime">
                        <div class="title-anime-obj">ABOUT US</div>
                    </div>
                </div>
                <div class="subTitle">
                    <div class="subTitle-anime">
                        <div class="subTitle-anime-obj">關於我們</div>
                    </div>
                </div>
                <div class="navBtn">
                    <div class="navBtnWrap">
                        <div class="navBtnAnime"><span @click="scrollTo('vision')">公司簡介</span></div>
                        <div class="navBtnAnime"><span @click="scrollTo('ourTeam')">員工技術技能簡介</span></div>
                        <div class="navBtnAnime"><span @click="scrollTo('legalTeam')">法律顧問團隊</span></div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="vision">
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
                <div class="des">
                    <div class="contain">
                        <div class="title">公司簡介</div>
                        <div class="desContain">
                            寶輇車業於2022年成立，源於對跑車的熱愛與對精緻汽車的珍愛之情。<br />
                            我們為您提供獨一無二的頂級透明箱型運載服務，堅守著對愛車的無微<br />
                            不至守護。透過創新的全卸斗方式，我們謹慎地處理各式超低底盤頂級<br />
                            車輛，確保在運輸過程中給予愛車最完美的呵護。<br />
                            我們的服務不僅僅是運載，更是一種愛車的守護。無論是滿足行銷需求<br />
                            的特殊配備，抑或是客戶隱私的極致保護，我們都能夠完美呈現。結合<br />
                            先進的科技定位系統，您隨時能夠了解愛車的運輸狀況，<br />
                            始終與愛車心靈相通。<br />
                            我們堅信，我們的服務能夠比您更加珍視您驕傲的愛車。寶輇車業不僅<br />
                            僅是運載的媒介，更是您愛車的信任代表，我們的驕傲源於能夠為您的<br />
                            愛車提供無與倫比的服務。讓我們攜手，為您的愛車開啟尊榮、<br />
                            安心的運載新紀元。<br />
                        </div>
                        <div class="desContain_mb">
                            寶輇車業於2022年成立，源於對跑車的熱愛與對精緻汽車的珍愛之情。我們為您提供獨一無二的頂級透明箱型運載服務，堅守著對愛車的無微不至守護。透過創新的全卸斗方式，我們謹慎地處理各式超低底盤頂級車輛，確保在運輸過程中給予愛車最完美的呵護。<br />
                            我們的服務不僅僅是運載，更是一種愛車的守護。無論是滿足行銷需求的特殊配備，抑或是客戶隱私的極致保護，我們都能夠完美呈現。結合先進的科技定位系統，您隨時能夠了解愛車的運輸狀況，始終與愛車心靈相通。我們堅信，我們的服務能夠比您更加珍視您驕傲的愛車。寶輇車業不僅僅是運載的媒介，更是您愛車的信任代表，我們的驕傲源於能夠為您的愛車提供無與倫比的服務。讓我們攜手，為您的愛車開啟尊榮、安心的運載新紀元。
                        </div>
                        <div class="title2">經營理念</div>
                        <ul>
                            <li>為頂級的客戶 提供頂級愛車的運輸服務，為我們的核心。</li>

                            <li>比您更愛護您的愛車，是我們的服務忠旨。</li>

                            <li>為服務您驕傲的愛車 是我們最大的驕傲。</li>
                        </ul>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="service">
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
                <div class="btnBox">
                    <div class="serviceBtn">
                        <div :class="`serviceBtn__${index + 1}`" v-for="(item, index) in serviceTxt" :key="'serviceBtn' + index" data-anime>
                            <a :href="item.url">
                                <div :class="`serviceBtn__${index + 1}-anime serviceBtnAnime`">
                                    <div :class="`serviceBtn__${index + 1}-anime-obj`">
                                        <div class="serviceTxtBg"></div>
                                        <div class="serviceTxt">
                                            <div class="wrap">
                                                <div class="txt">
                                                    {{ item.txt }}
                                                </div>
                                                <div class="serviceArrow">
                                                    <img :src="require('@/static/image/pc/aboutUs/serviceArrow.png')" alt="" />
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </a>
                        </div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="ourTeam">
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
                                            <p class="des" readonly>{{ item.des }}</p>
                                        </div>
                                    </div>
                                </div>
                            </swiper-slide>
                            <div class="swiper-button-prev" slot="button-prev"></div>
                            <div class="swiper-button-next" slot="button-next"></div>
                        </swiper>
                        <div class="swiper-pagination" slot="button-pagination"></div>
                    </div>
                </div>

                <div class="height"></div>
            </section>
            <section class="legalTeam">
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
                <div class="subTitle1">
                    <div class="subTitle1-anime">
                        <p class="subTitle1-anime-obj">寶輇車業專業法律顧問團隊</p>
                    </div>
                </div>
                <div class="certificate1">
                    <div class="certificate1-anime">
                        <img :src="require('@/static/image/pc/aboutUs/certificate1.png')" alt="" />
                    </div>
                </div>
                <div class="subTitle2">
                    <div class="subTitle2-anime">
                        <p class="subTitle2-anime-obj">寶輇車業專利證書</p>
                    </div>
                </div>
                <div class="certificate2">
                    <div class="certificate2-anime">
                        <img :src="require('@/static/image/pc/aboutUs/certificate2.png')" alt="" />
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
                    url: '',
                    txt: '服務案例',
                },
                {
                    url: '',
                    txt: '頂級車輛托運',
                },
                {
                    url: '',
                    txt: '專利透明車廂運載車介紹',
                },
            ],
            teamList: [
                {
                    name: '總經理-吳宗達',
                    enName: 'CEO-ZONG DA WU',
                    des: '寶輇團隊隊長，多年駕駛多款跑車經驗，了解頂級客群對於車輛託運的需求與擔心，擁有職業大貨車駕照及多次跑車運載經驗。',
                    img: require('@/static/image/pc/aboutUs/person1.png'),
                },
                {
                    name: '協理-彭彥鈞',
                    enName: 'Assistant Manager-PENG YAN JUN',
                    des: '仔細且謹慎熱情的服務精神，謹守紀律的特質，持有合格職業大貨車駕照，並擁有4年以上託運超跑運載經驗。熟悉各種頂級車輛特性與車主的需求。',
                    img: require('@/static/image/pc/aboutUs/person2.png'),
                },
                {
                    name: '運輸工程師-簡上捷',
                    enName: 'Transportation Engineer-SHANG JIE JIAN',
                    des: '個性警慎，謹守紀律的特質，持有合格職業大貨車駕照，並擁有3年以上大貨車跑車、豪車託運豐富經驗。',
                    img: require('@/static/image/pc/aboutUs/person3.png'),
                },
                {
                    name: '運輸工程師-游健勳',
                    enName: 'Transportation Engineer-YOU JIANXUN',
                    des: '個性務實，謹守紀律的特質，持有合格職業大貨車駕照，並擁有6年以上大貨車跑車、豪車託運豐富經驗。',
                    img: require('@/static/image/pc/aboutUs/person4.png'),
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
                        pagination: {
                            el: ".swiper-pagination",
                        },
                    },
                },
                navigation: {
                    nextEl: '.swiper-button-next',
                    prevEl: '.swiper-button-prev',
                },
            },
        }
    },
    mounted() {
        window.aboutUsAnime()
    },
    methods: {
        scrollTo(className) {
            const scrollEl = document.getElementsByClassName(className)[0]
            window.scrollTo({
                top: scrollEl.offsetTop,
                behavior: 'smooth',
            })
        },
    },
}
</script>
