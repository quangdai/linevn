<template>
    <div class="post-head">
        <h5 class="title">Timeline post</h5>
        <div class="btn-gr">
            <button class="btn-draft" :disabled="isActive == 0">
                Save draft
            </button>
            <button class="btn-schedule" :disabled="isActive == 0">
                Schedule
            </button>
        </div>
    </div>
</template>
<script>
module.exports = {
    data: function () {
        return {
            
        }
    },
    methods: {

    },
    props: ['isActive']
}
</script>