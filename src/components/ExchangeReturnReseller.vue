<template>
    <div class="printTemplate">
        <b-container fluid>
            <b-row>
                <b-col class="printTemplate__title">
                    <h1 >Exchange Retur Reseller</h1>
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
                        <b-col cols="4" class="label">
                            <h3>Cabang</h3>
                        </b-col>
                        <b-col cols="8">
                            <h3><small>: JKT-DM - Jakarta-DaanMogot</small></h3>
                        </b-col>
                    </b-row>
                </b-col>
                <b-col cols="4" >
                    <b-row>
                        <b-col cols="4" class="label" >
                            <h3>Gudang</h3>
                        </b-col>
                        <b-col cols="7">
                            <h3><small>: JKT01-Green Sedayu Bizpark</small></h3>
                        </b-col>
                        <b-col cols="4" class="label">
                            <h3>Supplier</h3>
                        </b-col>
                        <b-col cols="7">
                            <h3><small>: 0003 - Schumm PLC</small></h3>
                        </b-col>
                    </b-row>
                </b-col>
                <b-col cols="4">
                    <b-row>
                        <b-col cols="12">
                            <h3>Catatan :</h3>
                        </b-col>
                        <b-col cols="12" style="height: 4.5rem; border: 2px solid #888;"></b-col>
                    </b-row>
                </b-col>
            </b-row>
            <b-row class="printTemplate__table ExchangeReturnReseller">
                <b-table 
                    :items="ExchangeReturnReseller_contents" 
                    :fields="ExchangeReturnReseller_fields"
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
            ExchangeReturnReseller_fields: [
                {'no': {'class' : 'tb_no'}}, {'SKU': {'class' : 'tb_sku'}}, {'kode': {'class' : 'tb_kode'}}, {'nama': {'class' : 'tb_nama'}}, 'warna', 'qty','unit', 'total_qty', 'sisa_qty'
            ],
            ExchangeReturnReseller_fields: []
        }
    }
}
</script>

<style lang="scss">
    .printTemplate__table.ExchangeReturnReseller {
        min-height: 34rem;

        .tb_no{
            width: 4%;
        }
        .tb_kode{
            width: 20%;
        }
        .tb_nama{
            width: 20%;
        }
        .tb_sku{
            width: 20%;
        }
    }

    @media print {
        .printTemplate__table.ExchangeReturnReseller {
            min-height: 119rem;
        }
    }
</style>