<template>
    <div>
        <Header @navBarOpen="navBarOpen = true" />
        <right-side-bar />
        <div id="contactPage">
            <section class="banner">
                <div class="bgImg">
                    <div class="bgImg-anime">
                        <div class="bgImg-anime-obj"></div>
                    </div>
                </div>
                <div class="title">
                    <div class="title-anime">
                        <div class="title-anime-obj">CONTACT US</div>
                    </div>
                </div>
                <div class="subTitle">
                    <div class="subTitle-anime">
                        <div class="subTitle-anime-obj">聯絡我們</div>
                    </div>
                </div>
                <div class="height"></div>
            </section>
            <section class="form">
                <div class="wrap">
                    <div class="formArea">
                        <div class="bgImg">
                            <img :src="require('@/static/image/pc/contact/contactFormTitle.png')" alt="" />
                        </div>
                        <div class="titleLine">
                            <hr class="greenLine" />
                            <hr class="grayLine" />
                        </div>
                        <form class="formContain" @submit.prevent="sendForm" >
                            <div class="formTop">
                                <div class="leftPart">
                                    <div class="formTitle">客戶資訊</div>
                                    <div class="formItem required"><span>公司/姓名：</span><input v-model="formData.name" type="text" maxlength="8" required="required" /></div>
                                    <div class="formItem required"><span>聯繫電話：</span><input v-model="formData.phone" type="tel" required="required" /></div>
                                    <div class="formItem"><span>電子信箱：</span><input type="email" pattern="[^@\s]+@[^@\s]+\.[^@\s]+" v-model="formData.email" required="required" /></div>
                                    <div class="formItem"><span>地址：</span><input v-model="formData.name_address" type="text" required="required" /></div>
                                </div>
                                <div class="rightPart">
                                    <div class="formTitle">車輛資訊</div>
                                    <div class="formItem"><span>車牌號碼：</span><input v-model="formData.car_plate_number" required="required" /></div>
                                    <div class="formItem">
                                        <span>車輛品牌：</span>
                                        <select name="brand" class="brand" v-model="formData.car_brand" required="required">
                                            <option value=""><label>- Select -</label></option>
                                            <option v-for="(item, index) in car_brandList" :key="index" :value="item">{{ item }}</option>
                                        </select>
                                    </div>
                                    <div class="formItem"><span>車輛型號：</span><input v-model="formData.car_camry" required="required" /></div>
                                    <div class="formItem">
                                        <span>車輛顏色：</span>
                                        <select name="color" class="color" v-model="formData.car_color" required="required">
                                            <option value=""><label>- Select -</label></option>
                                            <option v-for="(item, index) in car_color" :key="index" :value="item">{{ item }}</option>
                                        </select>
                                    </div>
                                </div>
                            </div>
                            <div class="formTitle">托運詳情</div>
                            <div class="formBottom">
                                <div class="leftPart">
                                    <div class="formItem"><span>出發日期：</span><input type="date" v-model="formData.setout" required="required" /></div>
                                    <div class="formItem"><span>起運地址：</span><input type="text" v-model="formData.departure_address" required="required" /></div>
                                </div>
                                <div class="rightPart">
                                    <div class="formItem"><span>起運時間：</span><input type="time" v-model="formData.departure" required="required" /></div>
                                    <div class="formItem"><span>目的地地址：</span><input type="text" v-model="formData.destination_address" required="required" /></div>
                                </div>
                            </div>
                            <div class="formItem formDesItem"><span>特殊需求或注意事項：</span><textarea v-model="formData.memo" rows="" cols=""  required="required"></textarea></div>
                            <div class="submitBtn">
                                <button  class="submitBtn-anime" type="submit" value="" ></button>
                            </div>
                        </form>
                    </div>
                    <div class="mapArea">
                        <div class="map">
                            <iframe
                                src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3639.3104188110833!2d120.65574919999999!3d24.1959055!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3469164f49050db3%3A0x53f4dab95afd0981!2zNDA35Y-w5Lit5biC6KW_5bGv5Y2A6buO5piO6Lev5LiJ5q61MTIwMuiZnw!5e0!3m2!1szh-TW!2stw!4v1693881202795!5m2!1szh-TW!2stw"
                                style="border: 0"
                                allowfullscreen=""
                                loading="lazy"
                                referrerpolicy="no-referrer-when-downgrade"
                            ></iframe>
                        </div>
                        <div class="info">
                            <div class="title">
                                <img :src="require('@/static/image/pc/main/bc-haul-png.png')" alt="" />
                            </div>
                            <div class="detailBox">
                                <div class="address detial"><span class="icon">A | </span><span class="des">台中市西屯區黎明路三段1202號</span></div>
                                <div class="phone1 detial"><span class="icon">T | </span><span class="des">04-24267999</span></div>
                                <div class="phone2 detial"><span class="icon">T | </span><span class="des">0800-234-222</span></div>
                            </div>
                            <div class="qrBox">
                                <div class="desArea">
                                    <p>週一至週五 08:00-20:00</p>
                                    <p>週六.日 | 國定假日 公休</p>
                                </div>
                                <div class="qrArea">
                                    <img :src="require('@/static/image/pc/contact/lineQRCode.png')" alt="" />
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            <div class="social footerBox">
                <div class="title">社群連結</div>
                <div class="hr"></div>
                <div class="socialBtnBox">
                    <a href="https://www.instagram.com/bc_haul/" target="_blank">
                        <div class="igBtn icon">
                            <!-- <img :src="require('@/static/image/pc/main/ig-icon1.png')" alt="" /> -->
                        </div>
                    </a>
                    <a href="https://www.facebook.com/bchaul.tw/" target="_blank">
                        <div class="fbBtn icon">
                            <!-- <img :src="require('@/static/image/pc/main/facebook-icon1.png')" alt="" /> -->
                        </div>
                    </a>
                    <a href="https://www.tiktok.com/@bc_haul" target="_blank">
                        <div class="tiktokBtn icon">
                            <!-- <img :src="require('@/static/image/pc/main/tik-tok-icon1.png')" alt="" /> -->
                        </div>
                    </a>
                    <a href="https://line.me/R/ti/p/@bc_haul" target="_blank">
                        <div class="lineBtn icon">
                            <!-- <img :src="require('@/static/image/pc/main/line-copy.png')" alt="" /> -->
                        </div>
                    </a>
                </div>
            </div>
        </div>
        <Nav-bar @navBarOpen="navBarOpen = false" v-if="navBarOpen" />
    </div>
