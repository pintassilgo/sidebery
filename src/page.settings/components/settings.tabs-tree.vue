<template lang="pug">
section
  h2 {{t('settings.tabs_tree_title')}}
  ToggleField(
    label="settings.tabs_tree_layout"
    :value="$store.state.tabsTree"
    @input="setOpt('tabsTree', $event)")
  ToggleField(
    label="settings.group_on_open_layout"
    :inactive="!$store.state.tabsTree"
    :value="$store.state.groupOnOpen"
    @input="setOpt('groupOnOpen', $event)")
  SelectField(
    label="settings.tabs_tree_limit"
    optLabel="settings.tabs_tree_limit_"
    :inactive="!$store.state.tabsTree"
    :value="$store.state.tabsTreeLimit"
    :opts="$store.state.tabsTreeLimitOpts"
    @input="setOpt('tabsTreeLimit', $event)")
  ToggleField(
    label="settings.tabs_child_count"
    :inactive="!$store.state.tabsTree"
    :value="$store.state.tabsChildCount"
    @input="setOpt('tabsChildCount', $event)")
  ToggleField(
    label="settings.tabs_lvl_dots"
    :inactive="!$store.state.tabsTree"
    :value="$store.state.tabsLvlDots"
    @input="setOpt('tabsLvlDots', $event)")
  ToggleField(
    label="settings.tabs_tree_bookmarks"
    :inactive="!$store.state.tabsTree"
    :value="$store.state.tabsTreeBookmarks"
    @input="setOpt('tabsTreeBookmarks', $event)")
</template>

<script>
import ToggleField from '../../components/toggle-field'
import SelectField from '../../components/select-field'

export default {
  components: { ToggleField, SelectField }
}
</script>
