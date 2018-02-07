<template>
  <div>
    <x-header :left-options="{showBack: false}" :class="bg_color">小河项目</x-header>
    <group :class="group_project_list" :title="'PC网站'">
      <cell :title="'苏泊尔网站'" :class=project_list link="http://app70.vliang.com/home" is-link value="2014-11-11"></cell>
      <cell :title="'项目2'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目3'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目4'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目5'" :class=project_list link="https://vux.li" is-link></cell>
    </group>
    <group :class="group_project_list" :title="'移动端项目'">
      <cell :title="'项目1'" :class=project_list link="http://app70.vliang.com/home" is-link></cell>
      <cell :title="'项目2'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目3'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目4'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目5'" :class=project_list link="https://vux.li" is-link></cell>
    </group>
    <group :class="group_project_list" :title="'移动端游戏'">
      <cell :title="'2048小游戏'" :class=project_list link="http://app71.vliang.com/" is-link value="2014-11-15" is-link></cell>
      <cell :title="'项目2'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目3'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目4'" :class=project_list link="https://vux.li" is-link></cell>
      <cell :title="'项目5'" :class=project_list link="https://vux.li" is-link></cell>
    </group>
  </div>
</template>

<script>
import { XHeader, Actionsheet, TransferDom, ButtonTab, ButtonTabItem ,Cell,Group} from 'vux'

export default {
  directives: {
    TransferDom
  },
  components: {
    XHeader,
    Actionsheet,
    ButtonTab,
    ButtonTabItem,
    Cell,
    Group
  },
  data () {
    return {
      showMenus: false,
      project_list: "project_list",
      group_project_list: "group_project_list",
      bg_color: "blue_color"
    }
  }
}
</script>

<style lang="less">

  .overwrite-title-demo {
    margin-top: 5px;
  }
  .group_project_list>div {
    margin-top: 0;
    background: none;
  }

  .group_project_list .project_list {
    margin-bottom: 0.5rem;
    background: #fff; 
    // border-top: 1px solid #eee;
    // border-bottom: 1px solid #eee;
  }
  .project_list:before {
    display: none;
  }
  .group_project_list>div:after {
    display: none;
  }
  .blue_color.vux-header {
    background: #39f;
  }
  .group_project_list .weui-cells__title {
    padding: 0.4rem 0 0.4rem 15px;
    margin-bottom: 0;
    font-weight: bold;
    font-size: 1rem;
    color: #39f;
  }
</style>