<template>
    <div class="image-post">
        <div class="wrap-box-img" @click="showPopup()">
            <span>{{isTitle}}</span>
            <img src="images/ic_img.png" alt="">
        </div>
        <p>Formats: JPG, JPEG, PNG</p>
        <p>File size: Up to 10 MB</p>
        <popup :is-title="isTitle" :is-show="isShow" @update-status="showPopup()">
            <div class="popup-content-img">
                <span class="title">
                    Drop your image here or
                </span>
                <button>
                    <span>Browse</span>
                    <i class="fa fa-plus-square-o" aria-hidden="true"></i>
                </button>
            </div>
            <p>Formats: JPG, JPEG, PNG</p>
            <p>File size: Up to 10 MB</p>
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