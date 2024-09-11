<script>
    let darkMode = false;
  
    const toggleDarkMode = () => {
      darkMode = !darkMode;
      document.body.classList.toggle('dark', darkMode);
    };
  </script>
  
  <div class="topbar">
    <div class="logo">Squad 1E</div>
    <div class="switch">
      <input id="switch-1" type="checkbox" on:change={toggleDarkMode} checked={darkMode} />
      <label for="switch-1"></label>
    </div>
  </div>
  
  <style>
   :root {
    --primary-light: #8abdff;
    --primary: #6d5dfc;
    --greyLight-1: #e4ebf5;
    --greyLight-2: #c8d0e7;
    --greyDark: #9baacf;
    --white: #ffffff;
  }
  
    .topbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem;
      background-color: var(--background-color);
      color: var(--text-color);
    }
  
    .logo {
      font-size: 1.5rem;
      font-weight: bold;
    }
  
    .switch {
      width: 6rem;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  
    input {
      display: none;
    }
  
    label {
      width: 100%;
      height: 3rem;
      border-radius: 1.6rem;
      background: rgba(255, 255, 255, 0);
      box-shadow: 0.3rem 0.3rem 0.6rem var(--greyLight-2), -0.2rem -0.2rem 0.5rem var(--white);
      position: relative;
      cursor: pointer;
      display: flex;
      align-items: center;
    }
  
    label::after {
      content: "";
      position: absolute;
      left: 0.4rem;
      width: 2.1rem;
      height: 2.1rem;
      border-radius: 50%;
      background: var(--greyDark);
      transition: all 0.4s ease;
    }
  
    label::before {
      content: '';
      width: 100%;
      height: 100%;
      border-radius: inherit;
      background: linear-gradient(330deg, var(--primary-dark), var(--primary), var(--primary-light));
      opacity: 0;
      transition: all 0.4s ease;
    }
  
    input:checked + label::before {
      opacity: 1;
    }
  
    input:checked + label::after {
      left: 57%;
      background: var(--greyLight-1);
    }
  
    /* Light mode styles */
    :global(body) {
      --background-color: #d9d9d9;
      --text-color: #000;
    }
  
    /* Dark mode styles */
    :global(body.dark) {
      --background-color: #5f0cbc;
      --text-color: #fff;
    }
  </style>