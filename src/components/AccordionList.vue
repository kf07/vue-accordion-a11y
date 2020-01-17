<template>
  <div>
    <AccordionListItem accordion-name="accordion1">
      <template v-slot:title>アコーディオン1</template>
      <template v-slot:body>アコーディオン1テキスト</template>
    </AccordionListItem>
    <AccordionListItem accordion-name="accordion2">
      <template v-slot:title>アコーディオン2</template>
      <template v-slot:body>アコーディオン2テキスト</template>
    </AccordionListItem>
  </div>
</template>

<script>

  import AccordionListItem from "./AccordionListItem";

  export default {
    name: "AccordionList",
    components: {AccordionListItem}
  }
</script>

<style scoped>

</style>