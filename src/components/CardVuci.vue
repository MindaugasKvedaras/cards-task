<template>
    <a-card
      :title="this.cardData.title"
      style="width: 320px; height: 400px; margin: 10px; cursor: grab"
    >
      <a-list item-layout="horizontal" :data-source="this.cardData.option">
        <a-list-item slot="renderItem" slot-scope="item">
          <a-list-item-meta :description="item.data">
            <h4 slot="title">{{ item.name }}</h4>
          </a-list-item-meta>
        </a-list-item>
      </a-list>
    </a-card>
</template>

<script>
export default {
  name: "CardItem",

  data() {
    return {};
  },

  props: {
    cardData: Object,
  },
};
</script>
