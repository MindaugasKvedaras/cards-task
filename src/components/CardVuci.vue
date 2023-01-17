<template>
    <a-card :title="this.data.title" style="width: 320px; height: 400px; margin: 10px">
      <a-list item-layout="horizontal" :data-source="this.data.option">
      <a-list-item slot="renderItem" slot-scope="item">
        <a-list-item-meta :description="item.data">
          <h4 slot="title" href="https://www.antdv.com/">{{
            item.name
          }}</h4>
        </a-list-item-meta>
      </a-list-item>
    </a-list>
  </a-card>
</template>

<script>
export default {
    name: 'CardItem',

    data() {
        return {

        }
    },

    props: {
      data: Object
    }
}
</script>