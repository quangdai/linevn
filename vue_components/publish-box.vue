<template>
    <div class="publish-box">
        <div class="col-left">
            <span class="title">Publish date</span>
        </div>
        <div class="col-right">
            <div class="check-now" ref="publish_now" @click="radioClick('publish_now')">
                <p class="radio-item">
                    <input type="radio" name="publish-date" checked />
                    <span class="icon-check"></span>
                </p>
                <span>Publish now</span>
            </div>
            <div class="check-now" ref="publish_setdate" @click="radioClick('publish_setdate')">
                <p class="radio-item">
                    <input type="radio" name="publish-date" />
                    <span class="icon-check"></span>
                </p>
                <div class="box-set-time">
                    <input type="text" class="js-date" placeholder="DD/MM/YY">
                    <input type="text" class="js-time form-control" placeholder="DD/MM/YY">
                </div>
                <span class="time-zone">
                    GTM +7:00
                </span>
            </div>
        </div>
    </div>
</template>

<script>
    module.exports = {
        data: function() {
            return{
                format: 'D/d/m/Y',
                altFormat: 'd/m/Y',
            }
        },
        methods: {
            run_flatpickr: function() {
                var date = flatpickr(".js-date", {
                    altFormat: this.altFormat,
                    dateFormat: this.format,
                    altInput: true,
                    showMonths: 1,
                    minDate: "today"
                });
                var time = flatpickr(".js-time", {
                    enableTime: true,
                    noCalendar: true,
                    dateFormat: "H:i",
                    defaultDate: "00:00"
                });
            },
            radioClick(position){
                let elem = this.$refs[position];
                $(elem).find('input').click();
            }
        },
        mounted: function() {
            this.run_flatpickr();
        }
    };
</script>