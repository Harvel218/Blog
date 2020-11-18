<template>
  <div class="website_container">
    <header>
      <nav class="website_navigation">
        <input class="navigation_item" type="text" value="" placeholder="Search.."></input>
        <article class="navigation_item">
          <NuxtLink to="/">Blog</NuxtLink>
        </article>
        <article class="navigation_item">
          <NuxtLink to="/about">About</NuxtLink>
        </article>
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
  overflow: hidden;

  & .website_container {
    min-width: 330px;
    width: 100%;
    max-width: 820px;
    height: 100vh;
    margin: 0 auto;

    & header {
      & .website_navigation {
        width: 100%;
        height: 70px;
        display: flex;
        justify-content: flex-end;
        align-items: center;

        & input {
          border-radius: 5px;
          outline: none;
          border: 3px solid #dedede;
          background-color: #f5f5f5;
          width: 120px !important;
        }

        & .navigation_item {
          width: 75px;
          height: 35px;
          margin-right: 15px;

          & a {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            height: 100%;
            background-color: cornsilk;
            border-radius: 5px;

            &.nuxt-link-active {
              background-color: orange;
            }
          }
        }
      }
    }
  }
}
</style>
