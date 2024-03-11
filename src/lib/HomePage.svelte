<!-- HomePage.svelte -->
<script>
    import { navigate } from 'svelte-routing';
    import Littlegirl from '../components/Littlegirl.svelte';
    import SignUpModal from '../components/SignUpModal.svelte';
    import LogInModal from '../components/LogInModal.svelte';
    

  
    let showSignUp = false;
    let showLogIn = false;
  
    // Function to close modals
    function closeModal() {
      showSignUp = false;
      showLogIn = false;
    }
    // Function to listen for the custom event from SignUpModal
    function handleOpenLogIn() {
        showSignUp = false; 
        showLogIn = true;  
    }
    function handleLoggedIn() {
    navigate('/main'); // Navigate to MainPage when the user logs in
  }

  
  </script>
  
  <!-- Header with buttons -->
  <div class="relative">
    <div class="fixed w-full bg-white bg-opacity-75 backdrop-filter z-10">
      <div class="flex items-center justify-between px-4 py-2">
        <div class="flex items-center">
          <Littlegirl class="mr-4 w-12 h-12"/>
          <span class="text-5xl font-sunrise text-black">Tranquility</span>
        </div>
        <div class="flex space-x-3">
          <button class="bg-purple-400 text-white font-bold py-2 px-4 rounded hover:bg-purple-600 transition duration-300" on:click="{() => showSignUp = true}">Sign Up</button>
          <button class="bg-blue-400 text-white font-bold py-2 px-4 rounded hover:bg-blue-600 transition duration-300" on:click="{() => showLogIn = true}">Log In</button>
        </div>
      </div>
    </div>
</div>

    <!-- Content starts below the fixed header -->
    <div class="pt-20"> 
        <div class="bg-[url('love2.png')] min-h-screen bg-cover bg-center flex flex-col items-center text-center">
            
            <!-- First "paper" section -->
            <div class="bg-white bg-opacity-75 p-6 mx-auto max-w-4xl rounded-full shadow-lg my-5 text-gray-800">
                <h2 class="text-4xl font-sunrise mb-5">What is Tranquility?</h2>
                <p class="text-lg mb-6">
                    Imagine a place where your thoughts can roam free, and an AI, let's call it your digital confidante, is there to listen. That's Tranquility for you - a digital journal with a twist of AI empathy.
                </p>
            </div>
            
            <!-- Second "paper" section -->
            <div class="bg-white bg-opacity-75 p-6 mx-auto max-w-4xl rounded-full shadow-lg my-5 text-gray-800">
                <h2 class="text-4xl font-sunrise mb-4">How it works?</h2>
                <p class="text-lg">
                    It's simple. You talk, we listen. You type in your daily musings, your victories, your defeats, and our AI, equipped with virtual ears and a heart, provides a response. It's like having a chat with an old friend who's really good at nodding and giving you virtual pats on the back.
                </p>
            </div>

            <!-- Third "paper" section -->
            <div class="bg-white bg-opacity-75 p-6 mx-auto max-w-4xl rounded-full shadow-lg my-5 text-gray-800">
                <h2 class="text-4xl font-sunrise mb-4">A Friendly Heads-Up!</h2>
                <p class="text-lg">
                    While Tranquility is a great listener and loves to chat about your day, it's important to remember that it's more of a digital journal than a digital psychologist. Our AI is designed to provide responses based on empathy and understanding, not professional mental health advice.
                    Think of it as a diary that writes back. It's here to provide comfort and a space to reflect, but it's not a substitute for professional help. So, if your challenges feel heavier than a backpack filled with textbooks, we encourage seeking support from a qualified professional.
                </p>
            </div>
        </div>
    </div>    
<!-- Buttons -->

  <SignUpModal {showSignUp} on:closeModal={closeModal} on:openLogIn={handleOpenLogIn} />
  <LogInModal {showLogIn} on:closeModal={closeModal} on:loggedIn={handleLoggedIn} />


