<template>
  <div class="booking">
    <h3 class="booking__title">Make a Reservation</h3>
    <div class="booking__wrapper">
      <form class="booking__form">
        <div class="booking__form__section" id="pickup">
          <h4>Pickup</h4>
          <div class="booking__form__row">
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
          </div>
          <div class="booking__form__row">
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
          </div>
        </div>
        <div class="booking__form__section" id="drop-off">
          <h4>Drop-off</h4>
          <div class="booking__form__row">
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
          </div>
          <div class="booking__form__row">
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
            <div class="booking__form__item">
              <select>
                <option>Option 1</option>
                <option>Option 2</option>
              </select>
            </div>
          </div>
        </div>
        <div class="booking__form__section" id="submit">
          <div class="booking__form__item">
            <button type="submit" class="booking__form__button">Search</button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.booking {
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(5px);
  border-radius: $roundedCorners;
  max-width: 500px;
  overflow: hidden;

  &__title {
    background: $primary;
    color: white;
    font-size: 1.6rem;
    font-weight: 600;
    padding: 0.8rem;
    text-align: center;
  }

  &__wrapper {
    padding: 2rem;
  }

  &__form {
    &__section {
      padding: 1rem 0;

      &:not(:last-child) {
        border-bottom: 1px solid $primary;
      }

      h4 {
        font-size: 1.2rem;
        font-weight: 600;
      }
    }

    &__row {
      display: grid;
      grid-auto-flow: column;
      align-items: center;
      margin: 0.8rem 0;
      gap: 0.8rem;

      select {
        width: 100%;
      }
    }

    &__button {
      background: $secondary;
      appearance: none;
      border: none;
      color: white;
      padding: 0.6rem 1.4rem;
      font-family: inherit;
      font-size: 1.2rem;
      border-radius: $roundedCorners;
      margin: 20px 0 0 auto;
    }
  }
}
</style>
