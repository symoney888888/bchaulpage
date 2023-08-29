<template>
    <div>
        <Header @navBarOpen="navBarOpen = true" />
        <right-side-bar />
        <div id="modelPage">
            <div class="modelContain">
                <div class="bgIcon">
                    <div :class="`bgIcon__${index + 1}`" v-for="(item, index) in 6" :key="'bgIcon' + index" data-anime>
                        <div :class="`bgIcon__${index + 1}-anime bgIconAnime`">
                            <div :class="`bgIcon__${index + 1}-anime-obj`"></div>
                        </div>
                    </div>
                </div>
                <div class="title">
                    <div class="title-anime">
                        <div class="title-anime-obj">MODEL</div>
                    </div>
                </div>
                <div class="subTitle">
                    <div class="subTitle-anime">
                        <div class="subTitle-anime-obj">車種介紹</div>
                    </div>
                </div>
                <div class="des">
                    <div class="desWrap">
                        <div class="desImg">
                            <img :src="require('@/static/image/pc/model/modelDesImg.png')" alt="" />
                        </div>
                        <div class="desText">
                            <div class="desTitle">{{ modelDesData.title }}</div>
                            <ul class="desTxt">
                                <li v-for="(item, index) in modelDesData.txt" :key="index">
                                    {{ item.des }}
                                </li>
                            </ul>
                            <!-- <textarea class="desTxt" v-model="modelDesData.txt" readonly></textarea> -->
                        </div>
                    </div>
                </div>
                <div class="height"></div>
            </div>
            <div class="modelSlider">
                <div class="modelListWrap">
                    <swiper class="swiper" :options="swiperOption">
                        <swiper-slide :class="`modelList__${index + 1} modelListBox`" v-for="(item, index) in modelList" :key="'newsList' + index" data-anime>
                            <div :class="`modelList__${index + 1}-anime modelListAnime`">
                                <div class="modelTxt">
                                    <div class="modelTxtWrap">
                                        <p class="title">寶輇車業-託運輸車型介紹</p>
                                        <p class="subTitle">{{ item.title }}</p>
                                        <textarea class="des" v-model="item.des" readonly></textarea>
                                    </div>
                                </div>
                                <div class="modelImg">
                                    <img :src="item.image" />
                                </div>
                            </div>
                        </swiper-slide>
                        <div class="swiper-button-prev" slot="button-prev"></div>
                        <div class="swiper-button-next" slot="button-next"></div>
                    </swiper>
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
            navBarOpen: false,
            modelDesData: {
                title: '寶輇車業車種優勢',
                txt: [
                    {
                        des:"【全新打造】：2023年全新打造，專為頂級車輛所設計，堅持專利高級車款。"
                    },
                    {
                        des:"【全面車廂式託運】：無論風雨或異物，全面車廂式託運，確保愛車安全無虞。"
                    },
                    {
                        des:"【機密託運】：專為未上市新車、高貴的客戶低調的您打造的機密託運服務，保護車輛隱私。"
                    },
                    {
                        des:"【透明車廂】：根據客戶需求，提供透明車廂，讓愛車展示自信，同時車牌得以隱匿。"
                    },
                    {
                        des:"【車廂行銷】：利用託運過程，打造行銷平台，廣告品牌或傳遞最新資訊。"
                    }
                ],
            },
            modelList: [
                {
                    title: '11噸箱型單載託運車',
                    des: '載重11噸，為單輛車託運而設。保護車輛不受外界影響，確保安全運輸。',
                    image: require('@/static/image/pc/model/model1.png'),
                },
                {
                    title: '17噸箱型雙載託運車',
                    des: '載重17噸，可同時託運兩輛車輛。高效解決方案，為多輛車提供安全便捷的運輸。',
                    image: require('@/static/image/pc/model/model2.png'),
                },
                {
                    title: '26噸箱型4載託運車',
                    des: '載重26噸，適合同時託運四輛車輛。卓越運輸能力，確保多車同時達到目的地，安全無虞。',
                    image: require('@/static/image/pc/model/model3.png'),
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
    mounted() {
        window.modelPageAnime()
    },
}
</script>
