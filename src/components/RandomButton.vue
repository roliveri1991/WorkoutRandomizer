<<template>
  <button>
      {{ msg }}
  </button>
</template>

<script>
export default {
  name: 'RandomButton',
  props: {
    msg: String
  }
}
</script>