</template>
<script>
import formTxt from '~/assets/json/contactPageData/formTxtList.json'
import axios from 'axios'
export default {
    data() {
        return {
            navBarOpen: false,
            formData: {
                name: '',
                phone: '',
                email: '',
                name_address: '',
                car_plate_number: '',
                car_brand: '',
                car_camry: '',
                car_color: '',
                setout: '',
                departure: '',
                departure_address: '',
                destination_address: '',
                memo: '',
            },
            car_brandList: formTxt.car_brandList,
            car_color: formTxt.car_color,
        }
    },
    mounted(){
        window.contactAnime()
    },
    methods: {
        async getRecaptchaToken() {
            await this.$recaptchaLoaded()
            const token = await this.$recaptcha('contactUs')
            return token
        },
        sendForm() {
            const self = this
            const form = new FormData();
            for ( var key in self.formData ) {
                form.append(key, self.formData[key]);
            }
            if (self.getRecaptchaToken()) {
                const sendData = axios
                    // .post('https://bchaul.aeff.xyz/api/car.Reservation/add', form, {
                    //     header: { 'Content-Type': 'multipart/form-data', 'Access-Control-Allow-Origin': '*' },
                    // })
                    .post('https://bchaul.aeff.xyz/api/car.Reservation/add', form)
                    .then(function (response) {
                        console.log(response)
                        alert('表單提交成功!')
                    })
                    .catch(function (error) {
                        console.log('錯誤', error)
                        if (self.formData.name && self.formData.phone) {
                            alert('表單提交失敗 請稍後再試!')
                        }
                    })
                console.log(sendData)
            }
        },
    },
}
</script>
