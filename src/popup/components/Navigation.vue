<template>
  <nav>
    <ul>
      <li class="divider"></li>
      <router-link to="/streams" tag="li" data-testid="navigation-stream">Stream</router-link>
      <li class="divider"></li>
      <li class="icon">
        <a href="https://twitter.com/SolaryTV" target="_blank" title="Twitter" data-testid="socials-twitter">
          <icon name="twitter"></icon>
        </a>
      </li>
      <li class="icon">
        <a
          href="https://www.youtube.com/channel/UCb3c6rB0Ru1i9EUcc-a5ZJw"
          target="_blank"
          title="YouTube"
          data-testid="socials-youtube"
        >
          <icon name="youtube"></icon>
        </a>
      </li>
      <li class="icon">
        <a href="https://www.twitch.tv/solary" target="_blank" title="Twitch" data-testid="socials-twitch">
          <icon name="twitch"></icon>
        </a>
      </li>
      <li class="icon">
        <a href="https://www.snapchat.com/add/solarytv" target="_blank" title="SnapChat" data-testid="socials-snapchat">
          <icon name="snapchat"></icon>
        </a>
      </li>
      <li class="icon">
        <a href="https://www.instagram.com/solarytv/" target="_blank" title="Instagram" data-testid="socials-instagram">
          <icon name="instagram"></icon>
        </a>
      </li>
      <li class="icon">
        <a href="https://www.facebook.com/SolaryTV/" target="_blank" title="Facebook" data-testid="socials-facebook">
          <icon name="facebook"></icon>
        </a>
      </li>
      <li class="divider"></li>
      <li title="Paramètres" @click="openOptionsPage">
        <icon name="gear"></icon>
      </li>
      <li class="divider"></li>
    </ul>
  </nav>
</template>

<script>
export default {
  methods: {
    openOptionsPage() {
      chrome.runtime.openOptionsPage();
    },
  },
};
</script>

<style scoped lang="scss">
$padding-y: 6px;
$padding-x: 12px;

ul {
  display: flex;
  margin: 0;
  padding: 0;

  border-style: solid;
  border-width: 4px 0 0;
  border-color: #1b1c1d;
}

li {
  padding: $padding-y $padding-x;
  font-size: 2rem;
  background-color: #1b1c1d;
  list-style: none;
  text-transform: uppercase;

  transition: all 0.1s linear;

  svg {
    fill: #fff;
  }

  &:hover svg,
  &.router-link-active svg {
    fill: rgba(0, 0, 0, 0.9);
  }

  &.icon {
    padding: 0;

    & > a {
      display: block;
      padding: $padding-y $padding-x;
    }
  }

  &:nth-child(3) {
    flex: 1;
  }
}

li:not(.divider) {
  cursor: pointer;
}

li.router-link-active,
li:not(.divider):hover {
  background-color: transparent;
}
</style>
