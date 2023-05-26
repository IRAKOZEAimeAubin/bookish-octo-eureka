<template>
    <div class="fixed bg-black/50 w-full h-full z-20 left-0 top-0" @click.self="closeModal">
        <div class="absolute bg-white top-1/2 left-1/2  transform -translate-x-1/2 -translate-y-1/2 p-12 rounded-lg flex flex-col gap-6 justify-center text-center" :class="{'bg-slate-950': theme==='dark'}">
            <slot></slot>
            <div class="flex gap-2 justify-center">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Modal",
    props: [ "theme" ],
    methods: {
        closeModal () {
            this.$emit( "close" )
        }
    }
}
</script>