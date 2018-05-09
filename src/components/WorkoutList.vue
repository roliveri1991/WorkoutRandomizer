<<template>
    <div>
    <h2>{{ category }}</h2>
        <ul>
            <li v-for="workout in workouts">
                {{ workout.name }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'WorkoutList',
  props: {
      workouts: Array,
      category: String
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: bolder;
}
ul {
    list-style-type: none;
    align-content: flex-start;
}
div{
    align-content: flex-start;
}
</style>