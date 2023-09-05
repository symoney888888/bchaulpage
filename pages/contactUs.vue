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
                        <form class="formContain">
                            <div class="formRow">
                                <div class="formTitle">客戶資訊</div>
                                <div class="formTitle">車輛資訊</div>
                            </div>
                            <div class="formRow">
                                <div class="formItem"><span>公司/姓名：</span><input v-model="formData.name" type="text" maxlength="8" required="required" /></div>
                                <div class="formItem"><span>車牌號碼：</span><input v-model="formData.car_plate_number" /></div>
                            </div>
                            <div class="formRow">
                                <div class="formItem"><span>聯繫電話：</span><input v-model="formData.phone" type="tel"  required="required" /></div>
                                <div class="formItem">
                                    <span>車輛品牌：</span>
                                    <select name="brand" class="brand" v-model="formData.car_brand">
                                        <option value=""><label>- Select -</label></option>
                                        <option v-for="(item, index) in car_brandList" :key="index" :value="item">{{ item }}</option>
                                    </select>
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formItem"><span>電子信箱：</span><input type="email" pattern=".+@globex\.com"  v-model="formData.email" /></div>
                                <div class="formItem">
                                    <span>車輛型號：</span><input v-model="formData.car_camry" />
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formItem"><span>地址：</span><input v-model="formData.name_address"  type="text" /></div>
                                <div class="formItem">
                                    <span>車輛顏色：</span>
                                    <select name="color" class="color" v-model="formData.car_color">
                                        <option value=""><label>- Select -</label></option>
                                        <option v-for="(item, index) in car_color" :key="index" :value="item">{{ item }}</option>
                                    </select>
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formTitle">托運詳情</div>
                                <div class="formTitle"></div>
                            </div>
                            <div class="formRow">
                                <div class="formItem"><span>出發日期：</span><input type="date" v-model="formData.setout" /></div>
                                <div class="formItem"><span>起運時間：</span><input type="time" v-model="formData.departure" /></div>
                            </div>
                            <div class="formRow">
                                <div class="formItem"><span>起運地址：</span><input  type="text" v-model="formData.departure_address" /></div>
                                <div class="formItem"><span>目的地地址：</span><input  type="text" v-model="formData.destination_address" /></div>
                            </div>
                            <div class="formRow">
                                <div class="formItem formDesItem"><span>特殊需求或注意事項：</span><textarea v-model="formData.memo" rows="" cols=""></textarea></div>
                            </div>
                            <div class="submitBtn">
                                <input class="submitBtn-anime" type="submit" value="" @click="sendForm()" />
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
        </div>
        <Nav-bar @navBarOpen="navBarOpen = false" v-if="navBarOpen" />
    </div>
</template>
<script>
import axios from 'axios';
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
            car_brandList: [
                'MCLAREN- 麥卡倫',
                'BUGATTI- 布加迪',
                'PAGANI- 帕加尼',
                'ROLLYROYCE- 勞斯萊斯',
                'FERRARI- 法拉利',
                'MASERATI- 瑪莎拉蒂',
                'LAMBORGHINI- 藍寶堅尼',
                'BENTLEY- 賓利',
                'PORSCHE- 保時捷',
                'ASTONMARTIN- 阿斯頓馬丁',
                'M-BENZ- 賓士',
                'BMW- 寶馬',
                'KOENIGSEGG- 科尼賽克',
                'JAGUAR- 捷豹',
                'LOTUS- 蓮花',
                'LEXUS- 凌志',
                'AUDI- 奧迪',
                'CORVETTE- 克爾維特',
                'SPYKER- 世爵',
                'TESLA-特斯拉',
                'Others-其他品牌',
            ],
            car_camryList: ['單門', '雙門', '三門', '四門', '五門'],
            car_color: ['紅', '橙', '黃', '綠', '藍', '紫', '黑', '白', '灰', '其他'],
        }
    },
    methods: {
        async getRecaptchaToken() {
            await this.$recaptchaLoaded();
            const token = await this.$recaptcha('contactUs');
                return token;
        },
        sendForm() {
            const self = this
            if(self.getRecaptchaToken()){
                const sendData = axios
                .post('https://bchaul.aeff.xyz/api/car.Reservation/add', self.formData, { header: { 'Content-Type': 'application/json','Access-Control-Allow-Origin': '*' } })
                .then(function (response) {
                    console.log(response)
                    alert('表單提交成功!')
                })
                .catch(function (error) {
                    console.log('錯誤', error)
                    alert('表單提交失敗 請稍後再試!')
                })
                console.log(sendData)
                
            }
        },
    },
}
</script>
