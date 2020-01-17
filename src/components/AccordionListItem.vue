<template>
  <div class="accordion">
    <h2>
      <button :aria-expanded="isShow ? 'true' : 'false'" :aria-controls="accordionName" @click="handleClick">
        <slot name="title"></slot>
      </button>
    </h2>
    <div :id="accordionName" :aria-hidden="isShow ? 'false': 'true'">
      <p>
        <slot name="body"></slot>
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    name: "AccordionListItem",
    props: {
      accordionName: {
        type: String,
        required: true
      }
    },
    data() {
      return {
        isShow: false
      }
    },
    methods: {
      handleClick() {
        this.isShow = !this.isShow
      }
    }
  }
</script>

<style>
  /*最低限のCSSのみ指定*/
  [aria-hidden] {
    display: none;
  }

  [aria-hidden="false"] {
    display: block;
  }

  [aria-expanded]::before {
    content: '\25ba\0020'
  }

  [aria-expanded="true"]::before {
    content: '\25bc\0020'
  }

  .accordion {
    margin-bottom: 20px;
  }

  .accordion-body {
    padding: 30px 0;
  }
</style>