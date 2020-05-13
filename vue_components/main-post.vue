<template>
    <div class="main-post">
        <div class="tab-main-post">
            <a href="javascript:;" @click="tabControl('IMAGE')" ref="IMAGE" class="active">
                <i class="fa fa-picture-o" aria-hidden="true"></i>
                <span>Photo</span>
            </a>
            <a href="javascript:;" @click="tabControl('VIDEO')" ref="VIDEO">
                <i class="fa fa-play-circle-o" aria-hidden="true"></i>
                <span>Video</span>
            </a>
            <a href="javascript:;" @click="tabControl('Sticker')" ref="Sticker">
                <i class="fa fa-smile-o" aria-hidden="true"></i>
                <span>Sticker</span>
            </a>
            <a href="javascript:;" @click="tabControl('Coupon')" ref="Coupon">
                <i class="fa fa-bookmark-o" aria-hidden="true"></i>
                <span>Coupon</span>
            </a>
            <a href="javascript:;" @click="tabControl('Link')" ref="Link">
                <i class="fa fa-link" aria-hidden="true"></i>
                <span>Link</span>
            </a>
            <a href="javascript:;" @click="tabControl('Surveys')" ref="Surveys">
                <i class="fa fa-file-text-o" aria-hidden="true"></i>
                <span>Surveys</span>
            </a>
        </div>
        <div class="box-post-type">
            <image-post v-if="postType == 'IMAGE'" 
            :is-title="'Upload image'" 
            :is-show="isShow" 
            @update-status="showPopup()">
            </image-post>

            <video-post v-else-if="postType == 'VIDEO'" 
            :is-title="'Upload video'" 
            :is-show="isShow" 
            @update-status="showPopup()">
            </video-post>

            <coupon-post v-else-if="postType == 'Coupon'" 
            :is-title="'Coupon'" 
            :is-show="isShow" 
            @set-schedule2="changeSchedule1($event);"
            @update-status="showPopup()">
            </coupon-post>
        </div>
    </div>
</template>
<script>
    Vue.component('image-post',  httpVueLoader('vue_components/image-post.vue'));
    Vue.component('video-post',  httpVueLoader('vue_components/video-post.vue'));
    Vue.component('coupon-post',  httpVueLoader('vue_components/coupon-post.vue'));
    module.exports = {
        data: function() {
            return{
                postType: 'IMAGE',
                isShow: false,
                aaa: 1
            }
        },
        methods: {
            tabControl(type){
                this.postType = type;
                let elm = this.$refs[type];
                $(elm).addClass('active').siblings().removeClass('active');
                if(type == 'Coupon'){
                    this.showPopup()
                }
            },
            showPopup(){
                this.isShow = !this.isShow
            },
            changeSchedule1(val){
                this.$emit('set-schedule1', val);
            }
        }
    };
</script>