<template>
    <div class="printTemplate">
        <b-container fluid>
            <b-row>
                <b-col class="printTemplate__title">
                    <h1 >Exchange Retur Supplier</h1>
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
                        <b-col cols="12" class="border border-dark" style="height: 4.5rem;"></b-col>
                    </b-row>
                </b-col>
            </b-row>
            <b-row class="printTemplate__table ExchangeReturnSupplier">
                <b-table 
                    :items="ExchangeReturnSupplier_contents" 
                    :fields="ExchangeReturnSupplier_fields"
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
            ExchangeReturnSupplier_fields: [
                {'no': {'class' : 'tb_no'}}, {'SKU': {'class' : 'tb_sku'}}, {'kode': {'class' : 'tb_kode'}}, {'nama': {'class' : 'tb_nama'}}, 'warna', 'qty', 'total_qty', 'sisa_qty'
            ],
            ExchangeReturnSupplier_contents: []
        }
    }
}
</script>

<style lang="scss">
    .printTemplate__table.ExchangeReturnSupplier {
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
        .printTemplate__table.ExchangeReturnSupplier {
            min-height: 119rem;
        }
    }
</style>