<script setup lang="ts">
import { ref, reactive } from 'vue';

//Adres en contactgegevens
const inputfieldFirstName = ref();
const inputfieldPrefix = ref();
const inputfieldLastName = ref();
const inputfieldGender = ref();
const inputfieldBirthDate = ref();
const inputfieldSocialNumb = ref();
//Gekozen pakket
const inputfieldBasisverzekering = ref();

const invalid = ref(true);

const inputfieldEigenrisico = ref()
const optionsEigenrisico = ref([
    { text: 'Geen eigenrisico geselecteerd'},
  { text: ' € 385 - verplicht eigen risico', value: 385 },
  { text: '€ 885 - korting van € 22 per jaar', value: 885 },
])


const inputfieldAanvullendeverzekering = ref();
const optionsAanvullendeverzekering= ref([
  { text: 'Geen aanvullende geselecteerd'},
  { text: 'Aanvullend 1 - € 21,38 per jaar', value: 21.38 },
  { text: 'Aanvullend 2 - € 85,06 per jaar', value: 85.06 },
  { text: 'Aanvullend 3 - € 198,63 per jaar', value: 198.63 },
  { text: 'Aanvullend 4 - € 359,73 per jaar', value: 359.73 },
])



const inputfieldTandverzekering = ref();
const optionsTandverzekering= ref([
  { text: 'Geen tandartsverzekering geselecteerd'},
  { text: 'Tand 1 - € 80,28 per jaar', value: 80.28 },
  { text: 'Tand 2 - € 221,65 per jaar', value: 221.65 },
  { text: 'Tand 3 - € 449,36 per jaa', value: 449.36 },
])
//Totaalpremie
const inputfieldBetaaltermijn = ref();
const optionsBetaaltermijn= ref([
  { text: 'Geen betaaltermijn geselecteerd'},
  { text: 'per maand', value: 'per maand' },
  { text: 'per kwartaal', value: 'per kwartaal' },
  { text: 'per jaar', value: 'per jaar' },
])


//const inputfieldTotaalpremie = ref();
const inputfieldTotaalpremie = reactive({
    total1: inputfieldEigenrisico,
    total2: inputfieldAanvullendeverzekering,
    total3: inputfieldTandverzekering
})

function validation(event:any) {
  if (event.target.value == "") {
    console.log("empty")
    invalid.value = true
  }else{
    console.log(event.target.tagName )
    invalid.value = false
  }
}


