<template>
  <div class="modal-backdrop">
    <div class="modal">
      <header class="modal-header">
        <slot name="header">
          <h1 class="header-txt">{{modalHeader}}</h1>
          <button type="button" class="btn-close" @click="close"> &times; </button>
        </slot>
      </header>
      <section class="modal-body">
            <slot name="body">
                <div class="table-wrap">
	            	    <div class="table-header">
	            			<div>Session</div>
	            		    <div>Slides</div>
	            		    <div>Runtime</div>
	            		    <div>File Size</div>
	                	</div>
	            	    <div class="table-body">
	            			<div>{{sessionNumber}}</div>
	            			<div>{{numberofSlides}}</div>
	            			<div>{{sessionRuntime}}</div>
	            			<div>{{fileSize}}</div>
	            	    </div>
                </div>
            </slot>
       </section>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'modal',
    props: ['modalHeader', 'sessionNumber', 'numberofSlides', 'sessionRuntime', 'fileSize'],
    // props: {
    //     modalHeader: {
    //     type: String
    //     }
    // },
    methods: {
      close() {
        this.$emit('close');
      },
    },
  };
</script>

<style>
  .modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .modal {
    background: #FFFFFF;
    box-shadow: 0px 20px 44px rgba(0, 0, 0, 0.3);
    border: 1px solid #979797;
    border-radius: 3px;
    overflow-x: auto;
    display: flex;
    flex-direction: column;
    width: 544px;
  }

  .modal-header {
    padding: 15px;
    display: flex;
    background-color: #DADADA;
    display: flex;
    align-items: baseline;
    justify-content: space-between;
  }

  .header-txt {
      font-size: 18px;
      color: black;
      width: 410px;
  }

  .modal-body {
    position: relative;
    padding: 30px 0px;
  }

  .btn-close {
    border: none;
    font-size: 20px;
    cursor: pointer;
    font-weight: bold;
    background: transparent;
  }

 .table-wrap {
     width: 100%;
 }
.table-header {
    border-bottom: 1px solid #BABABA;
}
 .table-header,
 .table-body {
     display: flex;
     width: 456px;
     margin: auto;
     padding: 12px 0;
     color: #000000;
 }

 .table-header div,
 .table-body div {
     width: 130px;
 }

 .table-header div:last-child,
 .table-body div:last-child {
     width: 66px;
     text-align: right;
 }

</style>
