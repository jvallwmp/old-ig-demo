# Steps for Remaking Instagram

0. Clone repository, widths/heights on `html`/`body` are 100%, `margin: 0` set on `body`

1. Make body background color:

  `background-color: #fafafa;`

  Make page layout a grid, 2 rows and and 3 columns:

  ```
    .page-shell {
      width: 100%;
      height: 100%;
      display: grid;
      grid-template-columns: 1fr auto max-content;
      grid-template-rows: 56px 1fr;
    }
  ```

  Point out that the center column's width will always be fit to its content (615px cards), the right column takes up whatever it can, fitting its content, and the left column takes up whatever space is left.

  Make topbar shell:

  ```
  .topbar {
    grid-column: 1 / span 3;
    background-color: #fff;
    border-bottom: 1px solid rgb(219, 219, 219);
  }
  ```

  Make content containers: 

  .posts-container {
    grid-column-start: 2;
  }

  .stories-container {
    grid-column-start: 3;
  }

  Add elements to DOM:
  ```
  <main class="page-shell">
    <section class="topbar"></section>
    <section class="posts-container"></section>
    <section class="stories-container"></section>
  </main>
  ```

2. Add topbar elements:

  There are multiple ways to lay this out. I'll use flexbox.
  
  ```
  .topbar-content {
    width: 915px;
    height: 100%;
    margin: 0 auto;

    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  <div class="topbar-content">
    
  </div>
  ```

  And the rest of the code:
  
  ```
  .searchbox {
    background-color: #fafafa;
    border: 1px solid #dbdbdb;
    padding: 3px 10px;
    height: 20px;
    border-radius: 5px;
  }

  .icons-box > img {
    cursor: pointer;
    width: 22px;
    height: 22px;
  }

  .icons-box > img:not(:last-child) {
    margin-right: 22px;
  }

  .profile-icon {
    border-radius: 50%;
    width: 50px;
    height: 50px;
  }

  .profile-icon.sm {
    width: 22px;
    height: 22px;
  }
  ```

  ```
  <div class="topbar-content">
  <img src="icons/iglogo.png" />
  <input placeholder="Search..." class="searchbox" type="text" />
  <div class="icons-box">
    <img src="icons/home.svg" />
    <img src="icons/paperplane.svg" />
    <img src="icons/compass.svg" />
    <img src="icons/heart.svg" />
    <img class="profile-icon sm" src="images/jvall.jpg" />
  </div>
  ```
