<template>
  <header class="app-header">
    <ul class="left">
      <li class="apple">
        <i class="fa fa-apple"></i>
        <div class="submenu">
          <ul>
            <li>About This Mac</li>
            <li>Software Update...</li>
            <li>Mac OS X Software...</li>
            <li class="spacer"></li>
            <li>System Preferences...</li>
            <li class="hasSubMenu">Dock</li>
            <li class="spacer"></li>
            <li class="hasSubMenu">Recent Items</li>
            <li class="spacer"></li>
            <li class="shortcut" shortcut="&#x2325;&#x2318;&#x238B;">Force Quit...</li>
            <li class="spacer"></li>
            <li>Sleep</li>
            <li>Restart...</li>
            <li>Shut Down...</li>
            <li class="spacer"></li>
            <li class="shortcut" shortcut="&#x21E7;&#x2318;Q">Log Out Jack Harner...</li>
          </ul>
        </div>
      </li>
      <li><strong>Finder</strong>
        <div class="submenu">
          <ul>
            <li>About Finder</li>
            <li class="spacer"></li>
            <li class="shortcut" shortcut="&#x2318;,">Preferences...</li>
            <li class="spacer"></li>
            <li class="shortcut" shortcut="&#x21E7;&#x2318;&#x232b;">Empty Trash...</li>

            <li>Secure Empty Trash...</li>
            <li class="spacer"></li>
            <li class="hasSubMenu">Services</li>
            <li class="spacer"></li>
            <li class="shortcut" shortcut="&#x2318;H">Hide Finder</li>

            <li class="shortcut" shortcut="&#x2325;&#x2318;H">Hide Others</li>

            <li class="noChoice">Show All</li>
          </ul>
        </div>
      </li>
      <li>Edit
        <div class="submenu">
          <ul>
            <li class="noChoice shortcut" shortcut="&#x2318;Z">Undo</li>
            <li class="noChoice shortcut" shortcut="&#x21E7;&#x2318;Z">Redo</li>
            <li class="spacer"></li>
            <li class="shortcut" shortcut="&#x2318;X">Cut</li>
            <li class="shortcut" shortcut="&#x2318;C">Copy</li>
            <li class="shortcut" shortcut="&#x2318;V">Paste</li>
            <li class="shortcut" shortcut="&#x2318;A">Select All</li>
            <li class="spacer"></li>
            <li>Show Clipboard</li>
            <li class="spacer"></li>
            <li class="shortcut" shortcut="fn fn">Start Dictation</li>
            <li>Special Characters...</li>
          </ul>
        </div>
      </li>
    </ul>
    <ul class="right">
      <li id="volume-icon-li">
        <i class="fa fa-volume-off" id="volume-icon"></i>
        <div class="submenu">
          <ul class="volume">
            <li class="volume">
              <div>
                <input type="range" min="0" max="100" value="0" id="volume">
              </div>
            </li>
          </ul>
        </div>
      </li>
      <li><span id="clock"></span>
        <div class="submenu">
          <ul>
            <li id="date" class="noChoice"></li>
            <li class="spacer"></li>
            <li>View as Analog</li>
            <li>View as Digital</li>
            <li class="spacer"></li>
            <li>Open Date & Time Preferences...</li>
          </ul>
        </div>
      </li>
      <li>Shamil Frontend
        <div class="submenu">
          <ul>
            <li>
              <a href="http://alisultanov.ru/" target="_blank">Website</a>
            </li>
            <li>
              <a href="#">Log out</a>
            </li>
          </ul>
        </div>
      </li>
      <li>
        <i class="fa fa-search"></i>
      </li>
      <li>
        <i class="fa fa-bars"></i>
      </li>
    </ul>
  </header>
</template>

<script>
    export default {
        name: "AppHeader"
    }
</script>

<style lang="scss" scoped>
  body {
    background: url(https://harnerdesigns.com/wp-content/uploads/2018/05/universe-wallpaper.jpg) center center / cover fixed no-repeat;
    font-family: 'Helvetica', sans-serif;
    margin: 0;
    overflow: hidden;
    padding: 0;
    perspective-origin: 0 0;
  }

  /*--Header--*/
  header {
    background: linear-gradient(to bottom, rgba(230, 230, 230, 1) 0%, rgba(163, 163, 163, 1) 100%);
    display: block;
    font-size: 0.9em;
    height: 1.3em;
    user-select: none;
  }

  header ul {
    margin: 0 5px;
    padding: 0 3px;
  }

  header li {
    display: inline-block;
    line-height: 1.3em;
    padding: 0 0.5em;
    position: relative;
    cursor: default;
    &:hover > .submenu {
      display: block;
    }
  }

  header .left {
    float: left;
  }

  header .right {
    float: right;
  }

  a {
    color: #000;
    text-decoration: none;

    &:hover {
      text-decoration: underline;
    }
  }

  .apple i {
  }

  header .selected {
    background: -webkit-gradient(linear, left top, left bottom, color-stop(0%, rgba(89, 120, 245, 1)), color-stop(100%, rgba(51, 94, 246, 1)));
    color: #fff;
    border-bottom: 0.1em solid #5978F5;
  }

  /*--Menus--*/
  .visible {
    display: block;
  }

  .shortcut:after {
    content: attr(shortcut);
    float: right;
    padding-right: 20px;
  }

  .search {
    padding: 5px 10px;
  }

  .noChoice {
    color: #adadad;

    &:hover {
      background: #fff;
      color: #adadad;
    }
  }

  #volume-icon-li {
    width: 1em;
  }

  .submenu {
    display: none;
    position: absolute;
    left: 0;
    top: 100%;
    z-index: 10;

    & input[type="text"] {
      border-radius: 2em;
      border: 1px solid #333;
      height: 2em;
      padding: 0 10px;
    }

    & input[type="range"] {
      transform: rotate(-90deg);
      margin-left: -50px;
      margin-top: 65px;
    }

    & > ul {
      background: #fff;
      border-radius: 0 0 5px 5px;
      color: #333;
      font-size: 14px;
      margin: 0;
      overflow: hidden;
      padding: 0 5px 0 0;
      width: auto;
      white-space: nowrap;

      &.volume {
        height: 10em;
        width: 2em;
        margin: 0;
        padding: 0;
        position: absolute;
        overflow: visible;

        & li {
          margin: 0;
          padding: 0;
        }
      }

      & > li {
        display: block;
        vertical-align: middle;
        float: none;
        margin-right: 75px;
        font-weight: 400;
        padding: 2.5px 0 2.5px 15px;
        width: 100%;

        &.spacer {
          background: rgba(211, 211, 211, 0.8);
          height: 1px;
          margin: 2px 0;
          padding: 0;
          width: 102%;
          position: relative;

          &:hover {
            background: rgba(211, 211, 211, 0.8);
          }
        }
      }
    }

    & li:hover:not(.volume) {
      background: -webkit-gradient(linear, left top, left bottom, color-stop(0%, rgba(89, 120, 245, 1)), color-stop(100%, rgba(51, 94, 246, 1)));
      color: #fff;
    }

    & .hasSubMenu:after {
      content: "\f04b";
      font-family: FontAwesome, sans-serif;
      font-size: 0.8em;
      display: inline-block;
      position: absolute;
      right: 25px;
    }
  }

</style>
