<template>
    <div class="container">
        <div class="row">
            <div class="col-md-12">
                <router-view v-slot="{ Component }">
                    <transition name="fade" mode="out-in">
                        <component :is="Component" />
                    </transition>
                </router-view>
            </div>
        </div>
        <!-- <div class="row">
            <div class="col-md-6">
                <div class="box" :class="{ animate: animate }"></div>
                <div class="my-3">
                    <button
                        class="btn btn-primary"
                        @click.prevent="onAnimateClick()"
                    >
                        Click Me
                    </button>
                </div>
                <div class="my-3">
                    <animate-button></animate-button>
                </div>

                <div class="my-3">
                    <the-paragraph></the-paragraph>
                </div>
                <div class="my-3">
                    <animate-paragraph></animate-paragraph>
                </div>

                <div class="my-3">
                    <dialog-modal :open="openDialog">
                        <div>This is the Dialog Modal</div>
                        <div class="my-3">
                            <button
                                class="btn btn-primary"
                                @click.prevent="openDialog = false"
                            >
                                Okay!
                            </button>
                        </div>
                    </dialog-modal>

                    <div>
                        <button
                            @click.prevent="onOpenDialog()"
                            class="btn btn-primary"
                        >
                            Open Dialog Modal
                        </button>
                    </div>
                </div>
            </div>
            <div class="col-md-6">
                <div class="my-3">
                    <transition-events></transition-events>
                </div>
                <div class="my-3">
                    <list-data></list-data>
                </div>
            </div>
        </div> -->
    </div>
</template>

<script>
// import TheParagraph from './components/TheParagraph.vue';
// import AnimateParagraph from './components/AnimateParagraph.vue';
// import DialogModal from './components/DialogModal.vue';
// import AnimateButton from './components/AnimateButton.vue';
// import TransitionEvents from './components/TransitionEvents.vue';
// import ListData from './components/ListData.vue';
export default {
    data() {
        return {
            animate: false,
            openDialog: false,
        };
    },
    components: {
        // TheParagraph,
        // AnimateParagraph,
        // DialogModal,
        // AnimateButton,
        // TransitionEvents,
        // ListData,
    },
    methods: {
        onAnimateClick() {
            this.animate = true;
        },

        onOpenDialog() {
            this.openDialog = true;
        },
    },
};
</script>

<style>
.box {
    width: 100px;
    height: 100px;
    border: 1px solid red;
    background: red;
}

.animate {
    animation: animate-box 1s forwards;
}

@keyframes animate-box {
    0% {
        transform: translateX(0px) scaleX(1);
    }
    50% {
        transform: translateX(100px) scaleX(1.5);
    }
    100% {
        transform: translateX(200px) scaleX(1);
    }
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.fade-enter-to,
fade-leave-from {
    opacity: 1;
}
.fade-enter-active,
.fade-leave-active {
    transition: all 0.5s ease;
}
</style>
