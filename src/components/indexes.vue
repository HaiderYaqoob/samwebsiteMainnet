<template>
  <div
    class="hello" style="overflow: hidden"
    :class="
      changeModeIndex === 'lightTheme'
        ? 'helloForLightTheme'
        : 'helloForDarkTheme'
    "
  >
    <div class="side-bar" v-if="sidebar === 'true'">
      <br /><br />
      <span
        @click="navigateSidebar('false')"
        style="float: right; margin-right: 20px; color: white; cursor: pointer"
        ><img
          src="https://cdn4.iconfinder.com/data/icons/arrow-68/48/36-512.png"
          width="20px"
        /> </span
      ><br /><br />
      <h4 class="sidebarName" style="color: white">Sam Collins</h4>
      <br />
      <h4 class="sidebarItems">
        <a href="/indexes" class="sidebarLinks">Cryptocurrencies</a>
      </h4>
      <br />
      <h4 class="sidebarItems">
        <a href="/whatWeOffer" class="sidebarLinks">What We Offer</a>
      </h4>
      <br />
      <h4 class="sidebarItems">
        <a href="/whyBitcoin" class="sidebarLinks">Why Bitcoin</a>
      </h4>
      <br />
      <h4 class="sidebarItems">
        <a href="/whoItWork" class="sidebarLinks">Who It Works</a>
      </h4>
      <div
        class="navbar-nav ml-auto istBtn"
        id="color-btns"
        :class="
          changeModeIndex === 'lightTheme' ? 'displayInherit' : 'displayNone'
        "
      >
        <button
          class="change-color-site"
          id="changeModeIndexMoon"
          @click="changeIndexMode('darkTheme')"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'changeColorSiteForLight'
              : 'changeColorSiteForDark'
          "
        >
          <!-- @click="navigateMode('true')"
               id="changeMode1"   CLASS k aagay likha huwa tah -->
          <span
            class="red-btn"
            :class="
              changeModeIndex === 'darkTheme' ? 'displayNone' : 'displayInherit'
            "
            ><svg
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              aria-hidden="true"
              focusable="false"
              width="1em"
              height="1em"
              style="
                -ms-transform: rotate(360deg);
                -webkit-transform: rotate(360deg);
                transform: rotate(360deg);
              "
              preserveAspectRatio="xMidYMid meet"
              viewBox="0 0 24 24"
              class="iconify moon-icon"
              data-icon="feather-moon"
              data-inline="false"
            >
              <g
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <path
                  d="M21 12.79A9 9 0 1 1 11.21 3A7 7 0 0 0 21 12.79z"
                ></path>
              </g></svg
          ></span>
        </button>
      </div>
      <div
        class="navbar-nav ml-auto sndBtn"
        id="color-btns"
        :class="
          changeModeIndex === 'lightTheme' ? 'displayNone' : 'displayInherit'
        "
      >
        <button
          class="change-color-site"
          id="changeModeIndexMoon"
          @click="changeIndexMode('lightTheme')"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'changeColorSiteForLight'
              : 'changeColorSiteForDark'
          "
        >
          <!-- @click="navigateMode('true')"
               id="changeMode1"   CLASS k aagay likha huwa tah -->
          <span
            class="sun-like"
            :class="
              changeModeIndex === 'lightTheme'
                ? 'displayNone'
                : 'displayInherit'
            "
            ><svg
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              aria-hidden="true"
              focusable="false"
              width="1em"
              height="1em"
              style="
                -ms-transform: rotate(360deg);
                -webkit-transform: rotate(360deg);
                transform: rotate(360deg);
              "
              preserveAspectRatio="xMidYMid meet"
              viewBox="0 0 24 24"
              class="iconify sun-icon"
              data-icon="feather-sun"
              data-inline="false"
            >
              <g
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              >
                <circle cx="12" cy="12" r="5"></circle>
                <path d="M12 1v2"></path>
                <path d="M12 21v2"></path>
                <path d="M4.22 4.22l1.42 1.42"></path>
                <path d="M18.36 18.36l1.42 1.42"></path>
                <path d="M1 12h2"></path>
                <path d="M21 12h2"></path>
                <path d="M4.22 19.78l1.42-1.42"></path>
                <path d="M18.36 5.64l1.42-1.42"></path>
              </g></svg
          ></span>
        </button>
      </div>
    </div>
    <div v-if="page === 'buySell'">
      <div v-if="infoDiv === 'connected'">
        <div
          class="accountAddress"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'accountAddressForLightTheme'
              : 'accountAddressForDarkTheme'
          "
        >
          <span>{{ accountAddress }}</span>
        </div>
        <div
          class="accountBalance"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'accountBalanceForLightTheme'
              : 'accountBalanceForDarkTheme'
          "
        >
          <span>{{ withoutPoint }} ETH</span>
        </div>
      </div>
    </div>
    <nav
      class="navbar navbar-expand-md navbar-light"
      :class="
        changeModeIndex === 'lightTheme'
          ? 'navbarForLightTheme'
          : 'navbarForDarkTheme'
      "
    >
      <a href="/" class="navbar-brand">
        <img
          class="logo-1"
          src="https://www.freelogoservices.com/api/main/images/1j+ojFVDOMkX9Wytexe43D6kif+JqxFGkBjIwXs1M3EMoAJtliEuj...Vo9P89"
          style="position: absolute; width: 140px; top: -15px; left: -20px"
          width="160px"
        />
        <img
          class="logo-2"
          src="../assets/images/block360.png"
          style="position: absolute; width: 40px; top: 8px; left: 10px"
        />
        <span
          class="logo-1"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'logo1ForLightTheme'
              : 'logo1ForDarkTheme'
          "
          style="margin-left: 100px; font-weight: bold"
          >.</span
        >
        <span
          class="logo-2"
          style="margin-left: 50px"
          id="marginTopMinusFive"
          :class="changeModeIndex === 'darkTheme' ? 'colorWhite' : 'colorBlack'"
          >Sam Collins</span
        >
      </a>
      <button
        type="button"
        class="navbar-toggler"
        data-toggle="collapse"
        data-target="#navbarCollapse"
        style="border: none"
        aria-controls="navbarCollapse"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <i
          class="fas fa-search" id="marginTopMinusFive"
          :class="changeModeIndex === 'darkTheme' ? 'colorWhite' : 'colorBlack'"
          style="margin-right: 10px"
        ></i>
        <i
          @click="navigateSidebar('true')" id="marginTopMinusFive"
          class="fas fa-bars"
          :class="changeModeIndex === 'darkTheme' ? 'colorWhite' : 'colorBlack'"
        ></i>
      </button>

      <div class="collapse navbar-collapse" id="navbarCollapse">
        <div class="navbar-nav" style="margin-left: 120px">
          <router-link
            to="/indexes"
            class="nav-item nav-link active"
            :class="
              changeModeIndex === 'lightTheme'
                ? 'activeForLightTheme'
                : 'activeForDarkTheme'
            "
            >Cryptocurrencies</router-link
          >
          <router-link
            to="/whatWeOffer"
            class="nav-item nav-link"
            :class="
              changeModeIndex === 'lightTheme'
                ? 'navlinkForLightTheme'
                : 'navlinkForDarkTheme'
            "
            >What We Offer</router-link
          >
          <router-link
            to="/whyBitcoin"
            class="nav-item nav-link"
            :class="
              changeModeIndex === 'lightTheme'
                ? 'navlinkForLightTheme'
                : 'navlinkForDarkTheme'
            "
            >Why Bitcoin</router-link
          >
          <router-link
            to="/whoItWork"
            class="nav-item nav-link"
            :class="
              changeModeIndex === 'lightTheme'
                ? 'navlinkForLightTheme'
                : 'navlinkForDarkTheme'
            "
            >Who It Works</router-link
          >
        </div>
        <div class="navbar-nav ml-auto">
          <div
            class="navbar-nav ml-auto istBtn"
            id="color-btns"
            :class="
              changeModeIndex === 'lightTheme'
                ? 'displayInherit'
                : 'displayNone'
            "
          >
            <button
              class="change-color-site"
              id="changeModeIndexMoon"
              @click="changeIndexMode('darkTheme')"
              :class="
                changeModeIndex === 'lightTheme'
                  ? 'changeColorSiteForLight'
                  : 'changeColorSiteForDark'
              "
            >
              <!-- @click="navigateMode('true')"
               id="changeMode1"   CLASS k aagay likha huwa tah -->
              <span
                class="red-btn"
                :class="
                  changeModeIndex === 'darkTheme'
                    ? 'displayNone'
                    : 'displayInherit'
                "
                ><svg
                  xmlns="http://www.w3.org/2000/svg"
                  xmlns:xlink="http://www.w3.org/1999/xlink"
                  aria-hidden="true"
                  focusable="false"
                  width="1em"
                  height="1em"
                  style="
                    -ms-transform: rotate(360deg);
                    -webkit-transform: rotate(360deg);
                    transform: rotate(360deg);
                  "
                  preserveAspectRatio="xMidYMid meet"
                  viewBox="0 0 24 24"
                  class="iconify moon-icon"
                  data-icon="feather-moon"
                  data-inline="false"
                >
                  <g
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  >
                    <path
                      d="M21 12.79A9 9 0 1 1 11.21 3A7 7 0 0 0 21 12.79z"
                    ></path>
                  </g></svg
              ></span>
            </button>
          </div>
          <div
            class="navbar-nav ml-auto sndBtn"
            id="color-btns"
            :class="
              changeModeIndex === 'lightTheme'
                ? 'displayNone'
                : 'displayInherit'
            "
          >
            <button
              class="change-color-site"
              id="changeModeIndexMoon"
              @click="changeIndexMode('lightTheme')"
              :class="
                changeModeIndex === 'lightTheme'
                  ? 'changeColorSiteForLight'
                  : 'changeColorSiteForDark'
              "
            >
              <!-- @click="navigateMode('true')"
               id="changeMode1"   CLASS k aagay likha huwa tah -->
              <span
                class="sun-like"
                :class="
                  changeModeIndex === 'lightTheme'
                    ? 'displayNone'
                    : 'displayInherit'
                "
                ><svg
                  xmlns="http://www.w3.org/2000/svg"
                  xmlns:xlink="http://www.w3.org/1999/xlink"
                  aria-hidden="true"
                  focusable="false"
                  width="1em"
                  height="1em"
                  style="
                    -ms-transform: rotate(360deg);
                    -webkit-transform: rotate(360deg);
                    transform: rotate(360deg);
                  "
                  preserveAspectRatio="xMidYMid meet"
                  viewBox="0 0 24 24"
                  class="iconify sun-icon"
                  data-icon="feather-sun"
                  data-inline="false"
                >
                  <g
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  >
                    <circle cx="12" cy="12" r="5"></circle>
                    <path d="M12 1v2"></path>
                    <path d="M12 21v2"></path>
                    <path d="M4.22 4.22l1.42 1.42"></path>
                    <path d="M18.36 18.36l1.42 1.42"></path>
                    <path d="M1 12h2"></path>
                    <path d="M21 12h2"></path>
                    <path d="M4.22 19.78l1.42-1.42"></path>
                    <path d="M18.36 5.64l1.42-1.42"></path>
                  </g></svg
              ></span>
            </button>
          </div>
          <a href="/profile" class="nav-item nav-link"
            ><i
              class="fas fa-user" style="position:relative;top:7px;"
              :class="
                changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
              "
            ></i
          ></a>
        </div>
      </div>
    </nav>
    <!-- <hr class="divide" /> -->
    <br /><br /><br /><br />
    <div class="global-status">
      <p>
        <span class="global-status-heading">Market Cap: </span
        ><span
          class="global-status-detail"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'globalstatusDetailForLightTheme'
              : 'globalstatusDetailForDarkTheme'
          "
          >$1,715,605,569,999</span
        ><span class="dot">.</span
        ><span class="global-status-heading">24h Vol: </span
        ><span
          class="global-status-detail"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'globalstatusDetailForLightTheme'
              : 'globalstatusDetailForDarkTheme'
          "
          >$184,345,540,849</span
        ><span class="dot">.</span
        ><span class="global-status-heading">BTC Dominance: </span
        ><span
          class="global-status-detail"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'globalstatusDetailForLightTheme'
              : 'globalstatusDetailForDarkTheme'
          "
          >61.5%</span
        ><span class="dot">.</span
        ><span class="global-status-heading">Cryptocurrencies: </span
        ><span
          class="global-status-detail"
          :class="
            changeModeIndex === 'lightTheme'
              ? 'globalstatusDetailForLightTheme'
              : 'globalstatusDetailForDarkTheme'
          "
          >8,532</span
        >
      </p>
      <hr class="divider" />
    </div>
    <div></div>
    <div v-if="page === 'mainPage'">
      <div>
        <!-- <img
        src="https://static2.clutch.co/s3fs-public/logos/5122x.png?9LLY4hBhGYxh3oX_CPKPjrYEIRu4AFOS"
        width="100px"
        height="100px"
      /><span style="font-size: 30px; margin-left: 20px">Block360</span -->
        <img
          class="add-img"
          id="lightPageBanner"
          :class="
            changeModeIndex === 'lightTheme' ? 'heroImgForLight' : 'displayNone'
          "
          src="http://www.globalethicalbanking.com/wp-content/uploads/2020/07/23-zoya.jpg"
          width="1000px"
          height="250px"
        />
        <img
          class="add-img2"
          id="darkPageBanner"
          :class="
            changeModeIndex === 'lightTheme' ? 'displayNone' : 'displayInherit'
          "
          src="https://i.graphicmama.com/blog/wp-content/uploads/2019/11/01141506/black-web-banner-design.jpg"
          width="1000px"
          height="250px"
        />

        <br /><br />
      </div>
      <div class="table-main-div">
        <table
          class="table"
          :class="
            changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
          "
        >
          <thead style="position: sticky">
            <tr>
              <th>#</th>
              <th>Coin</th>
              <th></th>
              <th>Price</th>
              <th>1h</th>
              <th>24h</th>
              <th>7d</th>
              <th>24h Volume</th>
              <th>Mkt Cap</th>
            </tr>
          </thead>
          <div v-if="loading" class="loading-div">
            <img class="loading_class" src="@/assets/spinner.svg" />
            <span class="loading_class loading_text">Loading...</span>
          </div>
          <tbody v-else>
            <tr
              v-for="(indexes, index) in arrayOfIndex"
              :key="index"
              @click="furtherCoinData(indexes)"
            >
              <td>{{ index + 1 }}</td>
              <td><img class="indexesImage" :src="indexes.image" /></td>
              <td class="alignStart">{{ indexes.name }}</td>
              <td>{{ commaFunc("$" + indexes.current_price) }}</td>
              <td>
                <span
                  :class="
                    indexes.price_change_percentage_1h_in_currency === null
                      ? 'normal'
                      : indexes.price_change_percentage_1h_in_currency > 0
                      ? 'text-success'
                      : 'text-danger'
                  "
                >
                  {{
                    indexes.price_change_percentage_1h_in_currency === null
                      ? "?"
                      : formatPercent(
                          indexes.price_change_percentage_1h_in_currency
                        ) + "%"
                  }}
                </span>
              </td>
              <td>
                <span
                  :class="
                    indexes.price_change_percentage_24h === null
                      ? 'normal'
                      : indexes.price_change_percentage_24h > 0
                      ? 'text-success'
                      : 'text-danger'
                  "
                >
                  {{
                    indexes.price_change_percentage_24h === null
                      ? "?"
                      : formatPercent(indexes.price_change_percentage_24h) + "%"
                  }}
                  <!-- {{ formatPercent(indexes.price_change_percentage_24h) + '%' }} -->
                </span>
              </td>
              <td>
                <span
                  :class="
                    indexes.price_change_percentage_7d_in_currency === null
                      ? 'normal'
                      : indexes.price_change_percentage_7d_in_currency > 0
                      ? 'text-success'
                      : 'text-danger'
                  "
                >
                  {{
                    indexes.price_change_percentage_7d_in_currency === null
                      ? "?"
                      : formatPercent(
                          indexes.price_change_percentage_7d_in_currency
                        ) + "%"
                  }}
                </span>
              </td>
              <td>
                {{
                  indexes.total_volume === null
                    ? "?"
                    : commaFunc("" + indexes.total_volume)
                }}
              </td>
              <td>
                {{
                  indexes.market_cap === null
                    ? "?"
                    : commaFunc("" + indexes.market_cap)
                }}
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div v-if="page === 'buySell'">
      <div class="furtherPage">
        <div
          class="cross"
          style="
            position: absolute;
            right: 100px;
            cursor: pointer;
            margin-top: -10px;
          "
          @click="navigatePage('mainPage')"
        >
          <span
            ><img id="curvedArrow"
              src="https://cdn4.iconfinder.com/data/icons/arrow-68/48/36-512.png"
              width="20px"
              :class="
                changeModeIndex === 'lightTheme'
                  ? 'displayInherit'
                  : 'displayNone'
              "
          /></span>
          <span
            ><img id="curvedArrow"
              src="../assets/curvedArrow.png"
              width="20px"
              :class="
                changeModeIndex === 'lightTheme'
                  ? 'displayNone'
                  : 'displayInherit'
              "
          /></span>
        </div>
        <div class="success" v-if="transactionSuccess === 'true'">
          <!-- <div class="overLay"></div> -->
          <a href="/indexes"
            ><img src="../assets/images/cross.png" class="crossModel"
          /></a>
          <img class="successImg" src="../assets/images/successTick.png" />
          <h4 class="successHeading">Congratulations</h4>
          <p
            class="successSubHeading"
            :class="
              changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorBlack'
            "
          >
            Your Transaction is successfully completed.
          </p>
          <p class="successHash">
            <span
              class="successTransactionText"
              :class="
                changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorBlack'
              "
              >Transaction Hash: </span
            ><span
              class="successHashNumber"
              :class="
                changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorBlack'
              "
              >{{ transactionHash }}</span
            >
          </p>
          <a href="/indexes"><button class="successBtn">Home</button></a>
        </div>
        <div class="checkout">
          <h5
            class="about-heading"
            :class="
              changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
            "
          >
            <img :src="furtherCoinDetail.image.small" />
            {{ furtherCoinDetail.name }}
            <span class="coinSymbol">({{ furtherCoinDetail.symbol }})</span>
          </h5>
          <div
            class="about-sub-heading"
            :class="
              changeModeIndex === 'lightTheme'
                ? 'colorForAboutSubHeading'
                : 'colorWhite'
            "
          >
            <img
              src="../assets/images/heart.png"
              class="interestHeart"
              width="23px"
            />{{ furtherCoinDetail.public_interest_stats.alexa_rank }} people
            take interest in this coin <br /><br /><br />
            <p>
              Market Cap:
              <span
                ><span
                  class="rankBox"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'stylingForRankBoxLightTheme'
                      : 'stylingForRankBoxDarkTheme'
                  "
                  >Rank #{{ furtherCoinDetail.market_cap_rank }}</span
                ></span
              >
            </p>
            <p>
              Website:
              <span style="margin-left: 34px"
                ><span
                  class="infoTokens"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >{{ furtherCoinDetail.links.homepage[0] }}</span
                >
                <span
                  class="infoTokens"
                  style="margin-left: 2px"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >{{ furtherCoinDetail.links.announcement_url[0] }}</span
                ></span
              >
            </p>
            <p>
              Explorers:
              <span style="margin-left: 24px"
                ><span
                  class="infoTokens"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >Etherscan</span
                >
                <span
                  class="infoTokens"
                  style="margin-left: 2px"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >Ethplorer</span
                ></span
              >
            </p>
            <p>
              Contract:
              <span style="margin-left: 30px"
                ><span
                  class="infoTokens"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >{{ furtherCoinDetail.platforms.ethereum }}</span
                ></span
              >
            </p>
            <p>
              Community:
              <span style="margin-left: 12px"
                ><span
                  class="infoTokens"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >Twitter</span
                ><span
                  class="infoTokens"
                  style="margin-left: 2px"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >discordapp.com</span
                ></span
              >
            </p>
            <p>
              Tags:
              <span style="margin-left: 53px"
                ><span
                  class="infoTokens"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  style="color: black"
                  >Token</span
                >
                <span
                  class="infoTokens"
                  style="margin-left: 2px"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >Index</span
                >
                <span
                  class="infoTokens"
                  style="margin-left: 2px"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >DeFi Index</span
                >
                <span
                  class="infoTokens"
                  style="margin-left: 2px"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >TokenSets</span
                >
                <span
                  class="infoTokens"
                  style="margin-left: 2px"
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'infoTokensForLightTheme'
                      : 'infoTokensForDarkTheme'
                  "
                  >Decentralized Finance (DeFi)</span
                ></span
              >
            </p>
          </div>
          <!-- <p class="about-footer">
            <span class="totalSupply">Total Supply</span
            ><span class="aboutVolume">24 Hour Volume</span
            ><span class="aboutMarket">Market Cap</span>
          </p>
          <p class="about-footers">
            <span class="gap">ETH</span><span class="gaps">$37.45B USD</span
            ><span>$> 1T USD</span>
          </p> -->
        </div>
        <div class="checkoutInfo">
          <div class="checkout-div">
            <br />
            <h6 class="headMarketLimit">
              <span
                class="market"
                :class="
                  changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
                "
                >Limit</span
              ><span class="limit">Market</span
              ><span class="svg"
                ><svg
                  @click="navigatePage('mainPage')"
                  xmlns="http://www.w3.org/2000/svg"
                  width="16"
                  height="16"
                  fill="none"
                  viewBox="0 0 16 16"
                  style="cursor: pointer"
                >
                  <path
                    :class="
                      changeModeIndex === 'lightTheme'
                        ? 'svgPointerForLightTheme'
                        : 'svgPointerForDarkTheme'
                    "
                    d="M15 3h-4c-.6 0-1 .4-1 1s.4 1 1 1h4c.6 0 1-.4 1-1s-.4-1-1-1zM5 1c-1.3 0-2.4.9-2.8 2H1c-.6 0-1 .4-1 1s.4 1 1 1h1.2C2.6 6.1 3.7 7 5 7c1.7 0 3-1.3 3-3S6.7 1 5 1zM1 13h4c.6 0 1-.4 1-1s-.4-1-1-1H1c-.6 0-1 .4-1 1s.4 1 1 1zM15 11h-1.2c-.4-1.2-1.5-2-2.8-2-1.7 0-3 1.3-3 3s1.3 3 3 3c1.3 0 2.4-.9 2.8-2H15c.6 0 1-.4 1-1s-.4-1-1-1z"
                  ></path></svg
              ></span>
            </h6>
            <br />
            <hr
              class="divider"
              :class="
                changeModeIndex === 'lightTheme'
                  ? 'buyselldividerForLightTheme'
                  : 'buyselldividerForDarkTheme'
              "
            />
            <span
              class="youPay"
              :class="
                changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
              "
              >You Pay</span
            ><br /><br />
            <h2
              class="chooseToken"
              :class="
                changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
              "
            >
              Wrapped ether
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="11"
                height="7"
                fill="none"
                viewBox="0 0 11 7"
              >
                <path
                  :class="
                    changeModeIndex === 'lightTheme'
                      ? 'svgPointerForLightTheme'
                      : 'svgPointerForDarkTheme'
                  "
                  fill="#0A1A5D"
                  d="M5.4 6.9L0 1.5 1.4.1l4 4 4-4 1.4 1.4-5.4 5.4z"
                ></path>
              </svg>
            </h2>
            <!-- <input
              v-if="connectWallet === false"
              type="number"
              class="payFeild" :class="changeModeIndex === 'lightTheme' ? 'payFeildForLightTheme' : 'payFeildForDarkTheme'"
              id="payFeild"
              placeholder="0.01"
              @keypress="tokenPrice"
              disabled
              title="First Connect Wallet"
            /> -->
            <!-- <input
              v-if="connectWallet === true" -->
            <input
              type="number"
              class="payFeild"
              placeholder="0.01"
              v-model="placedAmount"
              @keypress="tokenPrice"
            />
            <br /><br />
            <div
              class="youReceive-div"
              :class="
                changeModeIndex === 'lightTheme'
                  ? 'youReceive-divForLightTheme'
                  : 'youReceive-divForDarkTheme'
              "
            >
              <div class="translator-icon-div">
                <span
                  ><span
                    ><svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="17"
                      height="17"
                      fill="none"
                      class="translatorSVG"
                      viewBox="0 0 17 17"
                    >
                      <path
                        fill="#0E103C"
                        d="M3.566 5.99h-3l4-5 4 5h-3v8a1 1 0 01-2 0v-8zM11.566 11.99v-8a1 1 0 012 0v8h3l-4 5-4-5h3z"
                      ></path></svg></span
                ></span>
              </div>
              <br />
              <span
                class="oneTokenPrice"
                :class="
                  changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
                "
                >One {{ furtherCoinDetail.symbol }} Price: {{ oneTokenPrice }}</span
              >
              <span
                class="youReceive"
                :class="
                  changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
                "
                >You Receive</span
              ><br /><br />
              <h3
                class="coinName"
                :class="
                  changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
                "
              >
                {{ furtherCoinDetail.symbol }}
                <span
                  ><svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="11"
                    height="7"
                    fill="none"
                    viewBox="0 0 11 7"
                  >
                    <path
                      :class="
                        changeModeIndex === 'lightTheme'
                          ? 'svgPointerForLightTheme'
                          : 'svgPointerForDarkTheme'
                      "
                      fill="#0A1A5D"
                      d="M5.4 6.9L0 1.5 1.4.1l4 4 4-4 1.4 1.4-5.4 5.4z"
                    ></path></svg></span
                ><span
                  ><input
                    class="result"
                    type="text"
                    placeholder="0"
                    :value="finalPrice"
                /></span>
              </h3>
              <br />
              <div v-if="swap === 'true'">
                <button class="review-btn" id="swapButton" @click="swapIt()">
                  SWAP</button
                ><br /><br />
              </div>
              <div v-if="swap === 'false'">
                <button class="review-btn" @click="loadWeb3()">
                  Connect Wallet</button
                ><br /><br />
              </div>
              <div v-if="swap === 'pending'">
                <button class="review-btn">
                  <img
                    src="../assets/loading.gif"
                    style="width: 20px; margin-right: 4px"
                  />loading ...</button
                ><br /><br />
              </div>
            </div>
            <br />
          </div>
        </div>
      </div>
    </div>
    <br /><br /><br /><br /><br /><br /><br />
    <div
      class="footer"
      :class="
        changeModeIndex === 'lightTheme' ? 'backgroundBrown' : 'backgroundWhite'
      "
    >
      <h6>
        <span
          class="footerText"
          :class="
            changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
          "
          >Disclaimer</span
        ><span class="footer-dot"> . </span
        ><span
          class="footerText"
          :class="
            changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
          "
          >Terms of Service</span
        ><span class="footer-dot"> . </span
        ><span
          class="footerText"
          :class="
            changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
          "
          >Privacy Policy</span
        >
      </h6>
      <h6>
        <!-- <span>@</span> -->
        <span
          class="footerText"
          :class="
            changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
          "
          >2021 Sam Collins<span class="footer-dot"> . </span></span
        ><span
          class="footerText"
          :class="
            changeModeIndex === 'lightTheme' ? 'colorBlack' : 'colorWhite'
          "
        >
          All Rights Reserved</span
        >
      </h6>
    </div>
  </div>
