<template>
  <div>
    <i-panel class="cell-panel-demo">
      <i-cell title="单行列表"></i-cell>
    </i-panel>
    <i-panel class="cell-panel-demo">
      <i-cell title="单行列表" is-link value="详细信息"></i-cell>
    </i-panel>
    <i-panel class="cell-panel-demo">
      <i-cell title="单行列表" label="附加描述" value="详细信息"></i-cell>
    </i-panel>

    <i-panel class="cell-panel-demo" title="带 icon 的 Cell">
      <i-cell title="单行列表" value="详细信息">
        <i-icon type="like_fill" slot="icon"/>
      </i-cell>
    </i-panel>

    <i-panel class="cell-panel-demo" title="带箭头的 cell">
      <i-cell title="只显示箭头" is-link></i-cell>
    </i-panel>

    <i-panel class="cell-panel-demo">
      <i-cell title="跳转到首页" is-link url="/pages/iview/iview_dashboard/main"></i-cell>
    </i-panel>

    <i-panel class="cell-panel-demo" title="cell 组">
      <i-cell-group>
        <i-cell title="只显示箭头" is-link></i-cell>
        <i-cell title="跳转到首页" is-link url="/pages/iview/iview_dashboard/main"></i-cell>
        <i-cell title="只有 footer 点击有效" is-link url="/pages/iview/iview_dashboard/main" only-tap-footer></i-cell>
        <div v-if="show">
          <i-cell title="单行列表" label="附加描述" value="详细信息"></i-cell>
          <i-cell title="表单">
            <input slot="footer" type="digit" placeholder="带小数点的数字键盘"/>
          </i-cell>
        </div>
        <i-cell title="开关">
          <i-switch :value="switch1" @change="onChange" slot="footer">
            <i-icon type="right" slot="open"></i-icon>
            <i-icon type="close" slot="close"></i-icon>
          </i-switch>
        </i-cell>
      </i-cell-group>
    </i-panel>
    <i-panel class="cell-panel-demo">
      <i-cell title="单行列表" label="附加描述" value="详细信息"></i-cell>
    </i-panel>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        show: true,
        switch1: true
      }
    },
    methods: {
      onChange (event) {
        const target = event.target
        this.switch1 = target.value
      }
    }
  }
</script>

<style lang="less">
  .cell-panel-demo {
    display: block;
    margin-top: 15px;
  }
</style>
