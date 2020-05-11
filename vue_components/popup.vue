<template>
    <div class="popup">
        <div class="wrap-content">
            <div class="head">
                <h5 class="title">
                    {{titleHead}}
                </h5>
                <a href="javascript:;" class="close"></a>
            </div>
            <div class="popup-content">
                <slot></slot>
            </div>
            <div class="text-center bottom">
                <a href="javascript:;" class="btn-cancel" v-if="btnBottom == 0">
                    Cancel
                </a>
                <a href="javascript:;" class="btn-share" v-else>
                    Share
                </a>
            </div>
        </div>
    </div>
</template>
<script>
    module.exports = {
        data: function() {
            return{
                btnBottom: 0,
                titleHead: 'Upload Photo'
            }
        },
    };
</script>