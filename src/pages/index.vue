<template>
  <div class="d-flex flex-column">
    <div class="section-page" id="home">
      <v-container class="section-page section-page-1">
        <p class="section-page-1-message">
          Turning Miles into Smiles: Elevating Your Travel Experience with
          Punctuality, Reliability, and a Commitment to Safety, only in V&A
          taxi.
        </p>
        <v-btn
          height="60"
          min-width="180"
          elevation="0"
          color="#e0dc00"
          href="tel:(914)564-0279"
        >
          Call now!
        </v-btn>
      </v-container>
    </div>
    <div class="section-page section-page-2" id="new-rochelle">
      <v-container class="container-custom">
        <p class="section-page-2-message">
          Situated in New Rochelle, our base serves as a strategic hub for
          seamless transportation services. From this central location, we
          extend our commitment to providing hassle-free rides, ensuring that
          clients experience convenience and comfort from the moment they book
          with us.
        </p>
        <v-btn href="tel:(914)564-0279" height="60" min-width="180" elevation="0" color="#e0dc00">
          Book now!
        </v-btn>
      </v-container>
    </div>
    <div class="section-page section-page-3" id="westchester">
      <v-container class="container-custom">
        <p class="section-page-3-message">
          Westchester Premier Transportation Service – Punctual, Reliable, and
          Committed to Your Security.
        </p>
        <v-btn href="tel:(914)564-0279" height="60" min-width="180" elevation="0" color="#e0dc00">
          Make a reservation
        </v-btn>
      </v-container>
    </div>
    <div class="section-page section-page-4" id="long-distance">
      <v-container class="container-custom">
        <p class="section-page-4-message">
          Turning Miles into Smiles Across The States – Your Trusted Partner for
          Long-Distance Journeys, Delivering Unmatched Reliability, Punctuality,
          and a Firm Commitment to Your Safety.
        </p>
        <v-btn href="tel:(914)564-0279" height="60" min-width="180" elevation="0" color="#e0dc00">
          Give us a call!
        </v-btn>
      </v-container>
    </div>
    <div class="section-page section-page-5" id="to-the-airport">
      <v-container class="container-custom">
        <p class="section-page-5-message">
          Your hassle-free transport to JFK, La Guardia, Newark, and more
          airports worldwide.
        </p>
        <v-btn href="tel:(914)564-0279" height="60" min-width="180" elevation="0" color="#e0dc00">
          Make a reservation
        </v-btn>
      </v-container>
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>

<style lang="scss">
.section-page {
  display: flex;
  font-size: 40px;
  .v-btn {
    text-transform: none;
    font-size: 22px;
    color: #0b2345 !important;
    font-weight: 800;
    letter-spacing: normal;
  }
  .container-custom {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }
  &-1 {
    margin-top: 180px;
    width: 100%;
    height: calc(100vh - 38px);
    display: flex;
    flex-direction: column;
    align-items: flex-end;

    align-items: center;
    &-message {
      text-align: center;
      font-weight: 700;
      color: #ffffff;
      margin-bottom: 48px !important;
    }
  }
  &-2 {
    height: 100vh;
    background-color: #0b2345;
    width: 100%;
    align-items: center;
    &-message {
      text-align: center;
      font-weight: 700;
      color: #ffffff;
      margin-bottom: 48px !important;
    }
  }
  &-3 {
    height: 100vh;
    background-color: #8d8d8d;
    width: 100%;
    align-items: center;
    &-message {
      text-align: center;
      font-weight: 700;
      color: #ffffff;
      margin-bottom: 48px !important;
    }
  }
  &-4 {
    height: 100vh;
    background-color: #0b2345;
    width: 100%;
    align-items: center;
    &-message {
      text-align: center;
      font-weight: 700;
      color: #ffffff;
      margin-bottom: 48px !important;
    }
  }
  &-5 {
    height: 100vh;
    background-color: #8d8d8d;
    width: 100%;
    align-items: center;
    &-message {
      text-align: center;
      font-weight: 700;
      color: #ffffff;
      margin-bottom: 48px !important;
    }
  }
}

@media (max-width: 600px) {
  .section-page {
    font-size: 22px;
    .container-custom {
      align-items: center;
    }
    &-1 {
      justify-content: center;
    }
  }
}
</style>
