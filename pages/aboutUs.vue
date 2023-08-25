<template>
    <div>
        <Header @navBarOpen="navBarOpen = true" />
        <right-side-bar />
        <div id="aboutUsPage">
            <div class="banner">
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
                        <div class="navBtnAnime"><span>公司簡介</span></div>
                        <div class="navBtnAnime"><span>員工技術技能簡介</span></div>
                        <div class="navBtnAnime"><span>法律顧問團隊</span></div>
                    </div>
                </div>
                <div class="height"></div>
            </div>
            <div class="vision">
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
                    寶輇車業為了運送特殊車輛及各是超跑而誕生的，位於台中市西屯區。<br />
                    我們了解超跑的客戶最大需求，也為您的愛車量身打造最完善的服務。<br />
                    我們的車體是獨立的空間運送，絕不讓您的愛車日曬雨淋，<br />
                    一次只能運送一輛。<br />
                    寶輇車業對於運送任務的司機師傅們有嚴格的把關要求，每一位司機皆受過<br />
                    專業的培訓課程，並要求重視對待客戶親切服務和處理態度。<br />
                    客戶放心和滿意的服務，就是我們最大的動力和目標。<br />
                    服務地區為全台灣本島
                </div>
                <div class="height"></div>
            </div>
            <div class="service">
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
                                            <div class="txt">
                                                {{ item.txt }}
                                                </div>
                                            </div>
                                            <div class="line">

                                            </div>
                                    </div>
                                </div>
                            </a>
                        </div>
                    </div>
                </div>
                <div class="height"></div>
            </div>
            <div class="ourTeam">
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
                        <div :class="`teamBtn__${index + 1}`" v-for="(item, index) in serviceTxt" :key="'teamBtn' + index" data-anime>
                            <a :href="item.url">
                                <div :class="`teamBtn__${index + 1}-anime teamBtnAnime`">
                                    <div :class="`teamBtn__${index + 1}-anime-obj`">
                                        <div class="teamTxtBg"></div>
                                        <!-- <div class="teamTxt">
                                            <div class="txt">
                                                {{ item.txt }}
                                                </div>
                                            </div>
                                            <div class="line">

                                            </div> -->
                                    </div>
                                </div>
                            </a>
                        </div>
                    </div>
                </div>
                <div class="height"></div>
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
            ]
        }
    },
}
</script>
