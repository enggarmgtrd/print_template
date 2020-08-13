<template>
    <div class="printTemplate">
        <b-container fluid>
            <b-row>
                <b-col class="printTemplate__title">
                    <h1>Tanda Terima Bukti Piutang</h1>
                </b-col>
                <b-col class="text-right pr-0">
                    <b-button class="btn-warning btn-lg px-5 no-print" onclick="window.print()">Print</b-button>
                </b-col>
            </b-row>
            <b-row class="printTemplate__header">
                <b-col cols="4">
                    <b-row>
                        <b-col cols="4" class="label">
                            <h3>No.</h3>
                        </b-col>
                        <b-col cols="8">
                            <h3><small>: ECV-20084015</small></h3>
                        </b-col>
                        <b-col cols="4" class="label">
                            <h3>Tanggal</h3>
                        </b-col>
                        <b-col cols="8">
                            <h3><small>: 07/08/2020</small></h3>
                        </b-col>
                    </b-row>
                </b-col>
                <b-col cols="3" offset="5" class="pr-0">
                    <b-row>
                        <b-col cols="12">
                            <h3>Customer :</h3>
                        </b-col>
                    </b-row>
                    <b-row>
                        <b-col cols="12">
                            <h3>ACC Pengadilan</h3>
                        </b-col>
                    </b-row>
                </b-col>
            </b-row>
            <div  class="printTemplate__table TukarFaktur">
            <b-row>
                <b-table 
                    :items="TukarFaktur_contents" 
                    :fields="TukarFaktur_fields"
                    show-empty
                    class="text-center"
                    bordered="bordered"
                    >
                    <template v-slot:cell(no)="data">
                        {{data.index + 1}}
                    </template>
                </b-table>
            </b-row>
            <b-row class="mb-5">
                <b-col cols="5" offset="7" class="border border-dark py-2" style="margin-top: -11px;">
                    <b-row>
                        <b-col cols="5">
                            <h1>Grand Total</h1>
                        </b-col>
                        <b-col cols="7" class="text-right">
                            <h1>: Rp. 100.000.000</h1>
                        </b-col>
                    </b-row>
                </b-col>
            </b-row>
            <b-row class="mb-5">
                <b-col cols="12" class="border border-dark py-2 mb-3">
                    <h2 class="text-blue">Pembayaran Tunai</h2>
                    <h5>1. Wajib menggunakan Bukti Tanda Terima Pembayaran</h5>
                    <h5>2. Tanpa Tanda Terima, pembayaran di luar tanggung jawab</h5>
                </b-col>
                <b-col cols="12" class="border border-dark text-blue">
                    <h2>Pembayaran Transfer Giro/Cek, Ditujukan Kepada:</h2>
                </b-col>
                <b-col cols="4" class="border border-dark text-center">
                    <h3>BCA</h3>
                </b-col>
                <b-col cols="4" class="border border-dark text-center">
                    <h3>Mandiri</h3>
                </b-col>
                <b-col cols="4" class="border border-dark text-center">
                    <h3>BRI</h3>
                </b-col>
                <b-col cols="4" class="border border-dark text-center">
                    <h3>869 133 0 133</h3>
                </b-col>
                <b-col cols="4" class="border border-dark text-center">
                    <h3>157 000 6272 620</h3>
                </b-col>
                <b-col cols="4" class="border border-dark text-center">
                    <h3>1134 01 000 285 567</h3>
                </b-col>
                <b-col cols="12" class="border border-dark text-center">
                    <h3>a/n : PT. Mega Visi Prima Jaya</h3>
                </b-col>
            </b-row>
            </div>
            <b-row class="printTemplate__footer">
                <b-col cols="12" class="printTemplate__footer-signature">
                    <b-row>
                        <b-col cols="2" class="text-center">
                            <h4 style="margin-bottom: 10rem;">Hormat Kami</h4>
                            <h4>............................</h4>
                        </b-col>
                        <b-col cols="2" offset="3" class="text-center">
                            <h4 style="margin-bottom: 10rem;">Sales</h4>
                            <h4>............................</h4>
                        </b-col>
                        <b-col cols="2" offset="3" class="text-center">
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
            TukarFaktur_fields: [
                  {'no': {'class' : 'tb_no'}}, {'noInvoice': {'class' : 'tb_noInvoice'}}, {'tanggal_kirim': {'class' : 'tb_tglKirim'}},  {'jatuh_tempo': {'class' : 'tb_tglKirim'}},{'total':{ 'class' : 'tb_total'}}, {'bayar':{ 'class' : 'tb_bayar'}}, {'sisa':{ 'class' : 'tb_sisa'}}
            ],
            TukarFaktur_contents: []
        }
    }
}
</script>

<style lang="scss">
    .TukarFaktur__content{
        margin: 10rem 0px;
    }
    .printTemplate__table.TukarFaktur {
        min-height: 0px;

        .tb_no{
            width: 4%;
        }
        .tb_noInvoice{
            width: 15%;
        }
        .tb_tglKirim{
            width: 15%;
        }
        .tb_total{
            width: 15%;
        }
        .tb_bayar{
            width: 15%;
        }
        .tb_sisa{
            width: 15%;
        }
        
    }
    p{
        margin-bottom: 0px !important;
    }

    @media print {
        .printTemplate__table.TukarFaktur {
            min-height: 119rem;
        }
    }
</style>