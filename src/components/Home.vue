<template>
    <div class="presentationList-wrap">
        <h1 class="bold-text presentation-header">Master templates</h1>
        <div class="title-wrap">
            <div class="element-wrap med-width">Cover</div>
            <div class="element-wrap lg-width">Event Name</div>
            <div class="element-wrap">Date added</div>
            <div class="element-wrap">Total size</div>
            <div class="element-wrap">Specs</div>
        </div>

        <div class="presentationList">
            <ul>
                <li  :key="item.name"  v-for="item in items">
                    <presentationList
                        :thumbnail="item.thumbnail"
                        :name="item.name"
                        :date="item.date"
                        :size="item.size"

                         v-for="newElement in item.info" :key="newElement"

                         :sessionNumber="newElement.session"
                         :numberofSlides="newElement.slides"
                         :sessionRuntime="newElement.runtime"
                         :fileSize="newElement.fileSize"
                        />
                </li>
            </ul>
        </div>
    </div>



    
</template>


<script>

import presentationList from '@/components/PresentationList.vue'
import jonFile from './json/data.json'

export default {
    name:'MainPage',
    components: {
        presentationList
    },
    data(){
        return{
            items: jonFile
        }
    }
    // computed: {
    // filteredArray() {
    //   return items.map(x => {
    //       console.log(x)
    //       return items[x].info.filter(obj => {
    //           obj.session === sessionNumber
    //           obj.slides === numberofSlides
    //           obj.runtime === sessionRuntime
    //           obj.fileSize === fileSize

    //       });
    //     })
    // },
    // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

    ul {
        list-style: none;
    }
    .bold-text {
        font-weight: bold;
    }

    .presentationList-wrap {
        width: 82%;
        margin: auto;
    }

    .presentation-header {
        margin: 74px 0px 44px;
    }

    .presentationList,
    .presentationList ul,
    .presentationList ul li {
        width: 100%;
    }
    .presentationList ul {
        border-bottom: 1px solid #D1D1D1;
    }

    .title-wrap {
        width: 100%;
        display: flex;
        border-bottom: 1px solid #D1D1D1;
    }

    .title-width {
        width: 300px;
        text-align: left;
    }

    .med-width {
        width: 165px;
    }

    .lg-width {
        width: 562px;
    }


</style>