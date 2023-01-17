<template>
  <div id="app">
    <draggable class="flex" v-model="cardData" @start="drag = true" @end="drag = false">
        <card-item v-for="card in cardData" :data="card" :key="card.id">
        </card-item>
    </draggable>

    <!-- <a-card :title="this.cardData[0].title" style="width: 300px">
      <a-list item-layout="horizontal" :data-source="this.cardData[0].option">
      <a-list-item slot="renderItem" slot-scope="item">
        <a-list-item-meta :description="item.data">
          <h4 slot="title" href="https://www.antdv.com/">{{
            item.name
          }}</h4>
        </a-list-item-meta>
      </a-list-item>
    </a-list>
  </a-card> -->
  </div>
</template>

<script>
import CardItem from "./components/CardVuci.vue";
import draggable from "vuedraggable";
export default {
  name: "App",

  components: {
    CardItem,
    draggable,
  },

  data() {
    return {
      sysinfo: [
        ["ROUTER UPTIME", "05h 41m 37s"],
        ["LOCAL DEVICE TIME", "2023-01-17"],
        ["FIRMWARE VERSION", "RUTX_R_00.07.02.7"],
      ],

      networkinfo: [
        ["TYPE", "Wired (br-lan)"],
        ["IP ADDRESS", "192.168.1.2/24"],
      ],

      networkevents: [
        ["2022-11-23 14:54:23", "Instance new is in master mode"],
        ["2022-11-23 14:54:19", "Instance new is backup mode"],
        ["2022-11-23 14:54:17", "Mobile data connected (internal modem)"],
        ["2022-11-23 14:54:11", "Joined FDD LTE network (internal modem)"],
      ],

      cardData: [],
      // cardOptions: [
      //   { name: this.sysinfo[0][0], data: this.sysinfo[0][1] },
      //   { name: this.sysinfo[1][0], data: this.sysinfo[1][1] },
      //   { name: this.sysinfo[2][0], data: this.sysinfo[2][1],
      //   },
      // ],
    };
  },

  created() {
    this.setCardData();
    console.log(this.cardData);
  },

  methods: {
    setCardData() {
      (this.cardData[0] = {
        title: "SYSTEM",
        option: [
          {
            name: this.sysinfo[0][0],
            data: this.sysinfo[0][1],
          },
          {
            name: this.sysinfo[1][0],
            data: this.sysinfo[1][1],
          },
          {
            name: this.sysinfo[2][0],
            data: this.sysinfo[2][1],
          },
        ],
        id: 1,
      }),
        (this.cardData[1] = {
          title: "LAN",
          option: [
            {
              name: this.networkinfo[0][0],
              data: this.networkinfo[0][1],
            },
            {
              name: this.networkinfo[1][0],
              data: this.networkinfo[1][1],
            },
          ],
          id: 2,
        }),
        (this.cardData[2] = {
          title: "RECENT NETWORK EVENTS",
          option: [
            {
              name: this.networkevents[0][0],
              data: this.networkevents[0][1],
            },
            {
              name: this.networkevents[1][0],
              data: this.networkevents[1][1],
            },
            {
              name: this.networkevents[2][0],
              data: this.networkevents[2][1],
            },
            {
              name: this.networkevents[3][0],
              data: this.networkevents[3][1],
            },
          ],
          id: 3,
        });
    },
  },
};
</script>
<style>
#app {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 10px;
}

.flex {
  display: flex;
}
</style>
