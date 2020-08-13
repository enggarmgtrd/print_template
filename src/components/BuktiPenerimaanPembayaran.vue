<template>
    <div class="printTemplate">
        <b-container fluid>
            <b-row>
                <b-col class="printTemplate__title">
                    <h1>Bukti Penerimaan Pembayaran</h1>
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
                            <h3><small>:</small> ARP-20084015</h3>
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
            <div class="BuktiPenerimaanPembayaran__content">
                <b-row>
                    <b-col class="text-center">
                        <h1>Terima Kasih Atas Pembayarannya</h1>
                        <h1>Kami Telah Menerima Sejumlah</h1>
                    </b-col>
                </b-row>
                <b-row>
                    <b-col cols="3" class=" py-2 text-center mx-auto my-3 bg-blue">
                        <h1>Rp. 9,861,900</h1>
                    </b-col>
                </b-row>
                <b-row>
                    <b-col class="text-center">
                        <h3>Metode Pembayaran :</h3>
                        <h1>Bank BCA-Non PPN</h1>
                    </b-col>
                </b-row>
            </div>
            <div  class="printTemplate__table BuktiPenerimaanPembayaran">
            <b-row>
                <b-col class="pl-0">
                    <h4>Detail Pembayaran</h4>
                </b-col>
                <b-table 
                    :items="BuktiPenerimaanPembayaran_contents" 
                    :fields="BuktiPenerimaanPembayaran_fields"
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
            </div>
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
            BuktiPenerimaanPembayaran_fields: [
                  {'no': {'class' : 'tb_no'}}, {'noInvoice': {'class' : 'tb_noInvoice'}}, {'tglKirim': {'class' : 'tb_tglKirim'}}, 'jatuh_tempo',{'total':{ 'class' : 'tb_total'}}, {'bayar':{ 'class' : 'tb_bayar'}}
            ],
            BuktiPenerimaanPembayaran_contents:[]
        }
    }
}
</script>

<style lang="scss">
    .BuktiPenerimaanPembayaran__content{
        margin: 10rem 0px;
    }
    .printTemplate__table.BuktiPenerimaanPembayaran {
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
            width: 20%;
        }
        .tb_bayar{
            width: 20%;
        }
        .tb_sisa{
            width: 15%;
        }
        
    }
    p{
        margin-bottom: 0px !important;
    }

    @media print {
        .printTemplate__table.BuktiPenerimaanPembayaran {
            min-height: 82rem;
        }
    }
</style>