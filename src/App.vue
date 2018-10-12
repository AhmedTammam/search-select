<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <form @submit="onSubmit">
          <div class="form-row align-items-center">
            <div class="col-5">
              <label>Supplier Category</label>
              <multi-select :options="options1"
                       :selected-options="items1"
                       placeholder="select item"
                       @select="onSelect1">
              </multi-select>
            </div>
            <div class="col-5">
              <label>LuxuryOutlet Category</label>
              <multi-select :options="options2"
                       :selected-options="items2"
                       placeholder="select item"
                       @select="onSelect2">
              </multi-select>
            </div>
            <div class="col-2">
              <button type="submit" class="btn btn-primary mb-2">Submit</button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { ModelListSelect } from 'vue-search-select'
import { MultiSelect } from 'vue-search-select'

export default {
  name: 'app',
  components: {
    ModelListSelect,
    MultiSelect
  },
  data: () => ({
    options1: [
      { value: '1', text: 'aa' + ' - ' + '1' },
      { value: '2', text: 'ab' + ' - ' + '2' },
      { value: '3', text: 'bc' + ' - ' + '3' },
      { value: '4', text: 'cd' + ' - ' + '4' },
      { value: '5', text: 'de' + ' - ' + '5' }
    ],
    searchText1: '',
    items1: [],
    lastSelectItem1: {},
    suppRes: [],
    options2: [
      { value: '1', text: 'aa' + ' - ' + '1' },
      { value: '2', text: 'ab' + ' - ' + '2' },
      { value: '3', text: 'bc' + ' - ' + '3' },
      { value: '4', text: 'cd' + ' - ' + '4' },
      { value: '5', text: 'de' + ' - ' + '5' }
    ],
    searchText2: '',
    items2: [],
    lastSelectItem2: {},
    loxRes: []
  }),
  methods: {
    onSelect1 (items, lastSelectItem) {
      this.items1 = items
      this.lastSelectItem2 = lastSelectItem
    },
    onSelect2 (items, lastSelectItem) {
      this.items2 = items
      this.lastSelectItem2 = lastSelectItem
    },
    onSubmit(e){
      e.preventDefault();
      
      this.items1.forEach(ele=>{
        this.suppRes.push(ele.text)
      })
      this.items2.forEach(ele=>{
        this.loxRes.push(ele.text)
      })

      console.log(this.suppRes, this.loxRes);
      
    }
  }
}
</script>

<style>
</style>
