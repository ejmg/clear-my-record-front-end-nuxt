<template>
<div style="padding-top: 3em;">
    <h2>Review Case and Charges</h2>

    <cases v-for="ccase in this.$store.getters.allCases" :key="ccase.id"  :ccase="ccase">

    </cases>

</div>
</template>

<script>
    import Cases from "../components/cases";
    export default {
        name: "section-work-sheet",
        components: {Cases},
    }
</script>


