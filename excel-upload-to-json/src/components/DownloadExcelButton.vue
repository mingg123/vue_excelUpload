<template>
  <div id="app">
    <div>
      <button @click="makeExcelFile5">Excel5</button>
    </div>
  </div>
</template>

<script>
import Xlsx from "xlsx";

export default {
  data() {
    return {
      data1: [
        // {
        //   checked: false,
        //   createDateTime: "2022-09-01T06:27:35.063",
        //   createUser: "NX_28963",
        //   createUserCompany: "NX",
        //   createUserName: "김민지7",
        //   createUserNo: "28963",
        //   gameInfoId: 67,
        //   id: 56,
        //   isUse: true,
        //   itemCode: "TEST",
        //   itemDesc: "TEST",
        //   itemId: 169,
        //   itemTitle: "TEST",
        //   itemType: "ITEM",
        //   localization: null,
        //   localizationId: 2200,
        //   updateDateTime: "2022-09-01T06:27:35.063",
        //   updateUser: "NX_28963",
        //   updateUserCompany: "NX",
        //   updateUserName: "김민지7",
        //   updateUserNo: "28963",
        // },
        {
          itemId: 169,
          itemDesc: "TEST",
          itemTitle: "TEST",
          itemType: "ITEM",
          itemCode: "TEST",
          // ko_name : "test1",
          // ko_description : "test1",
          // ko_iconImageUrl : "test1",
          // en_name : "test1",
          // en_description : "test1",
          // en_iconImageUrl : "test1",
        },
        {
          itemId: 126,
          itemTitle: "5성 승급의 날개",
          itemDesc: "5성 승급의 날개",
          itemType: "ITEM",
          itemCode: "350005",
          // ko_name : "test1",
          // ko_description : "test2",
          // ko_iconImageUrl : "test2",
          // en_name : "test2",
          // en_description : "test2",
          // en_iconImageUrl : "test2",
        },
      ],
    };
  },
  methods: {
    makeExcelFile5() {
      const workBook = Xlsx.utils.book_new();
      const workSheet = Xlsx.utils.json_to_sheet(this.createLocalizationData(this.data1));
      Xlsx.utils.book_append_sheet(workBook, workSheet, "example");
      Xlsx.writeFile(workBook, "example.xlsx");
    },

    createLocalizationData(data) {
      data.forEach((d) => {
        d.ko_name = "test1",
        d.ko_description = "test2",
        d.ko_iconImageUrl = "test2",
        d.en_name = "test2",
        d.en_description = "test2",
        d.en_iconImageUrl = "test2"
      });
      return data;
    }
  },
};
</script>

<style></style>
