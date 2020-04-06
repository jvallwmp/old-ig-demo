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