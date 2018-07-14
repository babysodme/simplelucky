<template>
  <div class="category">
    <b-button class="categorybt" variant="outline-success" size="md" @click="showModal(index)" v-for="(item,index) in list" ref="header">{{item.catename}}
    </b-button>

    <b-modal   ref="myModalRef" hide-footer title="ENJOY YOUR COFFEE" class="modal-dialog">
      <div class="d-block text-center">
        
        <h3 v-if="list[index].catename!='慕斯冰 Smoothies' && list[index].drinks[0]!='意式浓缩'">{{list[index].drinks[0]}} {{tag[0]}}</h3> 
        <h3 v-else>{{list[index].drinks[0]}}</h3>
        
      </div>
      <b-btn class="mt-3" variant="outline-danger" block @click="hideModal">Close Me</b-btn>
    </b-modal>

  <br>
  <br>
  <br>
   <b-alert show variant="light">
    Tips:仅供悦咖啡内部员工考核抓阄使用.
  </b-alert>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tag: ["(冰)", "(热)"],
      index:0,
      list: [
        {
          catename: "经典咖啡 Classic Coffee",
          drinks: ["美式", "摩卡", "卡布奇诺", "意式浓缩", "拿铁"]
        },
        {
          catename: "特色咖啡 Specialty Coffee",
          drinks: [
            "爱尔兰榛果拿铁",
            "红丝绒拿铁",
            "提拉米苏拿铁",
            "野兽咖啡",
            "玫瑰奶油拿铁",
            "澳洲平白",
            "太妃玛奇朵"
          ]
        },
        {
          catename: "慕斯冰 Smoothies",
          drinks: [
            "弗拉明戈慕斯冰",
            "布朗尼慕斯冰",
            "莫吉托慕斯冰",
            "玫瑰慕斯冰",
            "野莓果汁冰",
            "奇异果青柠慕斯冰",
            "抹茶慕斯冰",
            "香草慕斯冰"
          ]
        },
        {
          catename: "茶 Tea",
          drinks: [
            "蜜桃乌龙茶",
            "抗霾润肺茶",
            "珍珠茉莉",
            "伯爵红茶",
            "糯香普洱",
            "如意红茶拿铁",
            "宇治抹茶拿铁"
          ]
        }
      ],
      category: ["经典咖啡", "特色咖啡", "慕斯冰", "茶"]
    };
  },
  // computed: {
  //   reversedMessage: function() {
  //     // `this` 指向 vm 实例
  //     function randomsort(a, b) {
  //       return Math.random() > 0.5 ? -1 : 1;
  //     }
  //     return this.ccoffee.sort(randomsort);
  //   }
  // },
  methods: {
    showModal(index) {
      this.index= index
      function randomsort(a, b) {
        return Math.random() > 0.5 ? -1 : 1;
      }
      this.list[index].drinks.sort(randomsort);
      this.tag.sort(randomsort);
      this.$refs.myModalRef.show();
    },
    hideModal() {
      this.$refs.myModalRef.hide();
    }
  }
};
</script>

<style lang="scss">
.category {
  text-align: center;
  .categorybt {
    padding: 0.5rem;
    width: 15rem;
    margin-top: 1rem;
  }
}
.modal-dialog {
  position: absolute;
  width: auto;
  margin: 50% 15% 15%;
}
</style>

<!-- modal-methods-1.vue -->