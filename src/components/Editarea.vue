<template>
  <div id="Editarea">
    <div class="items">
      <ol>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-idcard"></use>
          </svg> 
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-company"></use>
          </svg> 
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-books"></use>
          </svg> 
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-works"></use>
          </svg> 
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-honor"></use>
          </svg> 
        </li>
        <li>
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-phone"></use>
          </svg> 
        </li>
      </ol>
    </div>
    <div class="contents"></div>
  </div>
</template>

<script>
</script>

<style lang="scss">
#Editarea {
  display: flex;
  height: inherit;
  width: 30%;
  .items {
    background: #f0f9eb;
    li {
      &:hover {
        background: #67c23a;
        .icon {
          fill: #ffffff;
        }
      }
      padding: 24px;
      .icon {
        fill: #67c23a;
        width: 2em;
        height: 2em;
      }
    }
  }
}
</style>
