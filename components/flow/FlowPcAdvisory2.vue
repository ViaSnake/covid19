<template>
  <div :class="$style.FlowComponent">
    <div :class="[$style.SubtleBox, $style.Box1, $style.Center]">
      <div :class="$style.LargerText">
        {{ $t('一般相談') }}
        <span :class="$style.SmallerText">({{ $t('コールセンター') }})</span>
      </div>
      <div :class="$style.SmallerText">
        {{ $t('平日：午前8時30分から午後9時') }}<br />
        {{ $t('土日祝日：午前8時30分から午後5時15分') }}
      </div>

      <div :class="$style.Tel">
        <a :class="$style.TelLink" href="tel:0120-567-177">
          <img
            :class="$style.TelLinkIcon"
            src="/flow/phone-24px.svg"
            aria-hidden="true"
          />
          0120-567-177
        </a>
      </div>
      <span :class="$style.SmallerText">
        {{ $t('耳の不自由な方') }}
      </span>
      <span :class="$style.LargerText">
        {{ $t('FAX 024-521-7926') }}
      </span>
    </div>
  </div>
</template>

<style module lang="scss">
.FlowComponent {
  color: $gray-2;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.Tel {
  @include largerThan($medium) {
    font-size: larger;
  }
}
.TelLink {
  display: flex;
  align-items: center;
  font-weight: bold;
  &:link,
  &:visited,
  &:hover,
  &:active,
  &:focus {
    color: inherit;
    text-decoration: none;
  }
  &Icon {
    display: inline-block;
    margin-right: 5px;
    width: 26px;
    height: 26px;
  }
}

.SubtleBox {
  @include card-container();

  display: flex;
  justify-content: space-evenly;
  align-items: center;
  padding: 0.5em;
}

.Box1 {
  flex-grow: 0;
  flex-shrink: 0;
  width: 100%;
  flex-direction: column;
  justify-content: center;
  div {
    margin: 0.5em;
  }
  &Icon {
    position: absolute;
    bottom: 40%;
    right: -30px;
    z-index: 1;
    display: block;
    width: 46px;
    height: 46px;
  }
}

.LargerText {
  font-size: larger;
  font-weight: bold;
}

.Center {
  text-align: center;
}

.SmallerText {
  font-size: smaller;
}
</style>
