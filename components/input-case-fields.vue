<template>
    <div class="row">

        <div class="col-md-6" style="padding-left: 2em;">
            <input-case-field v-bind:i="this.case_index" f="case_number">What was the case number?
                <template slot="help">
                    The best way to find your case number is by....
                </template>
            </input-case-field>
            <input-case-field v-bind:i="this.case_index" f="agency">Was the court a Missouri circuit (county) court
                or a municipal (city) court?
            </input-case-field>
            <input-case-field v-bind:i="this.case_index" f="city_county">What was the name of the County or City?
            </input-case-field>
            <input-case-field v-bind:i="this.case_index" f="name_of_judge">What was the name of the Judge?
            </input-case-field>

        </div>
        <div class="col-md-6" style="padding-left: 2em;">

            <input-case-field v-bind:i="this.case_index" f="your_name_in_case">What was your name as it appeared on
                the court’s records?
            </input-case-field>
            <input-case-field v-bind:i="this.case_index" f="release_status">Release Status</input-case-field>
            <input-case-field v-bind:i="this.case_index" f="release_date">Release Date</input-case-field>

        </div>


        <div class="col-md-12" style="padding-left: 2em; padding-top:3em;">

            <h4>CHARGE(S)</h4>

            <input-charge-fields v-for="(charge, charge_index) in this.ccase.charges" :key="charge.id"
                                 :charge_index="charge_index" :charge="charge"
                                 :case_index="0"
            >
            </input-charge-fields>


            <add-charge v-bind:case_index="this.case_index"></add-charge>
        </div>

    </div>

</template>

<script>
    import Charges from "./charges";
    import InputCaseField from "./input-case-field";
    import InputChargeFields from "./input-charge-fields";
    import AddCharge from "./add-charge";

    export default {
        components: {AddCharge, InputChargeFields, Charges, InputCaseField},
        name: "input-case-fields",
        props: {
            ccase: {
                type: Object,
                default: {},
            },
            case_index: {
                type: [Number, String],
                default: 0
            }

        },
    }
</script>

