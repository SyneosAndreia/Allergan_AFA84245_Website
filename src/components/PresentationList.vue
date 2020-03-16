<template>
    <div class="presentation-wrap">
        <img class="element-wrap" :src="require(`../assets/img/${thumbnail}`)" alt="">
        <p class="element-wrap">{{name}}</p>
        <p class="element-wrap">{{date}}</p>
        <p class="element-wrap">{{size}}</p>
        <div class="element-wrap">
            <a href="#">
                <img src="../assets/img/download.png" alt="">   
            </a>
        </div>
        <div class="element-wrap">
            <button type="button"  class="btn btn-modal" @click="showModal"></button>

            <modal 
            v-show="isModalVisible" 
            @close="closeModal" 
            :modalHeader="name"
            :sessionNumber="sessionNumber"
            :numberofSlides="numberofSlides"
            :sessionRuntime="sessionRuntime"
            :fileSize="fileSize"/>
        </div>
    </div>
</template>

<script>
import modal from '@/components/modal.vue';
 
export default {
    name:'PresentationList',
    components: {
        modal,
    },
    props: ['thumbnail', 'name', 'date', 'size', 'sessionNumber', 'numberofSlides', 'sessionRuntime', 'fileSize'],
    data () {
      return {
        isModalVisible: false,
      };
    },
    methods: {
      showModal() {
        this.isModalVisible = true;
      },
      closeModal() {
        this.isModalVisible = false;
      }
    },
}
</script>

<style>
    .presentation-wrap {
        display: flex;
        flex: row;
    }
</style>

