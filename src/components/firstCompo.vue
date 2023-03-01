<template>
    <div>
        <h1>my first compo</h1>
        <h3>helllo {{person.fname}} {{person.lname}}</h3>
    </div>
</template>
<script>

export default ({
    name: "FirstCompo",
    props: ["person"]
    // props: {
    //     fname: String,
    //     lname: String
    // } // if you want to do validation, you can do like this
})
</script>
