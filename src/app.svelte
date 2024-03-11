<script>
    import { Router, Route } from 'svelte-routing';
    import HomePage from './HomePage.svelte';
    import MainPage from './MainPage.svelte';
    

  </script>
  
  <Router>
    <Route path="/" component={HomePage} />
    <Route path="/main" component={MainPage} />
  </Router>
  