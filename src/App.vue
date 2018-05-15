<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div id="workouts">
      <WorkoutList v-bind:workouts="chestWorkouts" category="Chest"/>
      <WorkoutList v-bind:workouts="backWorkouts" category="Back"/>
      <WorkoutList v-bind:workouts="shoulderWorkouts" category="Shoulders"/>
      <WorkoutList v-bind:workouts="legWorkouts" category="Legs"/>
      <WorkoutList v-bind:workouts="accessoryWorkouts" category="Accessory"/>
    </div>
      <RandomButton :onClick="randomizeWorkout" msg="Randomize Workout"/>
      <p/>
      {{ randomWorkouts }}
  </div>
</template>

<script>
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
        ],
        legWorkouts: [
          {name: 'Barbell Back Squat'},
          {name: 'Barbell Front Squat'},
          {name: 'Goblet Squat - Dumbbell'},
          {name: 'Goblet Squat - Kettlebell'},
          {name: 'Barbell Lunge'},
          {name: 'Stiff Leg Barbell Deadlift'},
          {name: 'Single Leg Kettlebell Deadlift'},
          {name: 'Kettlebell Pistol Squat'},
          {name: 'Power Cleans'},
          {name: 'Goblet Lunge - Dumbbell'},
          {name: 'Goblet Lunge - Kettlebell'},
          {name: 'Kettlebell Lunge'},
          {name: 'Box Squats'},
          {name: 'Dumbbell Crossover Step Up'},
          {name: 'Kettlebell Overhead Squat'},
          {name: 'Barbell Overhead Squat'}
        ],
        accessoryWorkouts: [
          {name: 'Kettlebell Turkish Getups'},
          {name: 'Medice Ball Crunches'},
          {name: 'Planks'},
          {name: 'EZ Bar Curl'},
          {name: 'Dumbbell Curl'},
          {name: 'Single Arm High Cable Curl'},
          {name: 'Cable Curl'},
          {name: 'Rope Push Down'},
          {name: 'Dumbbell Tricep Extension'},
          {name: 'Skull Crushers'},
          {name: 'Dips'}
        ],
      randomWorkouts: ''
    }
  },
  methods: {
    randomizeWorkout() {
      var chestWorkout = this.getRandomWorkout(this.chestWorkouts);
      var backWorkout = this.getRandomWorkout(this.backWorkouts);
      var shoulderWorkout = this.getRandomWorkout(this.shoulderWorkouts);
      var legWorkout = this.getRandomWorkout(this.legWorkouts);
      var accessoryWorkout = this.getRandomWorkout(this.accessoryWorkouts);
      this.randomWorkouts = chestWorkout.name + ' | ' + backWorkout.name + ' | ' + shoulderWorkout.name + ' | ' + legWorkout.name + ' | ' + accessoryWorkout.name;
    },
    getRandomWorkout(workoutList){
      var int = Math.floor(Math.random() * workoutList.length);
      var workout = workoutList[int];
      if (!workout){
        debugger
      }
      return workout; 
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
