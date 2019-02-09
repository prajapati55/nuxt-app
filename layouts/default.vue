<template>
  <div>
    <Nav @showmodal="loadModal"/>
    <nuxt />
    <Modal v-if="modalShown">
        <template slot="header">
            <h5 class="modal-title">Sign In</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true" @click="modalShown = false">&times;</span>
            </button>
        </template>
       <Login slot="body"></Login>
    </Modal>
  </div>
</template>
<script>
import Nav from '~/layouts/partials/navbar'
import Modal from '@/components/modal'
import Login from '@/components/login'

export default {
  components: {
    Nav,
    Modal,
    Login
  },
  data(){
    return {
      modalShown:false
    }
  },
  methods:{
    loadModal: function(){
      this.modalShown = true;
    }
  }
}
</script>

<style>
.page-enter-active,
.page-leave-active {
  opacity: 1;
  transition: opacity .25s;
  animation-duration: .3s;
  animation-fill-mode: both;
}

.page-enter-active {
  animation-name: pageFadeInUp;
}

.page-leave-active {
  animation-name: pageFadeOutDown;
}

.page-enter, .page-leave-to {
  opacity: 0;
}


@-webkit-keyframes pageFadeInUp {
  0% {
    opacity: 0;
    transform: translate3d(0, 1.25%, 0);
  }

  to {
    opacity: 1;
    transform: none;
  }
}

@-webkit-keyframes pageFadeOutDown {
  0% {
    opacity: 1;
  }

  to {
    opacity: 0;
    transform: translate3d(0, 1.25%, 0);
  }
}
</style>
