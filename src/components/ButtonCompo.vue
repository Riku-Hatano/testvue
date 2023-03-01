<template>
    <div>
        <div @click="showMsg">button</div>
        <h4>welcome {{buttonPerson}}</h4>
    </div>
</template>
<script>

export default({
    name: "ButtonCompo",
    props: ["person"],
    data() {
        return {
            buttonPerson: ""
        }
    },
    methods: {
        showMsg() {
            // this.buttonPerson = person
        }
    }
})
</script>
