<template>
  <div class="website_container">
    <header>
      <nav class="website_navigation">
        <div class="search_box">
          <input type="text" value="" placeholder="Search for anything.." />
          <button type="button">&#10095;</button>
        </div>
      </nav>
    </header>
    <Nuxt />
  </div>
</template>

<style lang="scss">
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

a,
p,
h1,
h2,
h3,
h4,
h5,
div,
article,
section,
main,
footer,
nav,
span {
  text-decoration: none;
  color: black;
}

body {
  margin: 0;
  padding: 0;
  min-width: 100vw;
  width: 100vw;
  max-width: 100vw;
  min-height: 100vh;
  height: auto;
  overflow-x: hidden;

  & .website_container {
    min-width: 330px;
    width: 100%;
    max-width: 820px;
    height: 120vh;
    margin: 0 auto;

    & header {
      width: 100%;
      height: 50px;
      position: relative;

      & .website_navigation {
        width: 100%;
        height: 50px;
        max-width: 820px;
        display: flex;
        justify-content: flex-end;
        align-items: center;
        position: fixed;
        top: 0;

        & .search_box {
          display: flex;
          flex-direction: wrap;
          flex-wrap: nowrap;
          justify-content: flex-end;
          align-items: center;
          min-width: 185px;
          width: 70%;
          max-width: 500px;
          margin-right: 20px;

          & input {
            border-radius: 5px 0 0 5px;
            outline: none;
            border: 2px solid #dedede;
            background-color: #fff;
            min-width: 150px;
            width: calc(100% - 30px);
            max-width: 475px;
            height: 39px;
            font-size: 16.5px;
            color: #dedede;

            &::placeholder {
              padding-left: 10px;
              color: #dedede;
            }
          }

          & button {
            height: 39px;
            width: 30px;
            border-top: 2px solid #dedede;
            border-right: 2px solid #dedede;
            border-bottom: 2px solid #dedede;
            border-left: none;
            outline: none;
            background-color: #dedede;
            font-size: 30px;
            font-weight: bold;
            color: #fff;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
          }
        }
      }
    }
  }
}
</style>
