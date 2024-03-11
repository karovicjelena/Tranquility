<!--Profile Page-->
<script>
    import Littlegirl from '../components/Littlegirl.svelte';
    import LogInModal from './LogInModal.svelte';
    import { navigate } from 'svelte-routing'; // or your choice of routing library

  let showLogIn = false;

  // This function will be triggered when the loggedIn event is dispatched
  function handleLoggedIn() {
    navigate('/main'); // replace with your actual route
  }

</script>

<div class="relative">
    <div class="fixed w-full bg-white bg-opacity-75 backdrop-filter z-10">
      <div class="flex items-center px-4 py-2">
        <Littlegirl class="mr-4 w-12 h-12"/>
        <span class="text-5xl font-bold text-black font-sunrise">Tranquility</span>
      </div>
    </div>
  </div>
  <div class="pt-20"> <!-- Adjust the top padding as needed -->
    <div class="bg-[url('love2.png')] min-h-screen bg-cover bg-center flex flex-col items-center text-center">
    </div>
  </div>

  <LogInModal showLogIn={showLogIn} on:closeModal={() => showLogIn = false} on:loggedIn={handleLoggedIn} />