<template>
    <h2>{{num1}} {{operate}} {{num2}} = {{result}}</h2>
</template>
<script>

export default ({
    props:["num1", "num2", "operate", "result"],
    name: "CalResultCompo",
})
</script>
