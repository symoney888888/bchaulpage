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
                            <div class="bgImg-anime">
                                <div class="bgImg-anime-obj"></div>
                            </div>
                        </div>
                        <div class="formContain">
                            <div class="formRow">
                                <div class="formTitle">客戶資訊</div>
                                <div class="formTitle">車輛資訊</div>
                            </div>
                            <div class="formRow">
                                <div class="formItem">
                                    <span>公司/姓名：</span><input v-model="formData.name" />
                                </div>
                                <div class="formItem">
                                    <span>車牌號碼：</span><input v-model="formData.car_plate_number" />
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formItem">
                                    <span>聯繫電話：</span><input v-model="formData.phone" />
                                </div>
                                <div class="formItem">
                                    <span>車輛品牌：</span><input v-model="formData.car_brand" />
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formItem">
                                    <span>電子信箱：</span><input v-model="formData.email" />
                                </div>
                                <div class="formItem">
                                    <span>車輛型號：</span><input v-model="formData.car_camry" />
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formItem">
                                    <span>地址：</span><input v-model="formData.name_address" />
                                </div>
                                <div class="formItem">
                                    <span>車輛顏色：</span><input v-model="formData.car_color" />
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formTitle">托運詳情</div>
                                <div class="formTitle"></div>
                            </div>
                            <div class="formRow">
                                <div class="formItem">
                                    <span>出發日期：</span><input v-model="formData.setout" />
                                </div>
                                <div class="formItem">
                                    <span>起運時間：</span><input v-model="formData.departure" />
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formItem">
                                    <span>起運地址：</span><input v-model="formData.departure_address" />
                                </div>
                                <div class="formItem">
                                    <span>目的地地址：</span><input v-model="formData.destination_address" />
                                </div>
                            </div>
                            <div class="formRow">
                                <div class="formItem formDesItem">
                                    <span>特殊需求或注意事項：</span><textarea v-model="formData.memo" rows="" cols=""></textarea>
                                </div>
                            </div>
                        </div>
                        <div class="submitBtn">
                            <a href="javascript:void(0);">
                                <div class="submitBtn-anime">
                                    <img :src="require('@/static/image/pc/contact/submit.png')" alt="">
                                </div>
                            </a>
                        </div>
                    </div>
                    <div class="mapArea"></div>
                </div>
            </section>
        </div>
        <Nav-bar @navBarOpen="navBarOpen = false" v-if="navBarOpen" />
    </div>
</template>
<script>
export default {
    data() {
        return {
            navBarOpen: false,
            formData:{
                name:'',
                phone:'',
                email:'',
                name_address:'',
                car_plate_number:'',
                car_brand:'',
                car_camry:'',
                car_color:'',
                setout:'',
                departure:'',
                departure_address:'',
                destination_address:'',
                memo:'',
            }
        }
    }
}
</script>
