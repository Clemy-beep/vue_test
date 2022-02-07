<template>
  <div class="login">
    <h1>This is the login page.</h1>
    <form action="" method="post" @submit="checkForm">
        <!-- <p v-if="errors.lenght">
            <b>Please correct the following errors :</b>
            <ul>
                <li v-for="error in errors" :key="error.id">{{error}}</li>
            </ul>
        </p> -->
      <p>
        <label for="movie">Favourite movie</label>
        <select name="movie" id="movie" v-model="movie">
          <option value="starwars">Star Wars</option>
          <option value="fightclub">Fight Club</option>
        </select>
      </p>
      <p>
        <label for="firstname">First Name</label>
        <input
          type="text"
          name="firstname"
          id="firstname"
          v-model="firstname"
        />
      </p>
      <p>
        <label for="lastname">Lastname</label>
        <input type="text" name="lastname" id="lastname" v-model="lastname" />
      </p>
    </form>
  </div>
</template>

<script>
    
</script>