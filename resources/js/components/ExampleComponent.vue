<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Example Component</div>

                    <div class="card-body">
                        I'm an example component.
                        <v-client-table :columns="columns" :data="data" :options="options">
                            <!-- <a slot="uri" slot-scope="props" target="_blank" :href="props.row.uri" class="glyphicon glyphicon-eye-open"></a> -->

                        </v-client-table>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                columns: ['code', 'qty', 'country_name', 'item_code', 'item_desc', 'product_type', 'grade', 'connection', 'size'],
                data: []
            }
        },
        mounted() {
            // console.log('Component mounted.');
            axios.get('/api/data').then((response) => {
                this.data = response.data;
                console.log('test.');
            });
        }
    }
</script>
