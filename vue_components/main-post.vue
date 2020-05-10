<template>
    <div class="main-post">
        <div class="tab-main-post">
            <a href="javascript:;">
                <i class="fa fa-picture-o" aria-hidden="true"></i>
            </a>
            <a href="javascript:;">
                <i class="fa fa-play-circle-o" aria-hidden="true"></i>
            </a>
            <a href="javascript:;">
                <i class="fa fa-smile-o" aria-hidden="true"></i>
            </a>
            <a href="javascript:;">
                <i class="fa fa-bookmark-o" aria-hidden="true"></i>
            </a>
            <a href="javascript:;">
                <i class="fa fa-link" aria-hidden="true"></i>
            </a>
            <a href="javascript:;">
                <i class="fa fa-file-text-o" aria-hidden="true"></i>
            </a>
        </div>
        <div class="box-post-type">
            
        </div>
    </div>
</template>
<script>
    Vue.component('tab-main-post',  httpVueLoader('vue_components/tab-main-post.vue'));
    module.exports = {
        data: function() {
            return{

            }
        },
    };
</script>