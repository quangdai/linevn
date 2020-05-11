<template>
    <div class="main-post">
        <div class="tab-main-post">
            <a href="javascript:;">
                <i class="fa fa-picture-o" aria-hidden="true"></i>
                <span>Photo</span>
            </a>
            <a href="javascript:;">
                <i class="fa fa-play-circle-o" aria-hidden="true"></i>
                <span>Video</span>
            </a>
            <a href="javascript:;">
                <i class="fa fa-smile-o" aria-hidden="true"></i>
                <span>Sticker</span>
            </a>
            <a href="javascript:;">
                <i class="fa fa-bookmark-o" aria-hidden="true"></i>
                <span>Coupon</span>
            </a>
            <a href="javascript:;">
                <i class="fa fa-link" aria-hidden="true"></i>
                <span>Link</span>
            </a>
            <a href="javascript:;">
                <i class="fa fa-file-text-o" aria-hidden="true"></i>
                <span>Surveys</span>
            </a>
        </div>
        <div class="box-post-type">
            <image-post></image-post>
        </div>
    </div>
</template>
<script>
    Vue.component('image-post',  httpVueLoader('vue_components/image-post.vue'));
    module.exports = {
        data: function() {
            return{
                
            }
        },
    };
</script>