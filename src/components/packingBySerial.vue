<template>
    <div class="printTemplate">
        <b-container fluid>
            <b-row>
                <b-col class="printTemplate__title">
                    <h1 >Packing By Serial</h1>
                </b-col>
                <b-col class="text-right">
                    <b-button class="btn-warning btn-lg px-5 no-print" onclick="window.print()">Print</b-button>
                </b-col>
            </b-row>
            <b-row class="printTemplate__header">
                <b-col cols="4">
                    <b-row>
                        <b-col cols="4" class="label">
                            <h4>Packing No</h4>
                        </b-col>
                        <b-col cols="8">
                            <h4><small>: PS-20060590</small></h4>
                        </b-col>
                        <b-col cols="4" class="label">
                            <h4>Tanggal</h4>
                        </b-col>
                        <b-col cols="8">
                            <h4><small>: 07/08/2020</small></h4>
                        </b-col>
                    </b-row>
                </b-col>
                <b-col cols="3" offset="5" class="pr-0">
                    <b-row>
                        <b-col cols="4" class="label">
                            <h4>Sales Order</h4>
                        </b-col>
                        <b-col cols="8">
                            <h4><small>: SA-200050159</small></h4>
                        </b-col>
                        <b-col cols="4" class="label">
                            <h4>Customer</h4>
                        </b-col>
                        <b-col cols="8">
                            <h4><small>: ACC Pengadilan</small></h4>
                        </b-col>
                    </b-row>
                </b-col>
            </b-row>
            <b-row class="printTemplate__table packingBySerial">
                <b-table 
                    :items="packingBySerial_contents" 
                    :fields="packingBySerial_fields"
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
                <!-- <b-col cols="12" class="printTemplate__footer-grandTotal">
                    <b-col cols="3" offset="9" >
                        <b-row>
                            <b-col cols="6"><h3>Subtotal</h3></b-col>
                            <b-col cols="6"><h3>: Rp.0</h3></b-col>
                            <b-col cols="6"><h3>PPN</h3></b-col>
                            <b-col cols="6"><h3>: Rp. 0</h3></b-col>
                            <b-col cols="6"><h1>Grand Total</h1></b-col>
                            <b-col cols="6"><h1>: Rp. 0</h1></b-col>
                        </b-row>
                    </b-col>
                </b-col> -->
                <b-col cols="12" class="printTemplate__footer-signature">
                    <b-row>
                        <b-col cols="2" offset="10" class="text-center">
                            <h4 style="margin-bottom: 7rem;">Penerima</h4>
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
            packingBySerial_fields: [
                {'no': {'class' : 'tb_no'}}, {'item_no':{'class' : 'tb_itemNo'}}, {'kode': {'class' : 'tb_kode'}}, {'nama': {'class' : 'tb_nama'}}, {'serial_no':{'class':'tb_serial'}}, {'qty':{'class' : 'tb_qty'}}, 
                {'check':{'class' : 'tb_qty'}}
            ],
        }
    }
}
</script>

<style lang="scss">
    .printTemplate__table.packingBySerial {
        min-height: 38rem;

        .tb_no{
            width: 4%;
        }
        .tb_sku{
            width: 15%;
        }
        .tb_kode{
            width: 15%;
        }
        .tb_nama{
            width: 20%;
        }
    }

    @media print {
        .printTemplate__table.packingBySerial {
            min-height: 123rem;
        }
    }
</style>