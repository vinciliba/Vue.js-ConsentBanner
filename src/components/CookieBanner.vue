<template>
  <div class="modal" id="modal">
    <div class="header">
      <h2>Your privacy matters</h2>
    </div>
    <div class="content">
      <p>
        That's where we come in! This is the
        <a href="#/">"This Web Site"</a> CMP, where you can control how your
        data is collected and processed. We work with some of the world's
        largest brands to not only comply with data protection laws but also
        provide their users with transparency around their data choices.
      </p>
      <p>
        With your consent, "This Web Site" and our
        <a href="#/">partners</a> would like to use cookies stored on your
        device and process personal data, such as IP addresses or browsing
        history to understand you as a user, improve your experience on our
        website, and show you personalized ads.
      </p>
      <p>
        Click AGREE to consent to all processing purposes at once. Click into
        OPTIONS to reject all data processing, customize your preferences
        further, or object to processing based on legitimate interest.
      </p>
      <p>
        If at any point you want to surface this message again to edit your
        preferences, you can do so through the Privacy Settings link in our
        footer.
      </p>
    </div>

    <div class="wrap-collabsible">
      <input id="collapsible" class="toggle" type="checkbox" />
      <label for="collapsible" class="lbl-toggle"
        >Store and/or access information</label
      >
      <div class="collapsible-content">
        <div class="content-inner">
          <p>
            Cookies, device identifiers, or other information can be stored or
            accessed on your device for the purposes presented to you.
          </p>
        </div>
      </div>
    </div>

    <div class="wrap-collabsible-2">
      <input id="collapsible-2" class="toggle-2" type="checkbox" />
      <label for="collapsible-2" class="lbl-toggle-2">
        Personalised ads and content,and content measurement,audience insights
        and product development
      </label>
      <div class="collapsible-content-2">
        <div class="content-inner-2">
          <p>
            Ads and content can be personalised based on a profile. More data
            can be added to better personalise ads and content. Ad and content
            performance can be measured. Insights about audiences who saw the
            ads and content can be derived. Data can be used to build or improve
            user experience, systems and software.
          </p>
        </div>
      </div>
    </div>

    <div class="privacyPolicy">
      <p><a href="#/">Privacy Policy</a></p>
    </div>
    <div class="actions">
      <button class="accept">Accept</button>
      <button class="options">Options</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "CookieBanner",
};
</script>

