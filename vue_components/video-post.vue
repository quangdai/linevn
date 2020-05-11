<template>
    <div class="image-post">
        <div class="wrap-box-img">
            <span>Upload photo</span>
            <img src="images/ic_img.png" alt="">
        </div>
        <p>Formats: JPG, JPEG, PNG</p>
        <p>File size: Up to 10 MB</p>
        <popup>
            video
        </popup>
    </div>
</template>
<script>
    Vue.component('popup',  httpVueLoader('vue_components/popup.vue'));
</script>