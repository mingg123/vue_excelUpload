<template>
  <div id="app">
    <h1>excel import with vue & sheet.js!</h1>
    <div>
      <div>
        {{ this.excelData }}
      </div>
      <hr />
      <div>
        {{ this.excelData[1] }}
      </div>
      <input type="file" @change="excelExport" />
    </div>
    <div></div>
  </div>
</template>

<script>
import XLSX from "xlsx";
export default {
  data() {
    return {
      excelData: [],
    };
  },
  methods: {
    excelExport(event) {
      const input = event.target;
      const reader = new FileReader();
      reader.onload = () => {
        const fileData = reader.result;
        const wb = XLSX.read(fileData, { type: "binary" });
        wb.SheetNames.forEach(sheetName => {
          const rowObj = XLSX.utils.sheet_to_json(wb.Sheets[sheetName]);
          this.excelData = JSON.parse(JSON.stringify(rowObj));
        });
      };

      reader.readAsBinaryString(input.files[0]);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
