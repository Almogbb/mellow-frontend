<template>
    <section class="attachment-preview cmp-preview">
        <div class="cmp-header">
      <!-- <p class="cmp-container-title"></p> -->
      <a class="close-cmp-btn" @click="closeCmp">
        <span></span>
      </a>
    </div>
    <!-- <hr class="thin-hr" /> -->
        <label>
            <input type="file" @change="onAttachImg" hidden />
            <p class="attach-from">Attach from...</p>
            <hr class="thin-hr" />
            <div class="pointer">Computer</div>
        </label>
        <!-- <div>LOADING...</div> -->

        <hr class="thin-hr" />

        <div class="attach-link-title">Attach a link</div>
        <input
            v-focus
            v-model="input"
            class="attach-input"
            type="text"
            placeholder="Paste any link here..."
        />
        <button class="attach-link-btn" @click="showLink">Attach</button>
        <div class="attach-preview">
            <!-- <p>{{ imgUrls }}</p> -->
            <!-- <img v-for="imgUrl in imgUrls" :key="imgUrl" :src="imgUrl" /> -->
        </div>
    </section>
</template>

<script>
export default {
    props: {
        imgUrls: Array
    },
    components: {},
    data() {
        return {
            isLoading: false,
            input: null,
        }
    },
    created() { },
    methods: {
        onAttachImg(ev) {
            //how do i use the async await here???
            // cant see loading
            this.isLoading = true
            this.$emit('attachImg', ev)
            this.isLoading = false
        },
        showLink() {
            console.log(this.input);
            console.log('not working till we fix img upload on second time');
        },
        closeCmp() {
            this.$emit("closeCmp");
        }
    },
    computed: {},
    unmounted() { },

}
</script>

<style>
</style>