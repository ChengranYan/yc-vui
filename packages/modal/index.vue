<template lang="pug" id="modal-template">
  transition(name="modal")
    .modal-mask
      .modal-wrapper
        .modal-container
          //- img.modal-close-btn(src="../assets/window_icon_close.png" @click="$emit('closeHandler')")
          .modal-header
            h3.modal-title(v-if="showTitle") {{ title }}
          .modal-body
            .modal-content 
              slot {{ body }}
          .modal-footer
            button.modal-default-button(v-if="showDefaultButton" @click="$emit('defaultBtnHandler')") {{ defaultBtnName }}
            button.modal-primary-button(@click="$emit('primaryBtnHandler')") {{ primaryBtnName }}
</template>

<script>
export default {
  name: 'v-modal',
  props: {
    type: {
      type: String,
      default: 'alert'
    },
    title: String,
    body: {
      type: String,
      default: '内容'
    },
    primaryBtnName: {
      type: String,
      default: '我知道了'
    },
    defaultBtnName: {
      type: String,
      default: '取消'
    }
  },
  computed: {
    showDefaultButton: function () {
      return this.type === 'confirm'
    },
    showTitle: function () {
      return !!this.title
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
.modal-mask
  position fixed
  z-index 9998
  top 0
  left 0
  bottom 0
  right 0
  width 100%
  height 100%
  background-color rgba(0, 0, 0, .5)
  display flex
  justify-content center 
  align-items center
  transition opacity .3s ease
.modal-wrapper
  // display table-cell
  // vertical-align middle
.modal-container
  position relative
  width 280px
  margin 0px auto
  background-color #fff
  border-radius 2px
  box-shadow 0 2px 8px rgba(0, 0, 0, .33)
  transition all .3s ease
  font-family Helvetica, Arial, sans-serif
.modal-close-btn
  display none
  width 24px
  height 24px
  position absolute
  right 12px
  top 12px

.ios
  .modal-container
    padding 0 25px 25px
    border-radius 14px
    .modal-close-btn
      display block
    .modal-header
      .modal-title
        text-align center
        font-size 17px
        color #3b3b3b
        font-weight bold
    .modal-body
      // padding-top 11px
      .modal-content
        font-size 14px
        color #888
        text-align center
        line-height 22px
    .modal-footer
      display flex
      margin-top 14px
      button
        display block
        flex 1
        height 40px
        border none
        outline none
        border-radius 20px
        font-size 16px
        font-weight bold
      button + button
        margin-left 16px
      .modal-default-button
        color #888
        background-color #f3f3f3
      .modal-primary-button
        color #fff
        background-color #1696ea



.android
  .modal-container
    border-radius 3px
    .modal-header
      // padding 24px 24px 0
      .modal-title
        font-size 18px
        color #3b3b3b
        font-weight bold
    .modal-body
      // padding 0 24px
      margin-top 12px
      .modal-content
        font-size 14px
        color #888
        line-height 22px
    .modal-footer
      display flex
      margin-top 14px
      button
        display block
        margin-bottom 14px
        width 252px
        height 40px
        border none
        outline none
        border-radius 4px
        font-size 16px
        font-weight bold
      button + button
        margin-left 16px
      .modal-default-button
        color #888
        background-color #f3f3f3
      .modal-primary-button
        color #fff
        background-color #1696ea
        margin 14px auto


.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}

.clear-fix
  &:before, &:after
    content " "
    display table
  &:after
    clear both
#app
  width 100%
  height 100%
@media screen and (max-width: 321px) 
  .modal-container 
    width 200px

</style>
