<template>
    <div class="coupon-post">
        <div class="list-select" v-if="isSelect != null">
            <ul class="list-coupon">
                <li class="d-flex align-items-center">
                    <span class="img">
                        <img v-bind:src="isSelect.thumbnail" alt="">
                    </span>
                    <div class="content">
                        <span class="name">
                            {{isSelect.title}}
                        </span>
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
                <li class="d-flex align-items-center" v-for="(item, index) in Coupon" :key="index">
                    <span class="img">
                        <img v-bind:src="item.thumbnail" alt="">
                    </span>
                    <div class="content">
                        <a href="#" class="link">
                            {{item.title}}
                        </a>
                        <span class="name">Test</span>
                        <p class="time">
                            validity period 02/12/2019 00:00 ~ 08/07/2019 23:59
                        </p>
                    </div>
                    <a href="javascript:;" class="select" @click="selectCoupon(index)">
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
                isSelect: null,
                Coupon: [
                    {
                        id: 1,
                        startDate: 1468959781804,
                        endDate: 1468959781804,
                        // status: Status
                        title: "test 1",
                        thumbnail: 'https://via.placeholder.com/300/333'
                    },
                    {
                        id: 2,
                        startDate: 1468959781804,
                        endDate: 1468959781804,
                        // status: Status
                        title: "test 2",
                        thumbnail: 'https://via.placeholder.com/300/ccc'
                    },
                    {
                        id: 3,
                        startDate: 1468959781804,
                        endDate: 1468959781804,
                        // status: Status
                        title: "test 3",
                        thumbnail: 'https://via.placeholder.com/300/ff0'
                    }
                ]
            }
        },
        methods: {
            showPopup(){
                this.$emit('update-status');
            },
            selectCoupon(id){
                this.showPopup();
                this.$emit('set-schedule2');
                this.isSelect = this.Coupon[id]
            }
        },
    };
</script>