</template>

<script>
import Web3 from 'web3'
import { Fetcher, WETH, Route, Trade, TokenAmount, TradeType, Percent } from '@uniswap/sdk'
import { ethers } from 'ethers'
import uniswapAbi from '../assets/uniswapAbi.json'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      page: 'mainPage',
      infoDiv: '',
      sidebar: 'false',
      loading: true,
      arrayOfIndex: [],
      indexId: '',
      websitesRegex: '',
      websites: '',
      // filterWebsite: '',
      furtherCoinDetail: {},
      totalTokens: '',
      ethBalance: '0',
      withoutPoint: '0',
      swap: 'false',
      networkId: '',
      totalTokenPrice: '',
      oneTokenPrice: '',
      tradeIs: '',
      weth: '',
      dai: '',
      amountOutMin: '',
      minAmountOut: '',
      slippageTolerance: '',
      value: '',
      connectWallet: false,
      placedAmount: '',
      totalPriceM: '',
      finalPrice: '',
      transactionHash: '',
      transactionSuccess: 'false',
      keyPressedLast: '',
      charRegex: '',
      lightMode: 'true',
      changeModeIndex: '',
      tokenContractHashAddress: ''
    }
  },
  created () {
    this.$http
      .get('https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=defipulse-index%2Cdefi-top-5-tokens-index%2Csdefi%2Ccryptocurrency-top-10-tokens-index%2Cpower-index-pool-token%2Cassy-index%2Cpunk-basic%2Cpiedao-defi-large-cap%2Cyearn-ecosystem-token-index%2Cdegen-index%2Cpiedao-defi%2Cpiedao-defi-small-cap%2Cnftx-hashmasks-index%2Ccoinshares-gold-and-cryptoassets-index-lite%2Choly-trinity%2Coracle-top-5%2Cbaby-power-index-pool-token%2Cidefi%2Cpunk%2C1x-short-defi-index-token%2C0-5x-long-defi-index-token%2Cserum-ecosystem-token%2Cpunk-attr-4%2Cpunk-attr-5%2C3x-short-defi-index-token%2C3x-long-defi-index-token%2Cpunk-female%2Cpiedao-yearn-ecosystem-pie%2Cpunk-zombie&order=market_cap_desc&per_page=100&page=1&sparkline=true&price_change_percentage=1h%2C7d')
      .then(function (coins) {
        console.log('response', coins)
        this.props = coins
        const { data } = this.props
        console.log('data', data)
        this.loading = false

        const defipulseIndex = data.find(coin => coin.id === 'defipulse-index')
        const Defi5Index = data.find(coin => coin.id === 'defi-top-5-tokens-index')
        const SDEFI = data.find(coin => coin.id === 'sdefi')
        const cryptotop10Index = data.find(coin => coin.id === 'cryptocurrency-top-10-tokens-index')
        const powerPoolToken = data.find(coin => coin.id === 'power-index-pool-token')
        const ASSYINDEX = data.find(coin => coin.id === 'assy-index')
        const PunkBasic = data.find(coin => coin.id === 'punk-basic')
        const piedaoDefiLargeCap = data.find(coin => coin.id === 'piedao-defi-large-cap')
        const yearnEcosystemTokenindex = data.find(coin => coin.id === 'yearn-ecosystem-token-index')
        const degenindex = data.find(coin => coin.id === 'degen-index')
        const piedaodefi = data.find(coin => coin.id === 'piedao-defi')
        const piedaodefismallcap = data.find(coin => coin.id === 'piedao-defi-small-cap')
        const nftxhashmasksindex = data.find(coin => coin.id === 'nftx-hashmasks-index')
        const coinsharesgoldandcryptoassetsindexlite = data.find(coin => coin.id === 'coinshares-gold-and-cryptoassets-index-lite')
        const holytrinity = data.find(coin => coin.id === 'holy-trinity')
        const oracconstop5 = data.find(coin => coin.id === 'oracle-top-5')
        // const babypowerindexpooltoken = data.find(coin => coin.id === 'baby-power-index-pool-token')
        const idefi = data.find(coin => coin.id === 'idefi')
        const punk = data.find(coin => coin.id === 'punk')
        const shortdefiindextoken = data.find(coin => coin.id === '1x-short-defi-index-token')
        const xlongdefiindextoken = data.find(coin => coin.id === '0-5x-long-defi-index-token')
        const serumecosystemtoken = data.find(coin => coin.id === 'serum-ecosystem-token')
        const punkattr4 = data.find(coin => coin.id === 'punk-attr-4')
        const punkattr5 = data.find(coin => coin.id === 'punk-attr-5')
        const shortdefiindextoken3x = data.find(coin => coin.id === '3x-short-defi-index-token')
        const longdefiindextoken3x = data.find(coin => coin.id === '3x-long-defi-index-token')
        const punkfemale = data.find(coin => coin.id === 'punk-female')
        const piedaoyearnecosystempie = data.find(coin => coin.id === 'piedao-yearn-ecosystem-pie')
        const punkzombie = data.find(coin => coin.id === 'punk-zombie')

        this.arrayOfIndex = [
          defipulseIndex,
          Defi5Index,
          SDEFI,
          cryptotop10Index,
          powerPoolToken,
          ASSYINDEX,
          PunkBasic,
          piedaoDefiLargeCap,
          yearnEcosystemTokenindex,
          degenindex,
          piedaodefi,
          piedaodefismallcap,
          nftxhashmasksindex,
          coinsharesgoldandcryptoassetsindexlite,
          holytrinity,
          oracconstop5,
          // babypowerindexpooltoken,
          idefi,
          punk,
          shortdefiindextoken,
          xlongdefiindextoken,
          serumecosystemtoken,
          punkattr4,
          punkattr5,
          shortdefiindextoken3x,
          longdefiindextoken3x,
          punkfemale,
          piedaoyearnecosystempie,
          punkzombie
        ]
        console.log('arrayOfIndex', this.arrayOfIndex)
      })

      .catch((error) => {
        console.log('error', error)
      })
  },
  methods: {
    navigateMode (Mode) {
      this.lightMode = Mode
    },
    navigatePage (page) {
      this.page = page
    },
    changeIndexMode (mode) {
      localStorage.setItem('WebsiteIndexmode', mode)
      this.changeModeIndex = this.$store.state.changeModeIndexWebsite = mode
      // this.changeModeIndex = mode
    },
    furtherCoinData (index) {
      console.log(index.id)
      this.indexId = index.id
      this.$http
        .get(`https://api.coingecko.com/api/v3/coins/${this.indexId}`)
        .then(function (coin) {
          this.page = 'buySell'
          this.furtherCoinDetail = coin.body
          this.tokenContractHashAddress = this.furtherCoinDetail.platforms.ethereum
          console.log('furthercoindertatil', this.furtherCoinDetail)
          this.websites = this.furtherCoinDetail.links.homepage[0]
          console.log('websites', this.websites)
        })
        .catch(error => {
          console.log(error)
        })
    },
    navigateSidebar (sidebar) {
      this.sidebar = sidebar
    },
    formatPercent (number) {
      return Number.parseFloat(number).toFixed(1)
    },
    commaFunc (number) {
      return number.replace(/(\d)(?=(\d\d\d)+(?!\d))/g, '$1,')
    },
    async tokenPrice (e) {
      const numberRegex = /[0-9]+/
      if (e.key.match(numberRegex)) {
        this.swap = 'pending'
        const chainId = 1
        const tokenAddress = this.tokenContractHashAddress

        const dai = await Fetcher.fetchTokenData(chainId, tokenAddress)
        console.log(dai)
        const weth = WETH[chainId]
        console.log('weth', weth)

        const pair = await Fetcher.fetchPairData(dai, weth)
        this.charRegex = /[a-zA-Z]+/
        console.log('pair', pair)

        const route = new Route([pair], weth)
        console.log('route', route)

        // if (this.placedAmount > this.withoutPoint) {
        //   console.log('placedAmount', this.placedAmount)
        //   console.log('withoutPoint', this.withoutPoint)
        //   alert('insufficant Balance ' + this.withoutPoint)
        // } else if (this.placedAmount < this.withoutPoint) {
        console.log(e.key)
        const keyPressed = this.placedAmount

        console.log('placedAmount is ', this.placedAmount)

        if (keyPressed.match(/^[1-9]+/)) {
          console.log('first')
          this.keyPressedLast = keyPressed + '000000000000000000'
          console.log('keyPressedLast', this.keyPressedLast)

          const oneDai = new Trade(route, new TokenAmount(weth, 1000000000000000000), TradeType.EXACT_INPUT)
          console.log('oneDai', oneDai)
          const oneDaiExecutionPrice = oneDai.executionPrice.toSignificant(6)
          const priceWithKeyPressed = oneDaiExecutionPrice * keyPressed
          console.log('priceWithKeyPressed', priceWithKeyPressed)
          var totalPriceM = priceWithKeyPressed.toString()
          this.finalPrice = totalPriceM.match(/[0-9]+.[0-9]/).toString()
          console.log('totalPrice ', this.finalPrice)
        } else if (keyPressed.match(/^[0][.][1-9]$/)) {
          console.log('second')
          const numbAftPoint = keyPressed.substring(2, 3)
          console.log('numbAftPoint', numbAftPoint)
          this.keyPressedLast = numbAftPoint + '00000000000000000'
          console.log('keyPressedLast', this.keyPressedLast)

          const oneDai = new Trade(route, new TokenAmount(weth, 100000000000000000), TradeType.EXACT_INPUT)
          console.log('oneDai', oneDai)
          const oneDaiExecutionPrice = oneDai.executionPrice.toSignificant(6)
          const priceWithKeyPressed = oneDaiExecutionPrice * keyPressed
          console.log('priceWithKeyPressed', priceWithKeyPressed)
          var totalPriceMa = priceWithKeyPressed.toString()
          this.finalPrice = totalPriceMa.match(/[0-9]+.[0-9]/).toString()
          console.log('totalPrice ', this.finalPrice)
        } else if (keyPressed.match(/^[0][.][0][1-9]$/)) {
          console.log('third')
          const numbAftPoint = keyPressed.substring(3, 4)
          console.log('numbAftPoint', numbAftPoint)
          this.keyPressedLast = numbAftPoint + '0000000000000000'
          console.log('keyPressedLast', this.keyPressedLast)

          const oneDai = new Trade(route, new TokenAmount(weth, 10000000000000000), TradeType.EXACT_INPUT)
          console.log('oneDai', oneDai)
          const oneDaiExecutionPrice = oneDai.executionPrice.toSignificant(6)
          const priceWithKeyPressed = oneDaiExecutionPrice * keyPressed
          console.log('priceWithKeyPressed', priceWithKeyPressed)
          var totalPriceMan = priceWithKeyPressed.toString()
          this.finalPrice = totalPriceMan.match(/[0-9]+.[0-9]/).toString()
          console.log('totalPrice ', this.finalPrice)
        } else if (keyPressed.match(/^[0][.][0][0][1-9]$/)) {
          console.log('fourth')
          const numbAftPoint = keyPressed.substring(4, 5)
          console.log('numbAftPoint', numbAftPoint)
          this.keyPressedLast = numbAftPoint + '000000000000000'
          console.log('keyPressedLast', this.keyPressedLast)

          const oneDai = new Trade(route, new TokenAmount(weth, 1000000000000000), TradeType.EXACT_INPUT)
          console.log('oneDai', oneDai)
          const oneDaiExecutionPrice = oneDai.executionPrice.toSignificant(6)
          const priceWithKeyPressed = oneDaiExecutionPrice * keyPressed
          console.log('priceWithKeyPressed', priceWithKeyPressed)
          var totalPriceManu = priceWithKeyPressed.toString()
          this.finalPrice = totalPriceManu.match(/[0-9]+.[0-9]/).toString()
          console.log('totalPrice ', this.finalPrice)
        } else if (keyPressed.match(/^[0][.][0][0][0][1-9]$/)) {
          console.log('fifth')
          const numbAftPoint = keyPressed.substring(5, 6)
          console.log('numbAftPoint', numbAftPoint)
          this.keyPressedLast = numbAftPoint + '00000000000000'
          console.log('keyPressedLast', this.keyPressedLast)

          const oneDai = new Trade(route, new TokenAmount(weth, 100000000000000), TradeType.EXACT_INPUT)
          console.log('oneDai', oneDai)
          const oneDaiExecutionPrice = oneDai.executionPrice.toSignificant(6)
          const priceWithKeyPressed = oneDaiExecutionPrice * keyPressed
          console.log('priceWithKeyPressed', priceWithKeyPressed)
          var totalPriceManua = priceWithKeyPressed.toString()
          this.finalPrice = totalPriceManua.match(/[0-9]+.[0-9]/).toString()
          console.log('totalPrice ', this.finalPrice)
        } else {
          console.log('placedAmount', this.placedAmount)
          this.$toasted.error('Please write in this form / 1 , 0.1 , 0.01 , 0.001 , 0.0001 /')
        }

        const trade = new Trade(route, new TokenAmount(weth, this.keyPressedLast), TradeType.EXACT_INPUT)
        console.log('trade', trade)

        this.totalTokenPrice = trade.executionPrice.toSignificant(6)
        this.oneTokenPrice = route.midPrice.invert().toSignificant(6)

        console.log('with invert', route.midPrice.invert().toSignificant(6))
        console.log('trade execution price', trade.executionPrice.toSignificant(6))

        const slippageTolerance = new Percent('50', '10000') //  50 bips = 0.5% 1 bip = 0.001                      //slippage tolerance
        console.log('slippageTolerance', slippageTolerance)

        const amountOutMin = trade.minimumAmountOut(slippageTolerance).raw
        console.log('amountOutMin', amountOutMin)

        this.minAmountOut = amountOutMin.toString()
        console.log('minAmountOut', this.minAmountOut)

        const forValue = trade.inputAmount.raw
        console.log('value with out string', forValue)

        this.value = forValue.toString()
        console.log('value with string: ', this.value)

        if (this.ethBalance === '0') {
          this.swap = 'false'
        } else {
          this.swap = 'true'
        }
        this.dai = dai
        this.weth = weth
        this.tradeIs = trade
      } else if (e.key.match(this.charRegex)) {
        console.log('this is character')
        // this.$toasted.error('Please enter only numbers.')
      }
    },
    async swapIt () {
      // if (this.transactionSuccess === 'false') {
      //   setTimeout(() => {
      //     this.$toasted.error('Oops, something wasnt right!')
      //     this.swap = 'true'
      //   }, 40000)
      // }
      if (this.placedAmount === '') {
        this.$toasted.error('Please first enter the amount.')
        this.swap = 'true'
      } else {
        if (this.placedAmount > this.withoutPoint && this.placedAmount !== 9) {
        // if (this.placedAmount > this.withoutPoint) {
          this.swap = 'true'
          console.log('placedAmount', this.placedAmount)
          console.log('withoutPoint', this.withoutPoint)
          this.$toasted.error('insufficant Balance ' + this.withoutPoint)
        } else {
          // } else if (this.withoutPoint > this.placedAmount) {
          this.swap = 'pending'
          const path = [this.weth.address, this.dai.address]
          console.log('path', path)

          // deadline is 20 mnts in seconds
          const deadline = Math.floor(Date.now() / 1000) + 60 * 20
          console.log('deadline', deadline)

          const provider = ethers.getDefaultProvider('mainnet', {
            infura: 'https://mainnet.infura.io/v3/38a3d4450c784956877a1bd2fe75c406'
          })
          console.log('provider', provider)

          // const signer = new ethers.Wallet('db62a52693de0e6f98ec39b7bb3a12257dd49bb6459899b820ba9f468e99b416');  // acount 2
          // const signer = new ethers.Wallet('3bd56eea65f9728f2fca4d9f1e5e8499bd1d174dcf10b14dbaebbc6f71bf775a');  // acount 1
          const privateKey = '2883ae36fd4bbfc8bf9a27b69b424f59bd356c59a18dab36508e69db38db99cd'

          const signer = new ethers.Wallet(privateKey)
          console.log('signer', signer)

          const account = signer.connect(provider)
          console.log('account', account)

          const uniswap = new ethers.Contract(
            '0x7a250d5630B4cF539739dF2C5dAcb4c659F2488D',
            uniswapAbi,
            account
          )
          console.log('Uniswap', uniswap)

          const to = '0x9DD0F556cBE1e28217e96147a7DB5F155b991B10'
          const minAmountOut = this.minAmountOut
          const value = this.value

          if (this.transactionSuccess === 'false') {
            setTimeout(() => {
              this.$toasted.error('Request Timeout!')
              this.swap = 'true'
            }, 20000)
          }

          const tx = await uniswap.swapExactETHForTokens(
            minAmountOut,
            path,
            to,
            deadline,
            // {gasLimit: 2000000000000000}
            { value, gasPrice: 20e9 }
          )

          console.log(`Transaction hash: ${tx.hash}`)
          this.transactionHash = tx.hash
          this.transactionSuccess = 'true'

          const receipt = await tx.wait()
          console.log('only receipts', receipt)
          console.log('transaction was not mine', receipt.blockNumber)

          this.swap = 'true'
        }
      }
    },
    async loadWeb3 () {
      this.swap = 'pending'
      if (window.ethereum) {
        window.web3 = new Web3(window.ethereum)
        await window.ethereum.enable()
      } else if (window.web3) {
        window.web3 = new Web3(window.web3.currentProvider)
      } else {
        this.swap = 'false'
        window.alert(
          'Non-Ethereum browser detected. You should consider trying MetaMask!'
        )
      }
      const web3 = window.web3
      this.networkId = await web3.eth.net.getId()
      console.log('networkId', this.networkId)

      if (this.networkId !== 1) {
        this.$toasted.error('Please login with mainnet wallet')
        this.swap = 'false'
      } else if (this.networkId === 1) {
        const accounts = await web3.eth.getAccounts()
        this.accountAddress = accounts[0]
        console.log('accounts', this.accountAddress)

        this.ethBalance = await web3.eth.getBalance(this.accountAddress)
        console.log('ethBalance', this.ethBalance)
        if (this.ethBalance.length === 19) {
          this.withoutPoint = this.ethBalance.substring(0, 1)
          console.log('balance without point', this.withoutPoint)
        } else if (this.ethBalance.length === 20) {
          this.withoutPoint = this.ethBalance.substring(0, 2)
          console.log('balance without point', this.withoutPoint)
        } else if (this.ethBalance.length === 21) {
          this.withoutPoint = this.ethBalance.substring(0, 3)
          console.log('balance without point', this.withoutPoint)
        }

        this.connectWallet = true
        this.infoDiv = 'connected'
        this.swap = 'true'

        // Load Token

        // const chainId = ChainId.MAINNET
        // console.log(chainId)
        // const tokenAddress = '0x6B175474E89094C44Da98b954EedeAC495271d0F'

        // const tokenData = await Fetcher.fetchTokenData(chainId, tokenAddress)
        // console.log('tokenData', tokenData)
      }
    }
  },
  mounted () {
    var websiteModeTheme = localStorage.getItem('WebsiteIndexmode')
    console.log('websiteModeTheme', websiteModeTheme)
    if (websiteModeTheme === null) {
      this.$store.state.changeModeIndexWebsite = 'lightTheme'
      this.changeModeIndex = 'lightTheme'
    } else {
      this.changeModeIndex = websiteModeTheme
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.helloForLightTheme {
  background-color: white;
  color: black;
}
.helloForDarkTheme {
  background-color: #212121;
  color: white;
}
.navbarForLightTheme {
  background-color: white;
}
.navbarForDarkTheme {
  background-color: #212121;
}
.navbar {
  position: fixed;
  top: 0px;
  width: 100%;
  color: #000;
  z-index: 1111;
  height: 50px;
  border-bottom: 1px solid rgb(230, 230, 230);
}
.navbar-nav .nav-link {
  padding-right: 0 !important;
  padding-left: 15px !important;
}
.global-status {
  margin-top: -40px;
  width: 95%;
  white-space: nowrap;
  overflow: auto hidden;
  margin-left: 10px;
}

.global-status-heading {
  font-size: 13px;
}

.globalstatusDetailForLightTheme {
  color: blue;
}
.globalstatusDetailForDarkTheme {
  color: rgb(0, 187, 212);
}
.global-status-detail {
  font-size: 13px;
}

.footer {
  height: 110px;
  width: 100%;
  padding-top: 17px;
  bottom: 0;
  position: relative;
  font-size: 16px;
}

.footer span {
  font-size: 16px;
}

.footer-dot {
  font-size: 17px;
}

.divider {
  position: relative;
  top: -17px;
  width: 100%;
}

.divide {
  position: relative;
  top: -17px;
  width: 90%;
  border: none;
  // border-bottom: 1px solid rgb(255, 255, 255);
  border-bottom: 1px solid #e6e6e6;
}

.coinSymbol {
  text-transform: uppercase;
}

.loading_class {
  vertical-align: sub;
  width: 140px;
  margin: 0 auto;
  position: absolute;
  left: 45%;
  transform: translateX(-50%);
}

.loading_text {
  left: 52%;
  transform: translateX(-50%);
  font-size: 23px;
  margin-top: 50px;
}

.loading-div {
  margin-bottom: 79px;
}
.changeColorSiteForLight {
  background-color: white;
}
.changeColorSiteForDark {
  background-color: #212121;
}
// change color site
.change-color-site {
  width: auto;
  height: 45px;
  border: none;
  // box-shadow: 0px 1px 40px rgba(50, 50, 93, 0.1), 0 3px 6px rgba(0, 0, 0, 0.08);
}

.sun-like,
.red-btn {
  margin-right: 5px;
  margin-left: 5px;
}

.sun-icon,
.moon-icon {
  width: 20px;
  height: 20px;
}
@media only screen and (min-width: 900px) {
  .global-status {
    position: absolute;
    top: 35px;
    text-align: end;
    width: 90%;
    margin-left: 80px;
  }

  .navbar {
    width: 90%;
    position: relative;
    top: 50px;
    margin: 0 auto;
  }

  .logo-2,
  .side-bar {
    display: none;
  }
}
.logo1ForLightTheme {
  color: white !important;
}
.logo1ForDarkTheme {
  color: #212121 !important;
}

.logo-1 {
  color: white;
}

.add-img {
  margin-top: -30px;
}
.add-img2 {
  width: 70%;
  margin-top: -30px;
  height: 240px;
  border-radius: 13px;
  margin-left: 220px;
}
#curvedArrow{
  margin-top: -40px;
}
@media only screen and (max-width: 360px) {
  #curvedArrow{
    // margin-right: 50px;
    position: relative !important;
    right: 50px !important;
  }
}
@media only screen and (max-width: 900px) {
  .global-status {
    margin-top: -110px;
    margin-bottom: -20px;
  }
  .logo-1 {
    display: none;
  }
  #marginTopMinusFive{
    position: relative;
    top: -5px;
  }
  .change-color-site {
    float: left;
    margin-left: 20px;
    margin-top: 30px;
    border-radius: 10px;
  }
  .navbar {
    width: 100%;
    margin-bottom: -60px;
  }
  .add-img {
    width: 70%;
    height: 150px;
    position: relative;
    left: -170px;
  }
  .add-img2 {
    width: 70%;
    height: 200px;
    position: relative;
    left: -170px;
    border-radius: 5px;
    margin-top: -20px;
  }

  .checkout {
    overflow: auto;
    width: 110%;
    margin-top: 430px;
    margin-left: 30px;
  }
  .checkoutInfo {
    position: relative;
    top: -130px;
    left: -90px;
  }
  .checkout-div {
    width: 90%;
  }
  .checkoutInfo {
    width: 90%;
    margin-left: 20px;
    margin-top: 250px;
  }
  .cross {
    top: 110px;
    left: 370px;
  }
  .review-btn {
    margin-left: 30px;
  }
}
@media only screen and (max-width: 1640px) {
  .review-btn {
    margin-left: 30px;
  }
}
@media only screen and (max-width: 1500px) {
  .review-btn {
    padding: 20px 70px;
  }
}
@media only screen and (max-width: 1400px) {
  .review-btn {
    margin-left: 17px;
  }
}
@media only screen and (max-width: 1300px) {
  .review-btn {
    padding: 20px 60px;
  }
}
</style>
