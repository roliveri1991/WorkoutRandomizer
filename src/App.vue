<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div id="workouts">
      <WorkoutList v-bind:workouts="chestWorkouts" category="Chest"/>
      <WorkoutList v-bind:workouts="backWorkouts" category="Back"/>
      <WorkoutList v-bind:workouts="shoulderWorkouts" category="Shoulders"/>
    </div>
      <RandomButton msg="Randomize Workout"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import RandomButton from './components/RandomButton.vue'
import WorkoutList from './components/WorkoutList.vue'

export default {
  name: 'app',
  components: {
    WorkoutList,
    RandomButton
  },
  data() {
    return {
      chestWorkouts: [
            {name: 'Flat Barbell Bench'},
            {name: 'Incline Barbell Bench'},
            {name: 'Flat Dumbbell Bench'},
            {name: 'Incline Dumbbell Bench'},
            {name: 'Decline Dumbbell Bench'},
            {name: 'Flat Dumbbell Flys'},
            {name: 'Incline Dumbbell Flys'},
            {name: 'Decline Dumbell Flys'},
            {name: 'Cable Crossover Flys'},
            {name: 'Push Ups'},
            {name: 'Dumbbell Floor Press'}
        ],
      backWorkouts: [
            {name: 'Barbell Rows'},
            {name: 'Cable Rows'},
            {name: 'Single Arm Cable Rows'},
            {name: 'Pull Ups'},
            {name: 'Deadlifts'},
            {name: 'Alternating Kettlebell Rows'},
            {name: 'Dumbbell Rows'},
            {name: 'Cable Face Pulls'},
            {name: 'Kettlebell Swings'},
            {name: 'Yates Row'},
            {name: 'Straight Arm Pulldown'},
            {name: 'Single Arm Seated Cable Lat Row'}
      ],
      shoulderWorkouts: [
            {name: 'Barbell Overhead Press'},
            {name: 'Dumbbell Press'},
            {name: 'Arnold Press'},
            {name: 'Lateral Dumbbell Raises'},
            {name: 'Front Dumbbell Raises'},
            {name: 'Lateral Cable Raises'},
            {name: 'Front Cable Raises'},
            {name: 'Kettlebell Press'},
            {name: 'Kettlebell Halos'},
            {name: 'Dumbbell Shrugs'},
            {name: 'Kettlebell Snatch'},
            {name: 'Dumbbell Shoulder Complex'},
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#workouts{
display: flex;
}
</style>
