<template>
    <div class="printTemplate">
        <b-container fluid>
            <b-row>
                <b-col class="printTemplate__title">
                    <h1 >Invoice Return Supplier</h1>
                </b-col>
                <b-col class="text-right pr-0">
                    <b-button class="btn-warning btn-lg px-5 no-print" onclick="window.print()">Print</b-button>
                </b-col>
            </b-row>
            <b-row class="printTemplate__header">
                <b-col cols="4">
                    <b-row>
                        <b-col cols="4" class="label">
                            <h3>No. Retur</h3>
                        </b-col>
                        <b-col cols="8">
                            <h3><small>: RB-200003</small></h3>
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
                <b-col cols="5">
                    <b-row>
                        <b-col cols="5" class="label">
                            <h3>PPN</h3>
                        </b-col>
                        <b-col cols="7">
                            <h3><small>:</small> YES</h3>
                        </b-col>
                        <b-col cols="5" class="label">
                            <h3>Supplier</h3>
                        </b-col>
                        <b-col cols="7">
                            <h3><small>: 0003 - Schumm PLC</small></h3>
                        </b-col>
                        <b-col cols="5" class="label">
                            <h3>No. Ref Supplier</h3>
                        </b-col>
                        <b-col cols="7">
                            <h3><small>: 1321332</small></h3>
                        </b-col>
                    </b-row>
                </b-col>
                <b-col cols="3">
                    <b-row>
                        <b-col cols="12">
                            <h3>Catatan :</h3>
                        </b-col>
                        <b-col cols="12" class="border border-dark" style="height: 4.5rem;"></b-col>
                    </b-row>
                </b-col>
            </b-row>
            <b-row class="printTemplate__table invoiceReturnSupplier">
                <b-table 
                    :items="invoiceReturnSupplier_contents" 
                    :fields="invoiceReturnSupplier_fields"
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
                <b-col cols="12" class="printTemplate__footer-grandTotal">
                    <b-col cols="5" offset="7" >
                        <b-row>
                            <b-col cols="5" class="text-right"><h3>Subtotal</h3></b-col>
                            <b-col cols="6"><h3>: Rp.0</h3></b-col>
                            <b-col cols="5" class="text-right"><h3>PPN</h3></b-col>
                            <b-col cols="6"><h3>: Rp. 0</h3></b-col>
                            <b-col cols="5" class="text-right"><h1>Grand Total</h1></b-col>
                            <b-col cols="6"><h3 class="d-inline">: </h3><h1 class="d-inline">Rp. 0</h1></b-col>
                        </b-row>
                    </b-col>
                </b-col>
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
            // invoiceReturnSupplier_fields: [
            //     'no', 'kode', {'SKU': {'class' : 'tb_sku'}}, 'warna', 'sisa_qty', 'qty', 'total_qty', 'harga_satuan', 'potongan', 'total_harga', 'nilai_PPN', 'total_harga_+_PPN'
            // ],
            invoiceReturnSupplier_fields: [
                'no', {'kode': {'class' : 'tb_kode'}}, {'nama': {'class' : 'tb_nama'}}, 'qty(PCS)','harga_satuan', 'total_harga', 'nilai_PPN', 'total_harga_+_PPN'
            ],
            invoiceReturnSupplier_contents: []
        }
    }
}
</script>

<style lang="scss">
    .printTemplate__table.invoiceReturnSupplier {
        min-height: 18rem;

        .tb_kode{
            width: 20%;
        }
        .tb_nama{
            width: 20%;
        }
    }

    @media print {
        .printTemplate__table.invoiceReturnSupplier {
            min-height: 104rem;
        }
    }
</style>