<style lang="scss">
.modal {
  position: relative;
  margin-left: auto;
  margin-right: auto;
  margin-top: 20rem;
  width: 500px;
  height: auto;
  background: white;
  border: 1px solid #ccc;
  transition: 1.1s ease-out;
  box-shadow: -2rem 2rem 2rem rgba(black, 0.2);
  filter: blur(0);
  transform: scale(1);
  opacity: 1;
  visibility: visible;
  &.red {
    background: black;
    color: red;
  }
  &.blue {
    background: blue;
    color: red;
  }
  &.off {
    opacity: 0;
    visibility: hidden;
    filter: blur(8px);
    transform: scale(0.33);
    box-shadow: 1rem 0 0 rgba(black, 0.2);
  }
  @supports (offset-rotate: 0deg) {
    offset-rotate: 0deg;
    offset-path: path("M 250,100 S -300,500 -700,-200");
    &.off {
      offset-distance: 100%;
    }
  }
  @media (prefers-reduced-motion) {
    offset-path: none;
  }
  .content {
    padding: 1rem;
    text-align: left;
  }
  .header {
    background: #0069ff;
    h2 {
      border-bottom: 1px solid #ccc;
      padding: 1rem;
      margin: 0;
      color: #ffffff;
      text-align: center;
    }
  }
  .actions {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 2fr;
    gap: 0px 20px;
    grid-template-areas: "one two ";
    justify-items: stretch;
    align-items: stretch;
    border-top: 1px solid #ccc;
    background: #eee;
    padding: 0.5rem 1rem;

    button {
      box-sizing: border-box;
      display: inline-block;
      min-width: 164px;
      padding: 11px 15px 10px 10px;
      border-radius: 2px;
      text-decoration: none;
      text-align: center;
      font-family: "CeraPRO-Regular", sans-serif, arial;
      font-weight: normal;
      font-size: 16px;
      line-height: 20px;
      &.accept {
        background-color: #0069ff;
        color: #FFF;
        grid-area: one;
        &:hover {
          background-color: #20BA68;
        }
      }
      &.options {
        background-color: transparent;
        color: #000000;
        grid-area: two;
        &:hover {
          background-color: #0069ff;
          border-color: #838F93;
          color: #ffffff;
        }
      }
    }
  }
  .privacyPolicy {
    text-align: center;
    color: #0069ff;
    font-weight: bold;
  }
  input[type="checkbox"] {
    display: none;
  }
  .wrap-collabsible {
    margin: 1.2rem 0;
    .lbl-toggle {
      display: flex;
      align-items: flex-end;
      align-content: flex-end;
      font-weight: italic;
      font-family: monospace;
      font-size: 1rem;
      //text-transform: uppercase;
      text-align: center;
      padding: 1rem;
      color: #DDD;
      background: #0069ff;
      cursor: pointer;
      border-radius: 0px;
      transition: all 0.25s ease-out;
    }
    .lbl-toggle:hover {
      color: #FFF;
    }
    .lbl-toggle::before {
      content: " ";
      display: inline-block;
      border-top: 5px solid transparent;
      border-bottom: 5px solid transparent;
      border-left: 5px solid currentColor;
      vertical-align: middle;
      margin-right: 0.7rem;
      transform: translateY(-2px);
      transition: transform 0.2s ease-out;
    }
    .toggle:checked + .lbl-toggle::before {
      transform: rotate(90deg) translateX(-3px);
    }
    .collapsible-content {
      max-height: 0px;
      overflow: hidden;
      transition: max-height 0.25s ease-in-out;
    }
    .toggle:checked + .lbl-toggle + .collapsible-content {
      max-height: 350px;
    }
    .toggle:checked + .lbl-toggle {
      border-bottom-right-radius: 0;
      border-bottom-left-radius: 0;
    }
    .collapsible-content .content-inner {
      background: rgba(0, 105, 255, 0.2);
      border-bottom: 1px solid rgba(0, 105, 255, 0.45);
      border-bottom-left-radius: 0px;
      border-bottom-right-radius: 0px;
      padding: 0.5rem 1rem;
    }
    .collapsible-content p {
      margin-bottom: 0;
    }
  }

  .wrap-collabsible-2 {
    margin: 1.2rem 0;
    .lbl-toggle-2 {
      display: flex;
      align-items: center;
      align-content: flex-end;
      font-weight: italic;
      font-family: monospace;
      font-size: 1rem;
      //text-transform: uppercase;
      text-align: left;
      padding: 1rem;
      color: #DDD;
      background: #0069ff;
      cursor: pointer;
      border-radius: 0px;
      transition: all 0.25s ease-out;
    }
    .lbl-toggle-2:hover {
      color: #FFF;
    }
    .lbl-toggle-2::before {
      content: " ";
      display: inline-block;
      border-top: 5px solid transparent;
      border-bottom: 5px solid transparent;
      border-left: 5px solid currentColor;
      vertical-align: middle;
      margin-right: 0.7rem;
      transform: translateY(-2px);
      transition: transform 0.2s ease-out;
    }
    .toggle-2:checked + .lbl-toggle-2::before {
      transform: rotate(90deg) translateX(-3px);
    }
    .collapsible-content-2 {
      max-height: 0px;
      overflow: hidden;
      transition: max-height 0.25s ease-in-out;
    }
    .toggle-2:checked + .lbl-toggle-2 + .collapsible-content-2 {
      max-height: 350px;
    }
    .toggle-2:checked + .lbl-toggle-2 {
      border-bottom-right-radius: 0;
      border-bottom-left-radius: 0;
    }
    .collapsible-content-2 .content-inner-2 {
      background: rgba(0, 105, 255, 0.2);
      border-bottom: 1px solid rgba(0, 105, 255, 0.45);
      border-bottom-left-radius: 0px;
      border-bottom-right-radius: 0px;
      padding: 0.5rem 1rem;
    }
    .collapsible-content-2 p {
      margin-bottom: 0;
    }
  }
}
</style>