<template>
    <div class="coupon-post">
        <div class="list-select" v-if="selected == true">
            <ul class="list-coupon">
                <li class="d-flex align-items-center">
                    <span class="img">
                        <img src="https://via.placeholder.com/300" alt="">
                    </span>
                    <div class="content">
                        <span class="name">Test</span>
                        <p class="time">
                            validity period 02/12/2019 00:00 ~ 08/07/2019 23:59
                        </p>
                    </div>
                    <a href="javascript:;" class="close"></a>
                </li>
            </ul>
        </div>
        <popup :is-title="isTitle" :is-show="isShow" @update-status="showPopup()">
            <p class="sub">Per-valid and valid coupons are listed</p>
            <ul class="list-coupon">
                <li class="d-flex align-items-center">
                    <span class="img">
                        <img src="https://via.placeholder.com/300" alt="">
                    </span>
                    <div class="content">
                        <a href="#" class="link">
                            Valid
                        </a>
                        <span class="name">Test</span>
                        <p class="time">
                            validity period 02/12/2019 00:00 ~ 08/07/2019 23:59
                        </p>
                    </div>
                    <a href="javascript:;" class="select" @click="selectCoupon()">
                        Select
                    </a>
                </li>
                <li class="d-flex align-items-center">
                    <span class="img">
                        <img src="https://via.placeholder.com/300" alt="">
                    </span>
                    <div class="content">
                        <a href="#" class="link">
                            Valid
                        </a>
                        <span class="name">Test</span>
                        <p class="time">
                            validity period 02/12/2019 00:00 ~ 08/07/2019 23:59
                        </p>
                    </div>
                    <a href="javascript:;" class="select" @click="selectCoupon()">
                        Select
                    </a>
                </li>
            </ul>
        </popup>
    </div>
</template>
<script>
    Vue.component('popup',  httpVueLoader('vue_components/popup.vue'));
    module.exports = {
        props: ['isTitle', 'isShow'],
        data() {
            return {
                selected: false,
            }
        },
        methods: {
            showPopup(){
                this.$emit('update-status');
            },
            selectCoupon(){
                this.selected = true;
                this.showPopup();
                this.$emit('set-schedule2');
            }
        },
    };
</script>