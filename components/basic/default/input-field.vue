<template>
  <div class="textarea-box-wk" :style="styleObj" :class="{active: isFocus}">
    <label :style="{color: color}" class="textarea-label-wk" :class="{labelUp: labelUp(this)}" for="textarea-box-wk">{{ label }}</label>
    
    <textarea :style="{color: color}" id="textarea-box-wk'" class="textarea-form-wk" :type="type" @focus="isFocus=true" @blur="isFocus=false" v-model="cValue">
  </div>
</template>
<script>
export default {
  model: {
    prop: 'value',
    event: 'textarea'
  },
  data () {
    return {
    }
  },
  computed: {
    cValue: {
      get () {
        return this.value
      },
      set (value) {
        this.open = false
        this.$emit('textarea', value)
      }
    },
    styleObj () {
      let obj = {
        '--color' : this.color
      }
      return obj
    }
  },
  props : {
    type: {
      type: String,
      default () {
        return 'text'
      }
    },
    label: {
      type: String,
      default () {
        return ''
      }
    },
    value: {
      default () {
        return ''
      }
    },
    color: {
      type: String,
      defulat () {
        return '#FFFF'
      }
    }
  },
  data () {
    return {
      isFocus: false
    }
  },
  methods : {
    labelUp (e) {
      console.log("textarea value : "+e.value)
      if(this.isFocus || e.value){
        return true
      } else {
        return false
      }
    }
  }
}
</script>
<style>
.textarea-box-wk {
  --color: #FFFF;
  margin: 10px 10px;
  position: relative;
  width: 100%;
  border-bottom: 1px solid #ccc;
  &::after {
    content: '';
    position: absolute;
    bottom: -1px;
    width: 0;
    transition: 0.3s;
    transition-timing-function: cubic-bezier(0.0, 0.0, 0.2, 1);
    left: 50%;
    border-bottom: solid 1px var(--color);
  }
}
.textarea-box-wk .textarea-form-wk {
  width: 100%;
  padding: 0px 5px 3px 5px;
  background-color: inherit;
  margin: 0;
}
.textarea-box-wk.active::after {
  width: 100%;
  left: 0;
}
.textarea-box-wk textarea {
  border: none;
  outline: none;
}
.textarea-label-wk {
  opacity: 0.5;
  font-size: 10px;
  position: relative;
  padding-left: 5px;
  bottom: -15px;
  transition: 0.3s;
  transition-timing-function: cubic-bezier(0.0, 0.0, 0.2, 1);
}
.textarea-label-wk.labelUp{
  bottom:0px;
  transition: 0.3s;
  transition-timing-function: cubic-bezier(0.0, 0.0, 0.2, 1);
}
</style>
