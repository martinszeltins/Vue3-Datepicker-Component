<template>
    <div style="position: absolute; left: 500px; top: 200px;">
        <datepicker v-model="selected" />
    </div>

    <div style="position: absolute; left: 200px; top: 50px;">
        <dropdown-menu
            v-model="show">

            <button @click="show = !show">
                Click to open dropdown
            </button>

            <template v-slot:dropdown>
                <datepicker v-model="selected" />
            </template>
        </dropdown-menu>
    </div>

    <div style="position: absolute; left: 800px; top: 600px;">
        <dropdown-menu
            v-model="show2">

            <button @click="show2 = !show2">
                Click to open dropdown
            </button>

            <template v-slot:dropdown>
                <div class="menu-wrapper">
                    <div>Action</div>
                    <div>Another action</div>
                    <div>Something else here blah blah blah</div>
                    <div>Something else here</div>
                    <div>Something else here</div>
                    <div>Something else here</div>
                </div>
            </template>
        </dropdown-menu>
    </div>
</template>

<script>
    import { ref } from 'vue'
    import DropdownMenu from './components/DropdownMenu.vue'
    import Datepicker from './components/datepicker/Datepicker.vue'

    export default {
        components: { DropdownMenu, Datepicker },

        setup()
        {
            const show = ref(false)
            const selected = ref(null)

            const show2 = ref(false)
            const selected2 = ref(null)

            return { show, selected, show2, selected2 }
        },
    }
</script>

<style>
    .menu-wrapper {
        background: black;
        color: #fff;
    }
</style>