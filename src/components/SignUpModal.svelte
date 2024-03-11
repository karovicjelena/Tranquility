<script>
    import { createEventDispatcher } from 'svelte';
  
    export let showSignUp = false;
    const dispatch = createEventDispatcher();
  
    function closeHandler() {
      dispatch('closeModal');
    }

    function openLogIn() {
        dispatch('openLogIn'); // Dispatch custom event
    }
</script>
  
  {#if showSignUp}
  <div class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center">
    <div role="dialog" aria-modal="true" class="bg-white p-6 rounded-md space-y-4 w-full max-w-4xl">
      <h2 class="text-2xl font-bold">Sign Up</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
        <!-- First Name -->
        <div>
          <label for="first-name" class="block font-medium text-gray-700">First Name</label>
          <input type="text" id="first-name" placeholder="John" class="w-full p-2 border rounded" />
        </div>
  
        <!-- Last Name -->
        <div>
          <label for="last-name" class="block font-medium text-gray-700">Last Name</label>
          <input type="text" id="last-name" placeholder="Smith" class="w-full p-2 border rounded"/>
        </div>
        <!--User Name -->
        <div>
            <label for="username" class="block font-medium text-gray-700"></label>
        </div>
        <!-- Email Address -->
        <div>
          <label for="email-address" class="block font-medium text-gray-700">Email Address</label>
          <input type="email" id="email-address" placeholder="johnsmith@example.com" class="w-full p-2 border rounded"/>
        </div>
        
  
        <!-- Password -->
        <div>
          <label for="password" class="block font-medium text-gray-700">Password</label>
          <input type="password" id="password" placeholder="••••••••" class="w-full p-2 border rounded" />
        </div>
  
        <!-- Confirm Password -->
        <div>
          <label for="confirm-password" class="block font-medium text-gray-700">Confirm Password</label>
          <input type="password" id="confirm-password" placeholder="••••••••" class="w-full p-2 border rounded"/>
        </div>
  
        <!-- Empty div for alignment -->
        <div></div>
      </div>
  

        <div class="flex justify-end space-x-2">
          <button class="bg-gray-300 hover:bg-gray-400 text-black font-bold py-2 px-4 rounded" on:click={closeHandler}>Cancel</button>
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
        </div>
        <p class="text-center text-lg">
            Already have an account?
            <!-- Dispatch an event to open the log in modal -->
            <button
              class="font-medium text-indigo-500 underline-offset-4 hover:underline"
              on:click={openLogIn}
            >Log in</button>
        </p>
      </div>
    </div>
  {/if}
  