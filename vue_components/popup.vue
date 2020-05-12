<template>
    <div class="popup" v-if="isShow == true">
        <div class="wrap-content">
            <div class="head">
                <h5 class="title">
                    {{isTitle}}
                </h5>
                <a href="javascript:;" class="close" @click="closePopup()"></a>
            </div>
            <div class="popup-content">
                <slot></slot>
            </div>
            <div class="text-center bottom">
                <a href="javascript:;" class="btn-cancel" v-if="btnBottom == 0"  @click="closePopup()">
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
                titleHead: 'Upload Photo',
            }
        },
        props: ['isTitle', 'isShow'],
        methods: {
            closePopup(){
                this.$emit('update-status');
            }
        },
    };
</script>