</script>
<template>
    <div id="app" class="main-placeholder">
        <!-- HEADER -->
        <header class="nav-main" id="nav-main" aria-label="navigatie-header">
            <div class="nav-main__skip-links mb-3">
                <a
                    href="#navigatie-overslaan"
                    class="list__link link--no-underline"
                >
                    Navigatie overslaan
                </a>
            </div>
            <div class="nav-main__grid container">
                <!--LOGO-->
                <a href="/consumenten" class="nav-main__logo">
                    <img
                        class="nav-main__logo-img"
                        src="https://www.zilverenkruis.nl/assets/zilverenkruis/img/logo/logo_zilverenkruis.svg"
                        alt="Zilveren Kruis raad en daad logo"
                    />
                </a>
                <div class="nav-main__top-selections">
                    <a
                        href="/zakelijk"
                        class="nav-main__desktop link link--no-underline nav-main__desktop"
                    >
                        Zakelijk
                    </a>
                    <a
                        href="/zorgaanbieders"
                        class="nav-main__desktop link link--no-underline nav-main__desktop"
                    >
                        Voor zorgaanbieders
                    </a>
                    <a
                        href="/overons"
                        class="nav-main__desktop link link--no-underline nav-main__mobile"
                    >
                        Over ons
                    </a>
                    <a
                        href="/overons/pers"
                        class="nav-main__desktop link link--no-underline nav-main__mobile"
                    >
                        Pers
                    </a>
                </div>
                <nav
                    class="nav-main__main-menu"
                    role="navigation"
                    aria-label="hoofdnavigatie"
                >
                    <ul
                        class="main-menu__list list list--nostyle"
                        id="main-menu__list"
                    >
                        <li class="main-menu__item" data-has-section="false">
                            <a
                                href="/consumenten"
                                class="main-menu__title link--no-underline"
                                title="Naar de homepage van Zilveren Kruis voor consumenten"
                            >
                                Home
                            </a>
                        </li>
                        <li
                            class="main-menu__item"
                            data-has-section="true"
                            data-section-count="3"
                        >
                            <a
                                href="#"
                                class="main-menu__title link--no-underline"
                                aria-haspopup="true"
                                aria-expanded="false"
                            >
                                Verzekeringen
                            </a>
                        </li>
                        <li
                            class="main-menu__item"
                            data-has-section="true"
                            data-section-count="2"
                        >
                            <a
                                href="#"
                                class="main-menu__title link--no-underline"
                                aria-haspopup="true"
                                aria-expanded="false"
                            >
                                Vergoedingen
                            </a>
                        </li>
                        <li
                            class="main-menu__item"
                            data-has-section="true"
                            data-section-count="2"
                        >
                            <a
                                href="#"
                                class="main-menu__title link--no-underline"
                                aria-haspopup="true"
                                aria-expanded="false"
                            >
                                Zorg regelen
                            </a>
                        </li>
                        <li
                            class="main-menu__item"
                            data-has-section="true"
                            data-section-count="1"
                        >
                            <a
                                href="#"
                                class="main-menu__title link--no-underline"
                                aria-haspopup="true"
                                aria-expanded="false"
                            >
                                Betalen
                            </a>
                        </li>
                        <li
                            class="main-menu__item"
                            data-has-section="true"
                            data-section-count="2"
                        >
                            <a
                                href="#"
                                class="main-menu__title link--no-underline"
                                aria-haspopup="true"
                                aria-expanded="false"
                            >
                                Gezonder leven
                            </a>
                        </li>
                        <li
                            class="main-menu__item"
                            data-has-section="true"
                            data-section-count="1"
                        >
                            <a
                                href="#"
                                class="main-menu__title link--no-underline"
                                aria-haspopup="true"
                                aria-expanded="false"
                            >
                                Service &amp; Contact
                            </a>
                        </li>
                        <li
                            class="main-menu__item nav-main__mobile"
                            data-has-section="false"
                        >
                            <a
                                href="/zakelijk"
                                class="main-menu__title link--no-underline nav-main__desktop"
                            >
                                Zakelijk
                            </a>
                        </li>
                        <li
                            class="main-menu__item nav-main__mobile"
                            data-has-section="false"
                        >
                            <a
                                href="/zorgaanbieders"
                                class="main-menu__title link--no-underline nav-main__desktop"
                            >
                                Voor zorgaanbieders
                            </a>
                        </li>
                        <li
                            class="main-menu__item nav-main__mobile"
                            data-has-section="false"
                        >
                            <a
                                href="https://www.zilverenkruis.nl/en/consumenten"
                                class="main-menu__title link--no-underline"
                            >
                                English
                            </a>
                        </li>
                        <li
                            class="main-menu__item nav-main__mobile"
                            data-has-section="false"
                        >
                            <a
                                href="/overons"
                                class="main-menu__title link--no-underline nav-main__mobile"
                            >
                                Over ons
                            </a>
                        </li>
                        <li
                            class="main-menu__item nav-main__mobile"
                            data-has-section="false"
                        >
                            <a
                                href="/overons/pers"
                                class="main-menu__title link--no-underline nav-main__mobile"
                            >
                                Pers
                            </a>
                        </li>
                    </ul>
                </nav>
            </div>
            <a
                id="navigatie-overslaan"
                name="navigatie-overslaan"
                tabindex="-1"
            ></a>
        </header>

        <!-- CONTENT HERE -->
        <div class="container my-3">
            <div class="row">
                <div class="col-8">
                    <h1>Aanmelden</h1>

                    <h2>Gegevens</h2>
                    <div class="form-group">
                        <h3>Reden van aanmelding</h3>
                        <div class="form-input my-4">
                            <label id="aanmeldreden-label" class="input__title">
                                Wat is de reden van uw aanvraag?
                            </label>
                            <div class="input__group">
                                <select class="form-control">
                                    <option>
                                        Nieuwe werkgever met collectiviteit bij
                                        Zilveren Kruis
                                    </option>
                                    <option selected>
                                        Overstappen per 1-1-2023 naar Zilveren
                                        Kruis
                                    </option>
                                </select>
                            </div>
                        </div>
                    </div>
                    <div class="form-group">
                        <h3>Persoonlijke gegevens</h3>
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">Naam?</label>
                                <input
                                    class="input__field form-control"
                                    type="text"
                                    v-model="inputfieldFirstName"
                                />
                            </div>
                        </div>
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">
                                    Tussenvoegsels
                                </label>
                                <input
                                    class="input__field form-control"
                                    type="text"
                                    v-model="inputfieldPrefix"
                                />
                            </div>
                        </div>
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">Achternaam</label>
                                <input
                                    class="input__field form-control"
                                    type="text"
                                    v-model="inputfieldLastName"
                                />
                            </div>
                        </div>
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">Geslacht</label>
                                <div class="form-row">
                                    <div
                                        class="radio custom-radio radio__option"
                                    >
                                        <input
                                            id="man"
                                            value="man"
                                            class="radio__input custom-control-input"
                                            type="radio"
                                            name="geslacht"
                                            v-model="inputfieldGender"
                                        />
                                        <label
                                            class="radio__label custom-control-label"
                                            for="man"
                                        >
                                            Man
                                        </label>
                                    </div>

                                    <div
                                        class="radio custom-radio radio__option"
                                    >
                                        <input
                                            id="vrouw"
                                            value="vrouw"
                                            class="radio__input custom-control-input"
                                            type="radio"
                                            name="geslacht"
                                            v-model="inputfieldGender"
                                        />
                                        <label
                                            class="radio__label custom-control-label"
                                            for="vrouw"
                                        >
                                            Vrouw
                                        </label>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">
                                    Geboortedatum
                                </label>
                                <label for="start">Start date:</label>
                                <input  class="input__field form-control" type="date" id="start" name="trip-start" min="1900-01-01" max="2018-12-31" v-model="inputfieldBirthDate" />
                            </div>
                        </div>
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">
                                    Burgerservicenummer
                                </label>
                                <input
                                    class="input__field form-control is-invalid"
                                    type="text"
                                    v-model="inputfieldSocialNumb"
                                    @blur="validation"
                                />
                            </div>
                            <div
                                class="input__feedback invalid-feedback mt-1"
                                aria-live="polite"  v-show="invalid"
                            >
                                <span
                                    >Helaas is het ingevoerde
                                    burgerservicenummer niet geldig. Probeer het
                                    opnieuw.</span
                                >
                            </div>
                        </div>
                    </div>


                    <h2 class="mt-5">Verzekering</h2>
                    <div class="form-group">
                        <h3>Basisverzekering</h3>
                        <p>
                            In Nederland is de basisverzekering verplicht.
                            Iedereen wordt voor de basisverzekering
                            geaccepteerd. De overheid bepaalt welke zorg hierin
                            zit en dit is dus bij elke verzekeraar hetzelfde.
                        </p>

                        <div class="input__group">
                            <label class="input__title">
                                Kies uw basisverzekering
                            </label>
                            <div class="form-row">
                                <div class="radio__tile">
                                    <div
                                        class="radio custom-radio radio__option"
                                    >
                                        <input
                                            value="Basis Budget"
                                            type="radio"
                                            name="radio-insurance"
                                            id="radio-insurance-basis-budget"
                                            class="radio__input custom-control-input"
                                            v-model="inputfieldBasisverzekering"
                                        />
                                        <label
                                            for="radio-insurance-basis-budget"
                                            class="radio__label custom-control-label"
                                        >
                                            <p class="radio__description">
                                                Basis Budget
                                            </p>
                                            <p class="radio__price">
                                                € 1.393,26 per jaar
                                            </p>
                                        </label>
                                    </div>
                                </div>
                                <div class="radio__tile radio__tile--choice">
                                    <div class="badge radio__tile-badge">
                                        Meest gekozen
                                    </div>
                                    <div
                                        class="radio custom-radio radio__option"
                                    >
                                        <input
                                            value="Basis Zeker"
                                            type="radio"
                                            name="radio-insurance"
                                            id="radio-insurance-basis-zeker"
                                            class="radio__input custom-control-input"
                                            v-model="inputfieldBasisverzekering"
                                        />
                                        <label
                                            for="radio-insurance-basis-zeker"
                                            class="radio__label custom-control-label"
                                        >
                                            <p class="radio__description">
                                                Basis Zeker
                                            </p>
                                            <p class="radio__price">
                                                € 1.483,54 per jaar
                                            </p>
                                        </label>
                                    </div>
                                </div>
                                <div class="radio__tile">
                                    <div
                                        class="radio custom-radio radio__option"
                                    >
                                        <input
                                            value="Basis Exclusief (Restitutie)"
                                            type="radio"
                                            name="radio-insurance"
                                            id="radio-insurance-basis-exclusief-(restitutie)"
                                            class="radio__input custom-control-input"
                                            v-model="inputfieldBasisverzekering"
                                        />
                                        <label
                                            for="radio-insurance-basis-exclusief-(restitutie)"
                                            class="radio__label custom-control-label"
                                        >
                                            <p class="radio__description">
                                                Basis Exclusief (Restitutie)
                                            </p>
                                            <p class="radio__price">
                                                € 1.624,62 per jaar
                                            </p>
                                        </label>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>



                    <div class="form-group">
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">
                                    Kies je betaaltermijn
                                </label>
                                <select v-model="inputfieldBetaaltermijn"  class="form-control">
                                    <option v-for="option in optionsBetaaltermijn" :key="option.value" :value="option.value">
                                    {{ option.text }}
                                    </option>
                                </select>
                            </div>
                        </div>
                    </div>
                    <div class="form-group">
                        <h3>Eigen risico</h3>
                        <div class="form-input my-4">

                            <div v-if="inputfieldBasisverzekering" class="input__group">
                                <label class="input__title">
                                    Kies de hoogste van het eigen risico
                                </label>
                                <select v-model="inputfieldEigenrisico"  class="form-control">
                                    <option v-for="option in optionsEigenrisico" :key="option.value" :value="option.value">
                                        {{ option.text }}
                                    </option>
                                </select>
                            </div>
                            <div v-else class="input__group">
                                <label class="input__title">
                                     Kies de hoogste van het eigen risico
                                </label>
                                <select  class="form-control">
                                    <option>
                                        Kies eerst een basis verzekering
                                    </option>
                                </select>
                            </div>
                        </div>
                    </div>
                    <div class="form-group">
                        <h3>Aanvullende verzekering</h3>
                        <p>
                            Onze aanvullende verzekeringen kennen ruim 100
                            verschillende vergoedingen. De hoogte van de
                            vergoeding verschilt per pakket.hoogte van de
                            vergoeding verschilt per pakket
                        </p>
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">
                                    Kies uw aanvullende verzekering
                                </label>
                                <select v-model="inputfieldAanvullendeverzekering"  class="form-control">
                                    <option v-for="option in optionsAanvullendeverzekering" :key="option.value" :value="option.value">
                                    {{ option.text }}
                                    </option>
                                </select>
                            </div>
                        </div>
                    </div>
                    <div class="form-group">
                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">
                                    Kies uw tandartsverzekering
                                </label>
                                <select v-model="inputfieldTandverzekering"  class="form-control">
                                    <option v-for="option in optionsTandverzekering" :key="option.value" :value="option.value">
                                    {{ option.text }}
                                    </option>
                                </select>
                            </div>
                        </div>
                    </div>

                    <h2 class="mt-5">Controleren</h2>
                    <div class="form-group">
                        <h3>Gekozen pakket</h3>
                        <ul>
                            <li>Gekozen basisverzekering: &euro; {{ inputfieldBasisverzekering }}</li>
                            <li>Gekozen eigen risico: &euro; {{inputfieldEigenrisico}}</li>
                            <li>Gekozen aanvullende verzekering: &euro;{{inputfieldAanvullendeverzekering}}</li>
                            <li>Gekozen tandverzekering: &euro;{{inputfieldTandverzekering}}</li>
                        </ul>
                    </div>
                    <div class="form-group">
                        <h3>Totaalpremie</h3>
                        <ul>
                            <li v-if="inputfieldBetaaltermijn">Betaaltermijn: {{ inputfieldBetaaltermijn }}</li>
                            <li v-else>Geen betaaltermijn geselecteerd</li>

                            <li v-if="inputfieldTotaalpremie.total1 && !inputfieldTotaalpremie.total2 && !inputfieldTotaalpremie.total3">Totaalpremie: &euro; {{ inputfieldTotaalpremie.total1 }}</li>
                            <li v-else-if="inputfieldTotaalpremie.total1 && inputfieldTotaalpremie.total2 && !inputfieldTotaalpremie.total3">Totaalpremie: &euro;{{ inputfieldTotaalpremie.total1 + inputfieldTotaalpremie.total2 }}</li>
                            <li v-else-if="inputfieldTotaalpremie.total1 && inputfieldTotaalpremie.total2 && inputfieldTotaalpremie.total3">Totaalpremie: &euro; {{ inputfieldTotaalpremie.total1 + inputfieldTotaalpremie.total2 +  inputfieldTotaalpremie.total3 }}</li>
                            <li v-else-if="inputfieldTotaalpremie.total1">Totaalpremie: &euro; {{ inputfieldTotaalpremie.total1 }}</li>
                            <li v-else-if="inputfieldTotaalpremie.total2">Totaalpremie: &euro; {{ inputfieldTotaalpremie.total2 }}</li>
                            <li v-else-if="inputfieldTotaalpremie.total3">Totaalpremie: &euro; {{ inputfieldTotaalpremie.total3 }}</li>

                            <li v-else> Geen verzekering geselecteerd</li>
                        </ul>
                    </div>

                    <div class="form-group">
                        <h3>Adres en contactgegevens</h3>
                        <!-- -----------possible UX for user------------- -->

                        <!-- <label class="col-sm-2 col-form-label">Naam</label>
                        <div class="col-sm-10">
                            <input class="form-control" type="text" :placeholder="`${inputfieldFirstName }`" readonly>
                        </div>
                        <label class="col-sm-2 col-form-label">tussenvoegsel</label>
                        <div class="col-sm-10">
                            <input v-if="inputfieldPrefix" class="form-control" type="text" :placeholder="`${inputfieldPrefix }`" readonly>
                            <input v-else class="form-control" type="text" placeholder="" readonly>
                        </div>
                        <label class="col-sm-2 col-form-label">achternaam</label>
                        <div class="col-sm-10">
                            <input v-if="inputfieldPrefix" class="form-control" type="text" :placeholder="`${inputfieldLastName }`" readonly>
                            <input v-else class="form-control" type="text" placeholder="" readonly>
                        </div>

                        <div class="form-input my-4">
                            <div class="input__group">
                                <label class="input__title">Geslacht</label>
                                <div class="form-row">
                                    <div
                                        class="radio custom-radio radio__option"
                                    >
                                        <input
                                            name="geslachtt"
                                            class="radio__input custom-control-input"
                                            type="radio"
                                            readonly
                                            checked
                                        />
                                        <label
                                            class="radio__label custom-control-label"
                                        >
                                        {{ inputfieldGender }}
                                        </label>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <hr> -->
                        <ul>
                            <li>Naam: {{ inputfieldFirstName }}</li>
                            <li>Tussenvoegsel: {{ inputfieldPrefix }}</li>
                            <li>Achternaam: {{ inputfieldLastName }}</li>
                            <li>Geslacht: {{ inputfieldGender }}</li>
                            <li>Geboortedatum: {{ inputfieldBirthDate }}</li>
                            <li>Burgerservicenummer: {{ inputfieldSocialNumb }}</li>
                        </ul>
                    </div>
                </div>
                <div class="col-4">
                    <div class="card card--filled-secondary h-auto">
                        <div class="card-body">
                            <div class="sf-contactblok-content">
                                <h3 class="mb-2">We staan voor je klaar</h3>
                                <p class="mb-5">
                                    Twijfel je? Heb je een vraag?
                                </p>
                                <div class="phonenumber mb-2">
                                    <a href="tel:0900 040 03 09">
                                        <span class="sr-only">
                                            Telefoonnummer
                                        </span>
                                        0900 040 03 09
                                    </a>
                                    <div class="popover__container ml-1">
                                        <button
                                            id="info-phone"
                                            type="button"
                                            class="btn popover__btn btn--popover btn-none"
                                        >
                                            <span class="sr-only">
                                                Informatie weergeven
                                            </span>
                                        </button>
                                    </div>
                                </div>
                                <small>
                                    Open op maandag t/m vrijdag van 08:00 tot
                                    17:00
                                </small>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- FOOTER -->
        <div class="ratingbar">
            <div class="container">
                <div class="row">
                    <div class="col-xs-12 col-sm-6 col-md-4 ratingbar__rating">
                        <a
                            href="https://www.independer.nl/zorgverzekering/fi/zilveren-kruis-ac.aspx"
                            class=""
                            rel="noopener noreferrer"
                            target="_blank"
                        >
                            <img
                                src="https://www.zilverenkruis.nl/-/media/zilverenkruis/images/shared/independer.png?rev=bb0602912ded4b16adc221025f3fc010&amp;h=80&amp;w=80&amp;la=nl-NL&amp;hash=39DBF59680B0FEECA97C6C786FC7DE67"
                                class="ratingbar__icon"
                                alt="Independer"
                                title="Independer"
                            />
                        </a>
                        <span>
                            <span class="ratingbar__ratings-number"> 7,8 </span>
                            <span class="ratingbar__ratings-text">
                                op Independer
                            </span>
                        </span>
                    </div>
                    <div class="col-xs-12 col-sm-6 col-md-4 ratingbar__rating">
                        <span>
                            <span class="ratingbar__ratings-number">
                                3,8 miljoen
                            </span>
                            <span class="ratingbar__ratings-text">
                                klanten gingen u voor
                            </span>
                        </span>
                    </div>
                    <div class="col-xs-12 col-sm-6 col-md-4 ratingbar__rating">
                        <a
                            href="/consumenten/service/declareren/zilveren-kruis-app"
                            class=""
                        >
                            <img
                                src="https://www.zilverenkruis.nl/-/media/zilverenkruis/images/app-logo/app_icon.png?rev=8665a8133399403b92b34eaada19bd46&amp;h=80&amp;w=80&amp;la=nl-NL&amp;hash=70AB973D0AB046A6EFA670CB38F2BF2E"
                                class="ratingbar__icon"
                                alt="Logo Zilveren Kruis-app"
                            />
                        </a>
                        <span>
                            <span class="ratingbar__ratings-number"> 4,5 </span>
                            <span class="ratingbar__ratings-text">
                                beoordeling in App Store
                            </span>
                        </span>
                    </div>
                </div>
            </div>
        </div>
        <footer class="main-footer" role="contentinfo">
            <div class="container main-footer__grid">
                <ul
                    class="main-footer__links-section list list--nostyle list--horiz d-flex"
                >
                    <li class="list__item">
                        <a href="/consumenten/disclaimer" class="list__link"
                            >disclaimer
                        </a>
                    </li>
                    <li class="list__item">
                        <a href="/consumenten/privacy" class="list__link"
                            >privacy
                        </a>
                    </li>
                    <li class="list__item">
                        <a href="/consumenten/veiligheid" class="list__link"
                            >veiligheid
                        </a>
                    </li>
                    <li class="list__item">
                        <a href="/consumenten/cookies" class="list__link"
                            >cookies
                        </a>
                    </li>
                    <li class="list__item">
                        <a
                            href="https://www.wijzeringeldzaken.nl/verzekering/"
                            class="list__link"
                            rel="noopener noreferrer"
                            target="_blank"
                        >
                            wijzer in geldzaken
                        </a>
                    </li>
                </ul>
                <div class="main-footer__label-description">
                    <span>Zilveren Kruis is onderdeel van Achmea</span>
                </div>
            </div>
        </footer>
    </div>
</template>
