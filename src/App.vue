<template>
  <div id="app">
    
    <BuktiPenerimaanPembayaran />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import BuktiPenerimaanPembayaran from './components/BuktiPenerimaanPembayaran.vue'

export default {
  name: 'App',
  components: {
    BuktiPenerimaanPembayaran
  }
}
</script>

<style lang="scss">
html{
  font-size: 62.5%;
}
#app{
  padding: 0rem;
}

.bg-blue {
  background: #143793;
  -webkit-print-color-adjust: exact; 
  color: #fff;
}
.text-blue {
  color: #143793;
  -webkit-print-color-adjust: exact; 
}

.container-fluid{
  padding: 1rem 3rem !important;

  .printTemplate{

    &__title{
      padding-left: 0px;
      margin-bottom: 1rem !important;
    }

    &__header{
      margin-bottom: 2.5rem;
      [class^="col-"]{
        padding-left: 0px;
      }
    }

    &__footer{

      &-grandTotal {
        border: 1px solid #000 ;
        padding: 1rem 0px;
        margin-bottom: 5rem;
      }
    }
  } 
}

// Overrides Bootstrap
 .table-bordered tr th{
   border: 1px solid #000 !important;
     -webkit-print-color-adjust: exact; 
 }
 .table-bordered thead tr th {
    border: 1px solid #000 !important;
      -webkit-print-color-adjust: exact; 
 }
 .table-bordered tbody tr td {
    border: 1px solid #000 !important;
      -webkit-print-color-adjust: exact; 
 }
 




 @media print{
    .printTemplate__footer{
            page-break-inside: avoid;
        }
    .no-print{
      display: none !important;
    }

     .table-bordered tr th{
   border: 2px solid #000;
     -webkit-print-color-adjust: exact; 
 }
 .table-bordered thead tr th {
    border: 2px solid #000;
      -webkit-print-color-adjust: exact; 
 }
 .table-bordered tbody tr td {
    border: 2px solid #000;
      -webkit-print-color-adjust: exact; 
 }


}
</style>
