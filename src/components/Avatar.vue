<script>
    export default {
        name: 'ProfileAvatar',
        props: {
            name: {
                type: String,
                required: false,
                default: 'anonyme',
                validator: (value) => {
                    return value.length > 3;
                }
            },
            badgeColor: {
                type: String,
                required: false,
                default: 'grey'
            },
            image: {
                type: String,
                required: false,
                default: 'https://placehold.co/400'
            },
        }
    }
</script>

<style>
    * {
        color: white;
    }
</style>

<template >
    <div :style="{ position: 'relative', display: 'inline-flex', flexDirection: 'column', alignItems: 'center',  marginLeft: '20px' }">
        <img :style="{ borderRadius: '50%', width: '75px' }" :src="image" alt="image">
        <div :style="{ position: 'absolute', bottom: '45px', right: '-5px', background: badgeColor, height: '20px', width: '20px', borderRadius: '50%' }"></div>
        <p :style="{marginTop: '10px'}">{{ name }}</p>
    </div>
</template>