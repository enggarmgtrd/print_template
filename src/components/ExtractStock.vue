<template>
    <div class="printTemplate">
        <b-container fluid>
            <b-row>
                <b-col class="printTemplate__title">
                    <h1 >Pindah / Extract Stock</h1>
                </b-col>
                <b-col class="text-right pr-0">
                    <b-button class="btn-warning btn-lg px-5 no-print" onclick="window.print()">Print</b-button>
                </b-col>
            </b-row>
            <b-row class="printTemplate__header">
                <b-col cols="4">
                    <b-row>
                        <b-col cols="4" class="label">
                            <h3>No</h3>
                        </b-col>
                        <b-col cols="8">
                            <h3><small>: PRX/JKT-DM/2008/0008</small></h3>
                        </b-col>
                        <b-col cols="4" class="label">
                            <h3>Tanggal</h3>
                        </b-col>
                        <b-col cols="8">
                            <h3><small>: 07/08/2020</small></h3>
                        </b-col>
                    </b-row>
                </b-col>
                <b-col cols="4" >
                    <b-row>
                        <b-col cols="4" class="label">
                            <h3>Cabang</h3>
                        </b-col>
                        <b-col cols="8">
                            <h3><small>: JKT-DM - Jakarta-DaanMogot</small></h3>
                        </b-col>
                        <b-col cols="4" class="label" >
                            <h3>Gudang</h3>
                        </b-col>
                        <b-col cols="8">
                            <h3><small>: JKT01-Green Sedayu Bizpark</small></h3>
                        </b-col>
                    </b-row>
                </b-col>
                <b-col cols="4" class="pr-0">
                    <b-row>
                        <b-col cols="3">
                            <h3>Catatan </h3>
                        </b-col>
                        <h3 class=""><small>:</small></h3><b-col cols="8" class="pl-0 ml-4 border border-dark" style="height: 4.5rem;"></b-col>
                    </b-row>
                </b-col>
            </b-row>
            <b-row class="printTemplate__table ExtractStock">
                <b-table 
                    :items="ExtractStock_contents" 
                    :fields="ExtractStock_fields"
                    show-empty
                    class="text-center"
                    bordered="bordered"
                    >
                    <template v-slot:cell(no)="data">
                        {{data.index + 1}}
                    </template>
                </b-table>
            </b-row>
            <b-row class="printTemplate__footer">
                <b-col cols="12" class="printTemplate__footer-signature">
                    <b-row>
                        <b-col cols="2" class="text-center">
                            <h4 style="margin-bottom: 10rem;">Hormat Kami</h4>
                            <h4>............................</h4>
                        </b-col>
                        <b-col cols="2" offset="8" class="text-center">
                            <h4 style="margin-bottom: 10rem;">Penerima</h4>
                            <h4>............................</h4>
                        </b-col>
                    </b-row>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
export default {
    data(){
        return{
            ExtractStock_fields: [
                {'no': {'class' : 'tb_no'}},{'serial_no':{'class':'tb_serial'}}, {'SKU': {'class' : 'tb_sku'}}, {'nama': {'class' : 'tb_nama'}}, {'kode': {'class' : 'tb_kode'}}, 'warna', 'PPN', 'qty'
            ],
            ExtractStock_contents:[]
        }
    }
}
</script>

<style lang="scss">
    .printTemplate__table.ExtractStock {
        min-height: 37rem;

        .tb_no{
            width: 4%;
        }
        .tb_serial{
            width: 18%;
        }
        .tb_sku{
            width: 18%;
        }
        .tb_kode{
            width: 18%;
        }
        .tb_nama{
            width: 18%;
        }
    }

    @media print {
        .printTemplate__table.ExtractStock {
            min-height: 119rem;
        }
    }
</style>