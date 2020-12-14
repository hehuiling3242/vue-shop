<template>
  <li>
    <span @click="toggle">
      {{ model.menuName }}
    </span>
    <ul v-if="isFolder" v-show="open">
      <items
        v-for="(item, index) in model.childTree"
        :model="item"
        :key="index"
      ></items>
    </ul>
  </li>
</template>

<script type="text/javascript">
export default {
  name: "items",
  props: ["model"],
  data() {
    return {
      open: false
    };
  },
  computed: {
    isFolder() {
      return this.model.childTree && this.model.childTree.length;
    }
  },
  methods: {
    toggle() {
      if (this.isFolder) {
        this.open = !this.open;
      }
    }
  }
};
</script>
