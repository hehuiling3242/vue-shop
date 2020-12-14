<template>
  <div>
    <ul>
      <items v-for="(model, index) in list" :model="model" :key="index"></items>
    </ul>
  </div>
</template>

<script>
import Items from "./items";

export default {
  components: {
    Items
  },
  data() {
    return {
      list: [
        {
          id: "1",
          menuName: "haha",
          childTree: [
            {
              menuName: "一",
              childTree: [
                {
                  menuName: "1",
                  childTree: [
                    {
                      menuName: "2",
                      childTree: [
                        {
                          menuName: "3",
                          childTree: [{ menuName: "3" }]
                        }
                      ]
                    }
                  ]
                }
              ]
            },
            {
              menuName: "二"
            }
          ]
        },
        {
          id: "2",
          menuName: "heihei"
        },
        {
          id: "3",
          menuName: "enen"
        },
        {
          id: "4",
          menuName: "hehe",
          childTree: [
            {
              menuName: "一",
              childTree: [{ menuName: "1" }]
            }
          ]
        }
      ]
    };
  }
};
</script>
