<script>
    import Home from '../lib/components/Home.sveltete';
    import SessionList from '../lib/components/SessionList.sveltete';
    import SessionForm from '../lib/components/SessionForm.sveltete';
    import Stats from '../lib/components/Stats.sveltete';
  
    let activeTab = 'home';
  </script>
  
  <main>
    <header>
      <h1>Poker Tracker</h1>
      <nav>
        <button on:click={() => activeTab = 'home'}>Home</button>
        <button on:click={() => activeTab = 'sessions'}>Sessions</button>
        <button on:click={() => activeTab = 'new'}>New Session</button>
        <button on:click={() => activeTab = 'stats'}>Statistics</button>
      </nav>
    </header>
  
    <div class="content">
      {#if activeTab === 'home'}
        <Home />
      {:else if activeTab === 'sessions'}
        <SessionList />
      {:else if activeTab === 'new'}
        <SessionForm />
      {:else if activeTab === 'stats'}
        <Stats />
      {/if}
    </div>
  </main>
  