# 🧪 Minimal Firefox

This theme is designed to give Firefox a more minimalist appearance, removing some interface elements, focusing on keyboard-centric navigation, and adding dynamic colors based on the web page's colors.

> ⚠️ Warning!
Useful elements such as the back, forward, and close tab buttons have been removed! If you don't prefer keyboard-centric navigation, this theme may not be suitable for you.

## Preview
![Tailwindcss Docs](https://github.com/pdro-lucas/my-firefox-customization/blob/main/images/preview1.png)
> _Tailwindcss Documentation_

![Tailwindcss Docs](https://github.com/pdro-lucas/my-firefox-customization/blob/main/images/preview1.1.png)
> _Tailwindcss Documentation - Sidebar Open_

![Tailwindcss Docs](https://github.com/pdro-lucas/my-firefox-customization/blob/main/images/preview2.png)
> _Linear Website_

![Tailwindcss Docs](https://github.com/pdro-lucas/my-firefox-customization/blob/main/images/preview3.png)
> _Netflix Website_


## How to install
To install this theme, you need to enable some browser settings:
- Type `about:config` into your URL bar
- Search for `toolkit.legacyUserProfileCustomizations.stylesheets` and set it to `true`
- Go to your profile folder
  - Type `about:profiles` into your URL bar
  - Look for the profile with the message `This is the profile in use and it cannot be deleted`
  - Open the Root Directory
  - Alternatively, access it through your file explorer: `C:\Users\[YOUR-USER]\AppData\Roaming\Mozilla\Firefox\Profiles\[YOUR-PROFILE]`
- Place the `chrome` folder in your profile folder

## Configuration

For the best results, remove all `flexible spaces` from your toolbar and place necessary tools in the `expanded menu`.

### Extensions

To manage tabs vertically and get adaptive colors throughout the browser, install the following extensions:

- Adaptive tab bar color: [🔗Download here](https://github.com/easonwong-de/Adaptive-Tab-Bar-Color)
- Tab center reborn: [🔗 Download here](https://addons.mozilla.org/en-GB/firefox/addon/tabcenter-reborn/).

### Configuring Tab Center Reborn
To configure the extension, follow the steps below:

- Type `about:addons` into your URL bar
- Go to `Tab Center Reborn` options
- Paste the following CSS code into `Advanced -> Custom Stylesheet` and click on `Save CSS`

```css
#topmenu {
  border-bottom: 1px solid var(--tab-active-background) !important;
  padding: 4px 4px 4px 10px;
  margin-bottom: 10px;
}

#tablist-wrapper,
#pinnedtablist { background: var(--uc-base-colour);}

.tab:hover,
.tab.active { background: var(--uc-highlight-colour);}


.tab:hover {
  transform: scale(1.05);
}

#tablist-wrapper .tab-title-wrapper,#filterbox-icon, #filterbox-input {
  opacity: 0;
  transform: translateX(-10px);

  transition: all 200ms ease;
  transition-delay: 0ms;

}

#filterbox-input { width: 100%; border-radius: 6px !important; }
#filterbox-icon { z-index: 100; }

body:hover #tablist-wrapper .tab-title-wrapper, body:hover #filterbox-icon, body:hover #filterbox-input {
  opacity: 1;
  transform: translateX(0);

  transition-delay: 50ms;

}

#settings { display: none; }

.tab,
.tab.active { border-bottom: none !important; }

.tab.active { background: var(--input-background) !important; width: 16% !important }

body:hover .tab.active{ width: 95% !important; }

#pinnedtablist.compact:not(:empty) { padding-left: 6px; }

#pinnedtablist:not(.compact) .tab { padding: 8px; }
#tablist .tab { width: 90%; margin-left: 5px; border-radius: 6px}



.tab { overflow: visible; transition: all 0.1s cubic-bezier(.79,.14,.15,.86) !important;}



#pinnedtablist:not(.compact) .tab[data-identity-color] .tab-context::before,
#tablist .tab[data-identity-color] .tab-context::before {

  position: absolute;
  top: 4px; bottom: 4px;

  width: 2px;

  background: var(--identity-color);

  content: '';

}

#tablist { gap: 2px; }
#tablist .tab[data-identity-color] .tab-context::before { left: -3px; }

.tab-icon { width: 14px; }

#pinnedtablist:not(.compact) .tab .tab-pin,
.tab-close,
.tab-loading-burst { display: none; }

#pinnedtablist:not(.compact) .tab[data-identity-color] .tab-context { box-shadow: none !important; }

[data-identity-color="blue"]      { --identity-color: var(--uc-identity-colour-blue); }
[data-identity-color="turquoise"] { --identity-color: var(--uc-identity-colour-turquoise); }
[data-identity-color="green"]     { --identity-color: var(--uc-identity-colour-green); }
[data-identity-color="yellow"]    { --identity-color: var(--uc-identity-colour-yellow); }
[data-identity-color="orange"]    { --identity-color: var(--uc-identity-colour-orange); }
[data-identity-color="red"]       { --identity-color: var(--uc-identity-colour-red); }
[data-identity-color="pink"]      { --identity-color: var(--uc-identity-colour-pink); }
[data-identity-color="purple"]    { --identity-color: var(--uc-identity-colour-purple); }

.can-scroll-top #tablist { mask: linear-gradient(transparent, var(--uc-shadow-colour) 40px); }
.can-scroll-bottom #tablist { mask: linear-gradient(var(--uc-shadow-colour) calc(100% - 40px), transparent); }
.can-scroll-bottom.can-scroll-top #tablist { mask: linear-gradient(transparent, var(--uc-shadow-colour) 40px calc(100% - 40px), transparent); }
#topshadow, #bottomshadow { display: none; }
#main-window[titlepreface^="[1] "] #sidebar-box[sidebarcommand="tabcenter-reborn_ariasuni-sidebar-action"] {
  visibility: collapse;
}
```

## Todo

- [ ] Modify Dev Tools colors
- [ ] Add support for light theme
- [ ] Add transparency and blur effects
- [ ] Modify homepage styles
- [ ] Add accent color

## Credits

This theme is based on the [Cascade](https://github.com/andreasgrafen/cascade) theme created by [Andreas Grafen](https://github.com/andreasgrafen). We highly recommend checking out the original theme.

Updated by [Pedro Lucas](https://github.com/pdro-lucas)
