<template>
    <div>
        <div class="packingBySerial">
            <b-row>
                <b-col>
                    <h1 class="font-weight-bold">SO Pending</h1>
                </b-col>
            </b-row>
            <b-row class="packingBySerial__header">
                <b-col cols="6">
                    <b-row>
                        <b-col cols="4">
                            Sales Order No
                        </b-col>
                        <b-col cols="6">
                            : SA-20060590
                        </b-col>
                    </b-row>
                    <b-row>
                        <b-col cols="4">
                            Date
                        </b-col>
                        <b-col cols="6">
                            : 14/06/2020
                        </b-col>
                    </b-row>
                </b-col>
                <b-col cols="6">
                    <b-row>
                        <b-col cols="5" offset="7">
                            Customer <span class="ml-5">:</span>
                        </b-col>                  
                    </b-row>
                    <b-row>
                        <b-col cols="5" offset="7">
                            ACC Toys Pengadilan
                        </b-col>                      
                    </b-row>
                </b-col>
            </b-row>

            <b-row class="mt-3">
                <b-col>
                    <b-table 
                    :items="packingBySerial_contents" 
                    :fields="packingBySerial_fields"
                    show-empty
                    class="text-center"
                    >
                    <template v-slot:cell(no)="row">
                        {{row.item.no}}
                    </template>
                    </b-table>
                </b-col>
            </b-row>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            packingBySerial_fields: [
                {'no':{'class' : 'tb_no'}}, 
                {'SKU':{'class' : 'tb_sku'}}, 
                {'code':{'class' : 'tb_code'}}, 
                {'nama':{'class' : 'tb_code'}}, 
                {'qty_order':{'class' : 'tb_qty'}}, 
                {'qty_sold':{'class' : 'tb_qty'}}, 
                {'qty':{'class' : 'tb_qty'}}, 
                {'STOCK':{'class' : 'tb_qty'}}, 
                {'status':{'class' : 'tb_qty'}}],

            packingBySerial_contents: [
                {
                    no: 1,
                    SKU: '|||||||||||||||||||',
                    code: 'LS-LT-2',
                    nama: 'Sports Car Police Tarik (Opp)',
                    qty_order: '2.00 PCS',
                    qty_sold: '00  -',
                    qty: '2',
                    STOCK: '250 250',
                    status: 'Pending'
                }
            ]
        }
    }
}
</script>

<style lang="scss">
    .packingBySerial{

        &__header{
            font-size: 1.5rem;
            font-weight: 700;
        }
        
        table{
            font-size: 1.2rem;
            .tb_no{
                max-width: .5rem;
            }
            .tb_sku{
                min-width: 8rem;
            }
            .tb_code{
                min-width: 8rem;
            }
            .tb_nama{
                min-width: 8rem;
            }
            .tb_qty{
                max-width: 4rem;
            }
        }
    }
</style>