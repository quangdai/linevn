<template>
    <div class="video-post">
        <div class="wrap-box-img" @click="showPopup()">
            <span>{{isTitle}}</span>
            <img src="images/ic_video.png" alt="">
        </div>
        <p>Recommended formats: MP4, M4V, MOV, AVI, WMV</p>
        <p>File size: Up to 200 MB</p>
        <p>Duration: Up to 5 minutes</p>
        <popup :is-title="isTitle" :is-show="isShow" @update-status="showPopup()">
            <div class="popup-content-img">
                <span class="title">
                    Drop your video here or
                </span>
                <button>
                    <span>Browse</span>
                    <i class="fa fa-plus-square-o" aria-hidden="true"></i>
                </button>
            </div>
            <p>Recommended formats: MP4, M4V, MOV, AVI, WMV</p>
            <p>File size: Up to 200 MB</p>
            <p>Duration: Up to 5 minutes</p>
        </popup>
    </div>
</template>
<script>
    Vue.component('popup',  httpVueLoader('vue_components/popup.vue'));
    module.exports = {
        props: ['isTitle', 'isShow'],
        methods: {
            showPopup(){
                this.$emit('update-status');
            }
        },
    };
</script>