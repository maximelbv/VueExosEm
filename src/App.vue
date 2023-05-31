<script>
import ProfileAvatar from './components/Avatar.vue';
import ProfileCard from './components/ProfileCard.vue';
import InputSpinner from './components/InputSpinner.vue';

  export default {
    name: 'App',
    components: {
      ProfileAvatar,
      ProfileCard,
      InputSpinner
    },
    data() {
      return {
        avatars: [
          { name: 'Ricky', image: 'https://picsum.photos/id/154/200', badgeColor: '#06d6a0' },
          { name: 'Elise', image: 'https://picsum.photos/id/24/200', badgeColor: '#ef233c' },
          { name: 'Elon', image: 'https://picsum.photos/id/387/200' }
        ],
        users: [
          {
            name: 'Ricky Park',
            city: 'Paris',
            occupation: 'Front-end developer',
            image: 'https://picsum.photos/id/367/200',
            status: 'pro',
            skills: ['HTML', 'CSS', 'Javascript']
          },
          {
            name: 'Jean neige',
            city: 'Montréal',
            occupation: 'UX designer',
            image: 'https://picsum.photos/id/347/200',
            status: '',
            skills: ['Figma', 'Photoshop', 'Illustrator']
          }
        ]
      }
    }
  }

  

</script>

<template>
  <div :style="{ display: 'flex', flexDirection: 'column', alignItems: 'center' }">

    <div :style="{ display: 'flex' }">
      <ProfileAvatar v-for="a in avatars" :key="a.name" :name="a.name" :image="a.image" :badgeColor="a.badgeColor" />
    </div>

    <div :style="{display: 'flex'}">
      <ProfileCard 
        v-for="u in users" 
        :key="u.name" 
        :name="u.name" 
        :city="u.city" 
        :occupation="u.occupation" 
        :image="u.image" 
        :status="u.status"
        :skills="u.skills" 
      />
    </div>

    <InputSpinner />

  </div>


</template>

<style>
  h1 {
    font-family: Arial, Helvetica, sans-serif;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>