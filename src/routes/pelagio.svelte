<script>
  let active = "dashboard";

  const menuItems = [
    { id: "dashboard", label: "Dashboard" },
    { id: "inventory", label: "Inventory" },
    { id: "borrowed", label: "Borrowed" },
    { id: "reports", label: "Reports" }
  ];
</script>

<div class="layout">

  <!-- Sidebar -->
  <aside class="sidebar">
    <div class="logo">iReply Inventory System</div>

    {#each menuItems as item}
      <div class="menu-item {active === item.id ? 'active' : ''}">
        {item.label}
      </div>
    {/each}
  </aside>

  <!-- Main -->
  <div class="main">

    <!-- Header -->
    <header class="header">
      <h1>Dashboard</h1>
    </header>

    <!-- Content -->
    <div class="content">

      {#if active === "dashboard"}
        <div class="cards">
          <div class="card">
            <h3>Total Devices</h3>
            <p class="number">0</p>
            <span class="label">No devices added yet</span>
          </div>

          <div class="card">
            <h3>Available Devices</h3>
            <p class="number">0</p>
            <span class="label">Inventory is empty</span>
          </div>

          <div class="card">
            <h3>Borrowed Devices</h3>
            <p class="number">0</p>
            <span class="label">No borrowed records</span>
          </div>
        </div>

        <div class="empty-state">
          <h2>Welcome to Your Inventory Dashboard</h2>
          <p>
            You currently have no device records.
          </p>
        </div>
      {/if}

      {#if active === "inventory"}
        <h2 class="section-title">Device Inventory</h2>
        <div class="table-placeholder">
          <p>No inventory records yet.</p>
        </div>
      {/if}

      {#if active === "borrowed"}
        <h2 class="section-title">Borrowed Devices</h2>
        <div class="table-placeholder">
          <p>No borrowed devices yet.</p>
        </div>
      {/if}

      {#if active === "reports"}
        <h2 class="section-title">Reports & Analytics</h2>
        <div class="table-placeholder">
          <p>No reports available. Data will appear once inventory is added.</p>
        </div>
      {/if}

    </div>
  </div>
</div>

<style>
  :global(body) {
    margin: 0;
    font-family: "Segoe UI", sans-serif;
  }

  .layout {
    display: flex;
    height: 100vh;
    background: #f4f8fc;
    color: #1a1a1a;
  }

  /* Sidebar */
  .sidebar {
    width: 240px;
    background: #0b3c5d;
    color: white;
    padding: 25px 0;
    display: flex;
    flex-direction: column;
  }

  .logo {
    text-align: center;
    font-weight: 600;
    font-size: 18px;
    margin-bottom: 30px;
  }

  .menu-item {
    padding: 14px 25px;
    font-size: 15px;
    color: white;
  }

  .menu-item.active {
    background: #1e81b0;
    font-weight: 600;
  }

  /* Main content */
  .main {
    flex: 1;
    display: flex;
    flex-direction: column;
  }

  /* Header */
  .header {
    height: 65px;
    background: #1e81b0;
    color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 30px;
  }

  /* Content */
  .content {
    padding: 30px;
    flex: 1;
    overflow-y: auto;
  }

  .section-title {
    margin-bottom: 15px;
    color: #0b3c5d;
  }

  /* Cards */
  .cards {
    display: flex;
    gap: 25px;
    margin-bottom: 40px;
  }

  .card {
    background: white;
    padding: 25px;
    border-radius: 12px;
    flex: 1;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.06);
    text-align: center;
  }

  .card h3 {
    margin-bottom: 10px;
    color: #0b3c5d;
  }

  .number {
    font-size: 32px;
    font-weight: bold;
    color: #1e81b0;
    margin: 0;
  }

  .label {
    font-size: 13px;
    color: #6c7a89;
  }

  /* Empty state */
  .empty-state {
    background: white;
    padding: 40px;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.06);
  }

  .empty-state h2 {
    margin-bottom: 10px;
    color: #0b3c5d;
  }

  .empty-state p {
    color: #555;
    margin-bottom: 20px;
  }

  /* Table placeholder */
  .table-placeholder {
    margin-top: 20px;
    background: white;
    padding: 40px;
    border-radius: 10px;
    text-align: center;
    color: #666;
    box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  }
</style>