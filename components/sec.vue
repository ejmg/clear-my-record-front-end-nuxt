<template>
    <div class="container">
        <div class="row mt-4 mb-4">
            <div class="col-md-3 col-lg-3">
                <slot name="title"></slot>
            </div>
            <div class="col-md-9 col-lg-9">
                <slot></slot>
            </div>
        </div>
        <div class="row mb-4">
            <div class="col-6">
                <nuxt-link v-if="this.previous" class="btn btn-secondary btn-sm"
                           :to="this.previous">Previous page
                </nuxt-link>
            </div>
            <div class="col-6 ">
                <nuxt-link v-if="this.next" class="btn btn-primary btn-sm float-right"
                           :to="this.next">Next Page
                </nuxt-link>
            </div>

        </div>
        <div class="row">
            <slot name="note"></slot>
        </div>
    </div>
</template>

<script>
    export default {
        name: "sec",
        props: {
            previous: {
                type: String,
                default: '',
            },
            next: {
                type: String,
                default: '',
            },

        }
    }
</script>

