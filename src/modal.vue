<template>
    <div class="c-modal" v-show="visibility">
      <div class="c-container">
        <section>
            <div class="row">
                <div class="col-sm-2" style="float:right">
                    <button type="button" class="pull-right" @click="close">&times;</button>
                </div>
            </div>
            <div class="row">
                <slot> 		
                </slot>
            </div>
        </section>
      </div>
    </div>
</template>

<script>
export default {
 
 name: 'modal',
 props: {
 },
 data: function () {
    return {
      visibility:false
    }
  },
 methods: {
		show()
		{
			this.visibility = true;
		},
        close()
        {
			this.visibility = false;
			this.$emit('close');
		},
 }
};
</script>
<style>
    .c-modal {
	position: fixed;
	top: 0;
	right: 0;
	bottom: 0;
	left: 0;
	background: rgba(0,0,0,0.7);;
	z-index: 999;
}

.c-modal .c-container {
	position: relative;
	max-width: 600px;
	margin: 30vh auto 0;
	padding: 2rem;
	border-radius: 3px;
	background: #fff;
	box-shadow: 0 0 20px 0 rgba(52, 73, 94, 0.5);
    min-height: 40vh;
}

.c-modal .c-container a {
	position: absolute;
	top: 5px;
	right: 10px;
	padding: 5px;
}

.c-modal .c-container .button {
	margin-top: 1rem;
}
</style>