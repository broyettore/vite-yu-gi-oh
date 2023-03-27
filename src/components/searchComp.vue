<script>
export default {
    name: "selectComponent"
}
</script>

<template>
    <div class="container mb-3">
        <select class="form-select ms-select" aria-label="Default select example">
            <option selected>---</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
    </select>
    </div>
</template>

<style lang="scss" scoped>

.ms-select {
    width: 20%;
}
</style>