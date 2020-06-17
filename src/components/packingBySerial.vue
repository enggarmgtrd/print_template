<template>
    <div>
        <div class="packingBySerial">
            <b-row>
                <b-col>
                    <h1 class="font-weight-bold">Packing By Serial</h1>
                </b-col>
            </b-row>
            <b-row class="packingBySerial__header">
                <b-col cols="6">
                    <b-row>
                        <b-col cols="4">
                            Packing No
                        </b-col>
                        <b-col cols="6">
                            : PS-20060590
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
                        <b-col cols="4" offset="3">
                            Customer
                        </b-col>
                        <b-col cols="5">
                            : ACC Toys Pengadilan
                        </b-col>
                    </b-row>
                    <b-row>
                        <b-col cols="4" offset="3">
                            Sales Order
                        </b-col>
                        <b-col cols="5">
                            : SA-200050159
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
                {'item_no':{'class' : 'tb_sku'}}, 
                {'code':{'class' : 'tb_code'}}, 
                {'nama':{'class' : 'tb_code'}}, 
                {'serial_box_no':{'class' : 'tb_sku'}}, 
                {'qty':{'class' : 'tb_qty'}}, 
                {'check':{'class' : 'tb_qty'}}
            ],
            packingBySerial_contents: [
                {
                    no: 1,
                    item_no: 'SKU-18002083',
                    code: 'LS-LT-2',
                    nama: 'Sports Car Police Tarik (Opp)',
                    serial_box_no: 2000000061892,
                    qty: '4 PCS',
                    check: '-'
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