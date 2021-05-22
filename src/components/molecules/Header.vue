<template>
  <header :class="$style.header">
    <div :class="$style.title">{{headerText}}</div>
    <div :class="$style.burger">
      <span></span>
    </div>
  </header>
</template>

<script>
export default {
	props: {
		headerText: String
	}
};
</script>

<style lang="scss" module>
.header {
  background: #000;
  padding: 20px;
  text-align: center;
  width: 100%;
  .title {
    color: #ffffff;
    font-size: 25px;
    letter-spacing: 1px;
  }
  .burger {
    display: none;
    position: absolute;
    top: 24px;
    right: 20px;
    width: 30px;
    height: 19px;
    cursor: pointer;
    @media (max-width: 1250px) {
      display: block;
    }
    &::before,
    &:after {
      content: "";
      background-color: #ffffff;
      position: absolute;
      width: 100%;
      height: 2px;
      right: 0;
      transition: all 0.3s ease 0s;
    }
    &:before {
      top: 0;
    }
    &:after {
      bottom: 0;
    }
    span {
      background-color: #ffffff;
      color: #ffffff;
      position: absolute;
      width: 100%;
      height: 2px;
      right: 0;
      top: 9px;
      transition: all 0.3s ease 0s;
    }
  }
  .burgerOpen:before {
    transform: rotate(45deg);
    top: 9px;
  }
  .burgerOpen:after {
    transform: rotate(-45deg);
    top: 9px;
  }
  .burger.burgerOpen span {
    transform: scale(0);
  }
}
</style>