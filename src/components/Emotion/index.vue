<template>
  <div>
    <div class="emotion-box" :style="{height:'290px' }" >
      <div class="emotion-box-line" v-for="(line, i) in list" :key="i" >
        <emotion class="emotion-item" v-for="(item, i) in line" :key="i" @click.native="clickHandler(item)" >{{item}}</emotion>
      </div>
    </div>
  </div>
</template>

<script>
import Emotion from './Emotion'
export default {
  props: {
    height: {
      type: Number,
      default: 300,
    }
  },
  data () {
    return {
      list: [
        ['微笑', '撇嘴', '色', '发呆', '得意', '流泪', '害羞', '闭嘴', '睡', '大哭'],
        ['尴尬', '发怒', '调皮', '呲牙', '惊讶', '难过', '囧', '抓狂', '吐', '偷笑'],
        ['愉快', '白眼', '傲慢', '困', '惊恐', '流汗', '憨笑', '悠闲', '奋斗', '咒骂'],
        ['疑问', '嘘', '晕', '衰', '骷髅', '敲打', '再见', '擦汗', '抠鼻', '鼓掌'],
        ['坏笑', '左哼哼', '右哼哼', '哈欠', '鄙视', '委屈', '快哭了', '阴险', '亲亲', '可怜'],
        ['菜刀', '西瓜', '啤酒', '咖啡', '猪头', '玫瑰', '凋谢', '嘴唇', '爱心', '心碎'],
        ['蛋糕', '炸弹', '便便', '月亮', '太阳', '拥抱', '强', '弱', '握手', '胜利'],
        ['抱拳', '勾引', '拳头', 'OK', '跳跳', '发抖', '怄火', '转圈', '笑脸', '生病'],
        ['破涕为笑', '吐舌', '脸红', '恐惧', '失望', '无语', '嘿哈', '捂脸','奸笑','机智'],
        ['皱眉','耶','鬼魂','合十','强壮','庆祝','礼物','红包','發','小狗']
      ]
    }
  },
  methods: {
    clickHandler (i) {
      let emotion = `[${i}]`
      this.$emit('emotion', emotion)
    }
  },
  components: {
    Emotion
  }
}
</script>
<style scoped>
  .emotion-box {
    margin: 0 auto;
    width: 100%;
    box-sizing: border-box;
    padding: 5px;
    border: 1px solid #b4b4b4;
    overflow: hidden;
    overflow-y: auto;
  }
  .emotion-box-line {
    display: flex;
  }
  .emotion-item {
    flex: 1;
    text-align: center;
    cursor: pointer;
  }
</style>