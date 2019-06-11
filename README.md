# AutoEncoders

a<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<title>AutoEncoder</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>

<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    color: #000 !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.2.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.2.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.2.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.2.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.2.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.2.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=1);
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2);
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=3);
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1);
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1);
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
@media (max-width: 991px) {
  #ipython_notebook {
    margin-left: 10px;
  }
}
[dir="rtl"] #ipython_notebook {
  float: right !important;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#login_widget {
  float: right;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  text-align: center;
  vertical-align: middle;
  display: inline;
  opacity: 0;
  z-index: 2;
  width: 12ex;
  margin-right: -12ex;
}
.alternate_upload .btn-upload {
  height: 22px;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
[dir="rtl"] #tabs li {
  float: right;
}
ul#tabs {
  margin-bottom: 4px;
}
[dir="rtl"] ul#tabs {
  margin-right: 0px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons {
  float: left !important;
}
[dir="rtl"] .list_toolbar .pull-right {
  padding-top: 1px;
  float: left !important;
}
[dir="rtl"] .list_toolbar .pull-left {
  float: right !important;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: baseline;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
#tree-selector {
  padding-right: 0px;
}
[dir="rtl"] #tree-selector a {
  float: right;
}
#button-select-all {
  min-width: 50px;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
[dir="rtl"] #new-menu {
  text-align: right;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
[dir="rtl"] #running .col-sm-8 {
  float: right !important;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI colors. */
.ansibold {
  font-weight: bold;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  border-left-width: 1px;
  padding-left: 5px;
  background: linear-gradient(to right, transparent -40px, transparent 1px, transparent 1px, transparent 100%);
}
div.cell.jupyter-soft-selected {
  border-left-color: #90CAF9;
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected {
  border-color: #ababab;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 5px, transparent 5px, transparent 100%);
}
@media print {
  div.cell.selected {
    border-color: transparent;
  }
}
div.cell.selected.jupyter-soft-selected {
  border-left-width: 0;
  padding-left: 6px;
  background: linear-gradient(to right, #42A5F5 -40px, #42A5F5 7px, #E3F2FD 7px, #E3F2FD 100%);
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
  border-left-width: 0px;
  padding-left: 6px;
  background: linear-gradient(to right, #66BB6A -40px, #66BB6A 5px, transparent 5px, transparent 100%);
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  padding: 0.4em;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. We need the 0 value because of how we size */
  /* .CodeMirror-lines */
  padding: 0;
  border: 0;
  border-radius: 0;
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul {
  list-style: disc;
  margin: 0em 2em;
  padding-left: 0px;
}
.rendered_html ul ul {
  list-style: square;
  margin: 0em 2em;
}
.rendered_html ul ul ul {
  list-style: circle;
  margin: 0em 2em;
}
.rendered_html ol {
  list-style: decimal;
  margin: 0em 2em;
  padding-left: 0px;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin: 0em 2em;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
  margin: 0em 2em;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
  margin: 0em 2em;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
  margin: 0em 2em;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  background-color: #fff;
  color: #000;
  font-size: 100%;
  padding: 0px;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: 1px solid black;
  border-collapse: collapse;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  border: 1px solid black;
  border-collapse: collapse;
  margin: 1em 2em;
}
.rendered_html td,
.rendered_html th {
  text-align: left;
  vertical-align: middle;
  padding: 4px;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget {
  float: right !important;
  float: right;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  margin-top: 6px;
}
span.save_widget span.filename {
  height: 1em;
  line-height: 1em;
  padding: 3px;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  display: none;
}
.command-shortcut:before {
  content: "(command)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>
<style type="text/css">
    /*This file contains any manual css for this page that needs to override the global styles.
This is only required when different pages style the same element differently. This is just
a hack to deal with our current css styles and no new styling should be added in this file.*/

#ipython-main-app {
    position: relative;
}
#jupyter-main-app {
    position: relative;
}

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Deep-Neural-Auto-Encoders-"><center>Deep Neural Auto Encoders </center><a class="anchor-link" href="#Deep-Neural-Auto-Encoders-">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Welcome to this notebook, here we are going to perform a run down analysis on various use-cases based on auto encoders, so hold tight here we go......</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>An autoencoder network is actually a pair of two connected networks, an encoder and a decoder. An encoder network takes in an input, and converts it into a smaller, dense representation, which the decoder network can use to convert it back to the original input.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="1.-Auto-Encoders-for-Dimensionality-Reduction">1. Auto Encoders for Dimensionality Reduction<a class="anchor-link" href="#1.-Auto-Encoders-for-Dimensionality-Reduction">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><img src="http://ml.qizy.tech/wp-content/uploads/2017/12/43284732563234793247823.png?w=1400" alt=""></p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">keras.layers</span> <span class="k">import</span> <span class="n">Input</span><span class="p">,</span> <span class="n">Dense</span>
<span class="kn">from</span> <span class="nn">keras.models</span> <span class="k">import</span> <span class="n">Model</span><span class="p">,</span><span class="n">Sequential</span>
<span class="kn">from</span> <span class="nn">keras.layers</span> <span class="k">import</span> <span class="n">Input</span><span class="p">,</span> <span class="n">Dense</span><span class="p">,</span> <span class="n">Conv2D</span><span class="p">,</span> <span class="n">MaxPooling2D</span><span class="p">,</span> <span class="n">UpSampling2D</span><span class="p">,</span> <span class="n">Lambda</span><span class="p">,</span> <span class="n">Layer</span><span class="p">,</span> <span class="n">Add</span><span class="p">,</span> <span class="n">Multiply</span>
<span class="kn">from</span> <span class="nn">keras</span> <span class="k">import</span> <span class="n">backend</span> <span class="k">as</span> <span class="n">K</span>
<span class="kn">from</span> <span class="nn">keras.losses</span> <span class="k">import</span> <span class="n">mse</span><span class="p">,</span> <span class="n">binary_crossentropy</span>
<span class="kn">from</span> <span class="nn">keras.datasets</span> <span class="k">import</span> <span class="n">mnist</span>
<span class="kn">from</span> <span class="nn">keras.datasets</span> <span class="k">import</span> <span class="n">fashion_mnist</span>
<span class="kn">import</span> <span class="nn">warnings</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">from</span> <span class="nn">scipy.stats</span> <span class="k">import</span> <span class="n">norm</span>
<span class="kn">import</span> <span class="nn">time</span>
<span class="c1">#### Import ends</span>


<span class="n">warnings</span><span class="o">.</span><span class="n">filterwarnings</span><span class="p">(</span><span class="s2">&quot;ignore&quot;</span><span class="p">)</span>

<span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">_</span><span class="p">),</span> <span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="n">_</span><span class="p">)</span> <span class="o">=</span> <span class="n">fashion_mnist</span><span class="o">.</span><span class="n">load_data</span><span class="p">()</span> <span class="c1"># download the data set and split it into train and test</span>

<span class="c1"># scale the values of pixel between 0 and 1</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">x_train</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;float32&#39;</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.</span>
<span class="n">x_test</span> <span class="o">=</span> <span class="n">x_test</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;float32&#39;</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.</span>

<span class="c1"># reshape the 28*28 image into one long vector of size 784</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">x_train</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="nb">len</span><span class="p">(</span><span class="n">x_train</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">prod</span><span class="p">(</span><span class="n">x_train</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">:])))</span>
<span class="n">x_test</span> <span class="o">=</span> <span class="n">x_test</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="nb">len</span><span class="p">(</span><span class="n">x_test</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">prod</span><span class="p">(</span><span class="n">x_test</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">:])))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>


<div class="output_subarea output_stream output_stderr output_text">
<pre>/opt/anaconda3/lib/python3.6/site-packages/h5py/__init__.py:36: FutureWarning: Conversion of the second argument of issubdtype from `float` to `np.floating` is deprecated. In future, it will be treated as `np.float64 == np.dtype(float).type`.
  from ._conv import register_converters as _register_converters
Using TensorFlow backend.
</pre>
</div>
</div>

<div class="output_area">

<div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Downloading data from http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/train-labels-idx1-ubyte.gz
32768/29515 [=================================] - 0s 14us/step
Downloading data from http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/train-images-idx3-ubyte.gz
26427392/26421880 [==============================] - 12s 0us/step
Downloading data from http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/t10k-labels-idx1-ubyte.gz
8192/5148 [===============================================] - 0s 42us/step
Downloading data from http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/t10k-images-idx3-ubyte.gz
4423680/4422102 [==============================] - 1s 0us/step
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">&quot;We have </span><span class="si">{}</span><span class="s2"> training examples and </span><span class="si">{}</span><span class="s2"> test examples&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">x_train</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">x_test</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>We have 60000 training examples and 10000 test examples
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Lets first have a look at the data set, below is a function that will help us display the images.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span> <span class="k">def</span> <span class="nf">show_images</span><span class="p">(</span><span class="n">data_array</span><span class="p">,</span><span class="n">n</span><span class="p">,</span><span class="n">decoded_array</span><span class="p">,</span><span class="n">title</span><span class="p">,</span><span class="n">reconstruct</span><span class="o">=</span><span class="kc">False</span><span class="p">,):</span>
    <span class="n">fig</span><span class="o">=</span><span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">20</span><span class="p">,</span> <span class="mi">4</span><span class="p">))</span> <span class="c1"># set the layout size</span>
    <span class="n">fig</span><span class="o">.</span><span class="n">suptitle</span><span class="p">(</span><span class="n">title</span><span class="p">)</span> <span class="c1"># set the plot title</span>
    <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">n</span><span class="p">):</span>
        <span class="c1"># display original</span>
        <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="n">n</span><span class="p">,</span> <span class="n">i</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">data_array</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="mi">28</span><span class="p">,</span> <span class="mi">28</span><span class="p">))</span> <span class="c1"># reshape to 28*28 shape and display in subplot</span>
        <span class="n">plt</span><span class="o">.</span><span class="n">gray</span><span class="p">()</span> <span class="c1"># grayscale the image </span>
        <span class="n">ax</span><span class="o">.</span><span class="n">get_xaxis</span><span class="p">()</span><span class="o">.</span><span class="n">set_visible</span><span class="p">(</span><span class="kc">False</span><span class="p">)</span> <span class="c1"># hide x axis</span>
        <span class="n">ax</span><span class="o">.</span><span class="n">get_yaxis</span><span class="p">()</span><span class="o">.</span><span class="n">set_visible</span><span class="p">(</span><span class="kc">False</span><span class="p">)</span> <span class="c1"># hide y axis</span>
    
        <span class="k">if</span> <span class="n">reconstruct</span><span class="o">==</span><span class="kc">True</span><span class="p">:</span> <span class="c1"># check if we want to create a dual comparision plot</span>
            <span class="n">ax</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="n">n</span><span class="p">,</span> <span class="n">i</span> <span class="o">+</span> <span class="mi">1</span> <span class="o">+</span> <span class="n">n</span><span class="p">)</span>
            <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">decoded_array</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="mi">28</span><span class="p">,</span> <span class="mi">28</span><span class="p">))</span>
            <span class="n">plt</span><span class="o">.</span><span class="n">gray</span><span class="p">()</span>
            <span class="n">ax</span><span class="o">.</span><span class="n">get_xaxis</span><span class="p">()</span><span class="o">.</span><span class="n">set_visible</span><span class="p">(</span><span class="kc">False</span><span class="p">)</span>
            <span class="n">ax</span><span class="o">.</span><span class="n">get_yaxis</span><span class="p">()</span><span class="o">.</span><span class="n">set_visible</span><span class="p">(</span><span class="kc">False</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">show_images</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span><span class="mi">10</span><span class="p">,</span><span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([</span><span class="mi">1</span><span class="p">]),</span><span class="s1">&#39;Original Image&#39;</span><span class="p">,</span> <span class="kc">False</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABHEAAACPCAYAAAB9P0c7AAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDIuMi4yLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvhp/UCwAAIABJREFUeJzt3XvUXdO9//Hv6unNPVeJJBpCItJIVFBSt4Si2riFcqi2x2DUZVTroFpah5ODouMUbX9t6RlVVdGjqKNuVYfShiiNShqEkEQiEbkp6lTp+v3x5Jk+8+uZM+vZeW5rP+/XGMaYO2s9a6+91p5zrb3M7/dblGVpAAAAAAAA6Nne0907AAAAAAAAgHXjIQ4AAAAAAEAN8BAHAAAAAACgBniIAwAAAAAAUAM8xAEAAAAAAKgBHuIAAAAAAADUAA9xAABAm4qiOKcoih919LoVtlUWRbFtR2wLAACgmRRlWXb3PgAAgE5WFMXnzewMM9vGzP5iZreY2dfKslzTnfvVlqIoSjMbWZbls20su9/MrivLskMeGAEAANQJM3EAAGhyRVGcYWaXmNlZZraZme1mZsPN7J6iKN6f+Jv3dt0eAgAAoAoe4gAA0MSKotjUzC4wsy+WZXlXWZZ/L8tygZl92loe5Hxm7XrnF0Xxi6IoriuK4i9m9vm1/3adbOuzRVEsLIpiZVEU3yiKYkFRFPvJ31+3tr3V2pCozxVFsagoihVFUZwr29m1KIqHiqJYUxTF0qIovpt6mLSOz7ZPURSLi6L4SlEUy9du69CiKA4qimJeURSriqI4p+r7FkWxf1EUTxdF8UpRFP+vKIrfFkVxgiw/viiKJ4uiWF0Uxd1FUQxv7z4DAACsDx7iAADQ3Caa2QfN7Gb9x7IsXzOzO83s4/LPh5jZL8ysj5n9TNcvimKMmf0/MzvWzLawlhk9Q9fx3nuY2XZmtq+ZnVcUxfZr//1tMzvdzAaY2e5rl5/Szs/VarC1fL6hZnaemV1tLQ+mJpjZnmvfd8S63rcoigHW8tm/Zmb9zexpazl2tnb5oWZ2jpkdbmYDzexBM5ve4D4DAAA0hIc4AAA0twFmtqIsy7faWLZ07fJWD5Vl+cuyLP9RluUbbt0jzOy2six/V5blm9bywGRdifUuKMvyjbIs/2RmfzKz8WZmZVk+Vpblw2VZvrV2VtAPzWzv9n80MzP7u5ldWJbl383shrWf54qyLF8ty/LPZvZnMxtX4X0PMrM/l2V589pjdaWZLZP3+YKZXVyW5ZNrl19kZjsyGwcAAHQlHuIAANDcVpjZgESOmy3WLm/1QmY7Q3R5WZZ/NbOV63hvfQjyVzPb2MysKIpRRVH8qiiKZWtDty6y+GFSe6wsy/Ltte3WB08vyfI3Kr6v/3ylmS2W7Qw3syvWhmKtMbNVZlbYumcjAQAAdBge4gAA0NweMrO/WUsYUFAUxUZm9gkzu1f+OTezZqmZDZO/38Bawo4a8X0ze8paKlBtai1hSkWD2+qo9/Wfr9DX1vKA5wtlWfaR/zYoy3JGF+w3AACAmfEQBwCAplaW5SvWktj4O0VRHFgUxfuKotjKzG60lpkmP624qV+Y2ZSiKCauTQZ8gTX+4GUTaylz/lpRFKPN7OQGt9OR73u7me2wNjHye83sVGvJt9PqB2b2taIoPmxmVhTFZkVRHNlF+w0AAGBmPMQBAKDplWV5qbXMOvmWtTzEmGktM0v2LcvybxW38Wcz+6K15J1Zamavmtlya5nl015nmtkxa7dxtZn9vIFtNCL5vmVZrjCzI83sUmsJExtjZo/a2s9XluUt1lKm/Ya1oVhzrGUmEwAAQJcpWkK+AQAAqiuKYmMzW2MtoUnPd/f+dLSiKN5jLTOVji3L8r7u3h8AAAAzZuIAAICKiqKYUhTFhmvz6XzLzGab2YLu3auOUxTFAUVR9CmK4gP2Tr6ch7t5twAAAAIe4gAAgKoOMbMX1/430syOLptrSu/uZjbfWip2TTGzQ9sotQ4AANBtCKcCAAAAAACoAWbiAAAAAAAA1AAPcQAAAAAAAGqAhzgAAAAAAAA1wEMcAAAAAACAGuAhDgAAAAAAQA3wEAcAAAAAAKAGeIgDAAAAAABQAzzEAQAAAAAAqAEe4gAAAAAAANQAD3EAAAAAAABqgIc4AAAAAAAANcBDHAAAAAAAgBrgIQ4AAAAAAEAN8BAHAAAAAACgBniIAwAAAAAAUAM8xAEAAAAAAKgBHuIAAAAAAADUwHvbs3JRFGVn7QjyyrIsOmI7PeUcfvCDHwztD33oQ9GyVatWhfZf//rX0C7LeNf19QYbbBAt69u3b2j/3//9X2i/9NJL0Xpvv/12e3Z7fa0oy3JgR2yoO8/je9/7zrDRv3//0F65cmW03ltvvbXe76XnVb8za9asidbz343OVMe++P73vz96vckmm4R2nz59QtufMz2n2hf1XJjF/W3TTTeNlv3jH/9oc3srVqyotO+dpCn6Yld63/veF9p///vfu3FP3lHHvujpeKr9cuDA+OupfVOvaX7s+6d/+qfQ3njjjaNlr732WmgvWbIkuY0uRl9sAs3QF1N8P/rb3/4W2lXHQn8N3mijjUJ79erV67F3HYq+2ASauS/2IpX6Yrse4gBmZkXxzvjQ6M3fVlttFdrf/e53o2U33nhjaM+aNSu033zzzWg9vXiOHTs2WnbYYYeF9vz580P7sssui9bzDwM62cKufLPO0q9fv9D+3Oc+F9rXXntttN6yZcvW+72222670B49enRo33TTTdF6PeVHZU81ZMiQ6PU+++wT2occckho+wdx1113XWj/8Y9/DG09F2ZmU6dODe199903WqYPf3R7V111VZVd7yxN0Re7kj5UePHFF7txT3qOjrgW6ng6efLk0D7hhBOi9fRa9eSTT4a2vy7qQ9mJEydGyx5++OHQPuecc0L7jTfeqLy/HfGZHfoiOpR+R71GvrMTJkyIXus95eLFiyttw1+Dd9lll9DWe95uRl8EeoZKfbFoz4DGU7nu09VPVv1FsOr3ZMcddwzto48+OlqmP/R0Boz+HwmzePaFzvRoj3nz5oW2zgTQhwJm8cycu+++O1r2rW99K7TnzJnT0H44j5VluXNHbKgr+6L/v1B6Xr/0pS+Ftv8xoTMtdJlfT//v8wc+8IFo2bBhw0L71ltvDe2HHnooWq8rb4J66v/l+MQnPhG9Pv3000Pb/0jT/yuo/1dfz4VZ/HB00KBBob1gwYJoPZ0lsHTp0mjZK6+8Etp6focOHRqtd++994b2aaedZp2sln1Rj5FZPANKH8CdeOKJ0Xr+fKXoD4377rsvWqbj8sKF79xfHHjggdF6r7/+eqX36gg99bo4YMCA6LWOk/vtt1+0TPuEHjs/FuqDU99PlT7Q9j8wtW/q+dTZr2ZmDzzwQGh/5zvfiZZ1wqyBWvZFxHrSdfE973knU4Te/3l6f2Fmdvzxx4f2GWecEdp+dmlH0HtgvX6effbZ0XpXXHFFpe1V/czrQF9sAj2pL6JhlfoiOXEAAAAAAABqgIc4AAAAAAAANcBDHAAAAAAAgBogJ05N9KQYR40P9slsx40bF9oao2tm9uqrr4a25uHwSWk1Vlgromy22WbRepo/wMcAV/1ea5UdX+FK84Y8+OCDoX3cccdV2nYbmiLe+MgjjwxtzbVy7rnnRutpfg3Np+JzPWiOBa2eYmZ2zz33hPb06dND2+fp+eUvf1lp3ztCT+qL22yzTWiff/750TLN97ThhhtGy1Lx87461ZZbbtnm+/r+pq81B47fpvZ1n4dDc+T4hONnnnlmm/uxHmrZF++///7otZ5/7Vd+LNOxV5OCf+Yzn4nW08pGOkabxedE+/348eOr7Hqn6Ek5cfRc3HbbbdF62hf9cdU+odc+rYBjFvcXHf98hUX9O18RR5NTa1Usv56+1sTkZmY/+MEPQvuWW26xDlDLvohYd18Xq+aE0QT9I0eOjJbp/aB+732eL11P71/8dWuLLbYIbX8N1u3reO3vbbTf/+Y3v4mWHXvssdYWf+/djhw5vaov6nie+/7kfk+kkmg3mvRdk9HPmDEjWqY5PTXvp3+/7u6L3aWjE5q3x09/+tPQ/va3vx3aOt6Yxfdp/hrvkBMHAAAAAACgWfAQBwAAAAAAoAbeu+5V6kWnU+WmT2mJzj322CNaduedd65z22bx1HMfhlBVd07/atTNN98c2sOHD4+WLV++PLT9lESdvq3Hyx8DXU+Xaclqs/j4e346aYqGBfhp7nr899prr9DWUq9mZk899VSl92oWOtVepw9/97vfjdbTMtE6bdCHU+k2HnvssWjZj3/849DeeuutQ/vll19u7243JS2Dmjsmvj/odHDti34ce/7550Nbw6T0783ivu7Pr9LQD+3nZnHZai1tbmb2yU9+MrRvv/325PabnZYRN4v7hC7r169ftN7gwYND+4tf/GJo+1AoDYf1paT1fPn96C1y1+SLL744tJctWxYt05AIDRH228xdFzXMQsdTf93S/rfRRhtFyzR0S9/Lb0PHCx9qdeqpp4a2hrv6UFigM/n+kQoZeuihh6LXO+ywQ2j7fqp9R/ul7wN6HdOxVUPIzeKQqTfffDNapiFUeh+qbbN4vDjmmGOiZdq/Dz300ND2x6Lq7yK0aM8xauR47rPPPtFr/U5qiN9FF10Urafncf/994+WrSM0p8fLhSpXXU/bfr2qfUD7m0/1ofelGpZuZjZq1KjQ1ucL2i/X9d6NYCYOAAAAAABADfAQBwAAAAAAoAZ4iAMAAAAAAFADTZcTR2O5NW512223jdY74YQTQtvHoGo5QY0Vf+SRR6L1cnlwUqXrfJxebhutOV98CdHuMGHChNDWPDg+T43mTfA5azSPhpYTzpU/1phEn0NDj4s/rhrXqMdYS+2amS1evLjN9Tx9L/3umHVK+eMeTXMfDBgwILQ1p4mZ2b/+67+G9rBhw0Jby9yaxXlXfK4N3X4qV1Jvds0114T26aefHi3THDla4tgsjtn1cb9K4/j1XHh/+ctfQtuPp1W2bWa22WabhfYLL7wQLevNeXDUc889F73ebbfdQlvHLx8fn+ovCxYsiF7vueeeob1kyZJomeZw8GN2b6UlhDU3huaPMotzavjrjB5LzXGRKxOs1yN/f6DXWZ8TR9fV/fDb0DHe58vRbU6ZMiW0p0+fbkBXyeWWOOyww0L7ox/9aLRM7/ly943a3/x76Wu9p/Tby937a5/TsdXns9F+umjRomiZ5kX5xCc+Edo+r2dvy4NTNf+JLqv6O+uzn/1s9Prhhx8Obb1+ak5IM7MXX3wxtDX3nJnZM888E9pakvrLX/5ytN7jjz9eaR/ryJ+nqqXbU7lR/fVTfz/4e9TUb07NhWoW54P1982aG1Xzxnm5++1GMBMHAAAAAACgBniIAwAAAAAAUANNF06lU6t0etzkyZOj9fbbb7/Q1umVZnGZQZ3q/PGPfzxa70c/+lFo+3CFqtP0tGyon0ap5Qm726RJk0Jbj48vJ6yfwU9z0yn+Z599dmjrNEOz+HxoycalS5dG6+kUOB+aofulx3innXaK1tNyu7nQMP1cRxxxRLRebwunSoWd5cJt9Nj6sp7axzTMzizuO6lSgr2Zhnj6UqoHH3xwaM+cOTNapt9tPf4+nE37lZ5DH2Kh2/Bhjxpq5UPpUtv46le/mlyvN5s7d270OjWVWEOCzeLz6KdyK51m7Kcz63nVc9qb9e3bN7Q1nMpf8zWcyoc46Xiq161cmeBcOKl+J3JlmHWZ31/tp/66qJ9F74kIp0JnS93fexr24L+/Gkq8Zs2aaFkqfD8XwqH3oY2Wpk7d55jF/VTDvczisM077rgjtDXM0yy+5/LX51wagd5q9OjR0Ws9Zr48+M477xzaej3QUHczswceeCC0NWTKLE5Xscsuu4S2/12jaUGeffbZ1O43hap9KTUO+H/PhTHpdXHLLbcMbR/Gr2HG/t5L00doKHrV0umNYiYOAAAAAABADfAQBwAAAAAAoAaaLpzKTz9rpVPUzMy22mqr0PbTonR65N133x3aH/nIR6L1Lr300tB+9NFHo2WzZ88O7SeffDK0d9111+R+zZgxI1rWGh6hU7i6i4YQ6fRLf+x0CptWyTCLp35effXVoa0Z9s3ikKcf//jHof2FL3whWm/OnDmh3a9fv2iZ7peGun3729+O1jvllFNC208z1f3X0DY/1XLUqFGhPW/ePGt2qenDfvqinoM+ffo09F6pKgP+XMHsyiuvjF5/6UtfCm1f1UIrV2nojQ/h9NXcWvl+r9vw50angOv2tBqVWVxRg3CdtvmKUTpFWPuln3avoag6ldufX92+P8faF331pd5KQ9P0eGlolVl8bnzVDA1N1NDi+fPnR+tpJbFUBU2/zE8h11Ao3fdPfepTyX3yY7eGJ/vQMKAz5UKobr311tDWMCl//6zVVX04lYZV5MKMfB9eX7lQcf3MueuuhsL6kJ8bbrihze01q6ohKxrCPXHixND2If96P/Jf//Vf0TKtCqrjt/+tsfnmmyf37+mnnw5tDa3yKTx0XG72cCrtYz60OGXQoEGhraFtZmb9+/cPbQ2B83+n96+rV6+O1tPvhb9/feyxxyrtY0djJg4AAAAAAEAN8BAHAAAAAACgBniIAwAAAAAAUAO1TyyRK9+l8YQ+Bk5zAfi4bs1xou0//OEP0Xoak6hx4mZmu+++e2gffvjhoe1j1HWbJ5xwQrSstSS3z7fTHcaPHx/aL7zwQmj72GBfclxtuummbf77XXfdFb3WON8xY8aEti/lfcstt4T2lClTomUa16g5IDTe1CyOe/bfA40d1phMn19Ez3VvyImj33U93z43g8Zv50rP58rlpnJJ+HxLvZV+z30M/x577BHaF154YXIbmgfHb2ODDTYIbY2593lv9HXruNUqlT/A//ttt92W3Ee00Jh7s/h6ov3Ix5Br39Qy5T53jp4Tn/dG+3quz/YmmmviwQcfDO1jjz02Wm/s2LGhfdFFF0XLnnrqqUrvpfkbtF9q2yy+jvlxUq+tWhL8a1/7WrSe3pdovgCzeLwYMWJEpX0HOpvehynNA2UWj125/DC5PDWp7TUq9165/dXxW/u6/72j41RHlzjuiVL3nv6z672sXiN1vDaLcwz53JwHHnhgaGsOVW/58uXJZZovZ9WqVaE9dOjQaL3jjz8+tH//+99HyzRHaDNIncNtttkmWu/yyy8Pbc3f5vP9ffjDHw5tn1tQl91///3J9XQs8fe5HZGnUz9z1dxVzMQBAAAAAACoAR7iAAAAAAAA1EBtwqkambI4bdq00N5iiy2S6+k0ZbM4pEBLlmt4glk8ZdFPX9cQHg278uEKp556amj7qcla1rur+emEWpI4V2Jcz5Of5r1y5cpK76XT1PS8+ZAQfS8fpqbLUtNszeLwBD91MRVOpWElZmZ77rlnaP/kJz9Jvlez0GmDepx9H9XQjEbWM4u/a7qe/971VrkyqFpW2pcr3nrrrUNbpxH7Kaj6vdf1fCiUlnEdOHBgch/17xYuXJjcd7RtxYoV0eutttoqtDUsx4c2ar/KTfvV653vizoe+vG2t7r00ktDW/vKfffdF603a9as0PZhxXre9JhrWVuz+PqppZH9udCQAX8OtSyqTiH344OGg/kSzboffkp5b5a6R/UhHFVDPXKhsil+XK5amlf5EEt9754ciqP3ZRr2kAtL8OdM+5IeB9/H9NzoMfHvlQoHX9ffKd0P39/0c2qopA/n9KkIml2uXyn9zuj5mTx5crTeddddF9onnXRSR+xiRMtf6/XBp9LQ8+9TV7RuQ68NdZa6x/DXqs9//vOhnfqN2R76W9eHI8+ePTu0//u//ztapr8lU2O8X5b7vVMVM3EAAAAAAABqgIc4AAAAAAAANcBDHAAAAAAAgBqoTU6cRmJxV69eHdo+J47GQvrYQo13TZWgM4tzvvi4N82TMnHixND2cbFaWs6X2u5OZ599dvRaP6vGyPtYXl3PHy+N99N8QhoPambWr1+/0NZ4YF/qVGMm/XtprLCWnTvqqKOi9fr27RvaPteN5g9IxVubvbucY7PT77CWm/V5alK5bqqW9fTIv9A4P+5ssskmoa1jlx8LNS+Hfu99f9NcKl4qzjdXchNtW7ZsWXKZnuNc6XDl+1vVPBB6be3NtKTsvvvuG9pTp06N1tt///1D2+dNO/nkk0Nbr1XbbrtttJ7ei+h58+Ou9lPfL7Wva54HnwtLr/9+G3ruDz/88NDW+xyzuFRub1D1HlWvhbm/qZofQb8/X//616NlPs9fFXXJdzV+/Pjo9YABA0Jbr1s+r4V+n/2yVN43f3+vr3P5V1Lr5fixWs+Hz6Gh96/6uRrJrdFMqvZFHfceeOCBNtuez/Wp35mqpej9evr7VMdNPy7feeedoT1kyJBo2fDhw83s3b9jmp3mwcnlzaw6rmk+O72+mcXXvr333jtadskll4R27jdObpn+Fq6a34eZOAAAAAAAADXAQxwAAAAAAIAaqE04VSO0dLifopgKCTEze+WVV0JbpzRpOVezfClP3b7uh59KpVMst9xyy3d/iG4yY8aM6PXgwYNDW6d5+3KpG220UWg/88wz0TL97A8//HBo56aq6t/46XGpUtf+7/Rc+OmJ8+bNC21fal7fT7ehpeTMzH75y19ab5IKzfDnR89j6liui55jDafSMES0yJWXXbx4cbRs3Lhxbf6dD1nTMU5Dbfw4ptPS/XRenW6sU96XLFnSxqdo4ctg9/bp4SmpEMPctG5d5sdePa/+HOfKX/dW3/zmN0Nbp2v7a8STTz4Z2lOmTImWnXfeeW1u20//1nOt58afa+0rfkzWPqzhWT487pFHHgltH8Kn0831Gt/bwqdycqETVceyf/7nfw7tj3zkI9GyI488MrR1vF2xYkW03vTp09vcXo4PF//KV74S2v/xH/9RaRtdwV8j9Luux1zvSc3ivuPvG7V/6DJ/bU0t8+NpKqTc70fqb8zy/VmX6faGDRvW5raRlisLnbtn1WW5UJmcgQMHhramq/DfGd1HHb/Neu89UmqszYVP5e4vr7322tDWcdYsPtc+3FnD7HIhbWPGjAnt733ve9EyvU8/7rjjktuI9qnSWgAAAAAAAOhWPMQBAAAAAACogdqEU6WmL/rpazrFTLN3+2nn+tpXZNEs7xpqpZUjzOJQKx+Ko1NSNYRHKx6ZmT3xxBNt7rvZO1WP5s6da13t+9//fvK1ZsQfOXJktJ5WSvDZu3W69Zw5c0J7zZo10Xo6pdVPH60q9X3xVXX0fOi5MDM79thjG3rvZqPn2yw+J7lp4+0Jm2rlp7HqtEc9d36KtIbz+HMMswULFkSv9dzoWOXPtf6dTjn1FeU0HMNP69WxVt+3t07/7UhVK56kQn/9dG3ll+k2Xn/99aq72NRuvvnm0NbqVL5ioVYV+Z//+Z9omYaGLlq0KLRzoVA63vmp4cr3Mb2f0fscHxbdWunEzOzLX/5yctk+++wT2rNmzYrWe/zxx5P71Qxy/SMXzqjT8HW6vq/upRXN5s+fHy3Tafca2uhD/g866KDkfqQcffTR0euPfvSj7d5GV9hpp52i19o/9Pj7+xD93vuwB70Hz1VczIWkqlRIuafLcuv5z6IhHPo7Q0NyzOJzOHPmzOT2e7OqFYX8dyZ1vnLjg6f3s5/73OdC+1e/+lW03vXXXx/a/hy3ju1V7wmaRSOVq3PHSI+5DxHW34uadsXMbPLkyaGt47PeI3j+fvuYY45JrpvCTBwAAAAAAIAa4CEOAAAAAABADfAQBwAAAAAAoAZqkxNH4940BtHHMR511FGhrWWxX3755Wg9jSX18XEan6hlv32MrObS8eXMNE5d38vnktASYzvuuGOb28jlLegOmv9CS5GaxfkvNEbQLD6HmofD5zfJlfpTudwO+nd6nvw51NwCvqw6WuTySVWNR82tlyvlqfR74eNRyYOT5+O4U/3K/7sec+0rfj0dE7SMuJnZJpts0uZ7aQ4DNKZq3intY1VzLvg+q9dazePSm2m5UO1jviz3ww8/HNof+9jHomVjx44N7dR9jqf9z5+n3HUxdW31+6u5F3xum+eeey60X3jhhdCeN29ecn97Gt9v9FjovUnVvCie5k+88MILo2V6j6o5ipYuXRqtp/dWfqzUe8qnnnoqtH1p6WnTpiX3Ufuw7tN//ud/RuuNHj06tCdMmBAte+yxx5Lb72z+u50q9Z0rNZzbpuaT8nkzdSzUe/32lKZW+l3y76X3Orl75dz+al6rqqXme7pcPsaupN+F3Jidy7mzYsWK0NbcYj632g9/+MPQ3mabbaJlrb9fuvNYdIWquYb8eo18XzS3jVl8L9uvX79omebS0e0vX748Wk/Ho/vvvz9a5q8BVTATBwAAAAAAoAZ4iAMAAAAAAFADtQmn0imLuSmuWrpawz78dNRcSJZOM9UwDS0p7repoQZm8bRHDTXw07O0pNhll10WLdMp2N1Np6Lp5/bnQqeRaelLs/Qxrxpq0xHTBHPTHX2p89Tf+SmzzT590X++Rsu+r+97+ynCiOVCD32pYQ0v1T6sY5Wny3y/1+n9fvrowIEDQ9uXxcT6SYXa5qYS58q863q+dLWu60sZ91YjRowIbT1ePqxFw5U0hMYsPq5aJtiHYuh6ufuXHL0v0Wnd2kf9PvpwSP1sGjak4etmcdhVT5ALM1O5+0ulJeXNzKZOnRrael/n7xvnzp0b2npOfZl3Db334bB6fjTkwofF6X6cddZZ0TLd5uzZs0PbX2f13la/n90tty/ad/z51O99LiRLVV2vUbpPftytGmql++RD4P3vk2bQE++7q47FPnXGn/70p9C+4YYbQvtTn/pUtN4BBxwQ2hr2afZOaGt7wgfrqNHz3kjp9fHjx0evn3jiidAeMmRItOzoo48ObR3LL7jggmg9vQbfc8897d4nj5k4AAAAAAAANcBDHAAAAAAAgBrosHCqXPULnean6/lpX+0JB0i54447Qvv1118PbT8dVaei+elZGmqQqs5ilp+2psv0c/ljM27cuND2FXd6Ej1Guc89f/780PbhVFW7NmNkAAAZrklEQVRD4vS9qoZTVZ0enauI4/dX6Xe4PdPXm0HVKilVpxg3WsEhdw5SlSl6k1zFFR8S0bdv39DWqfk+477SCgobbrhhtGyzzTYL7Vzf1n46fPjw5HpVx/veLjXu+e9C1bAr5fu99jnCqVrocdbQaz8+aeiH7zup+wN//FMhcblznRtr9R7Iv5f2dU/HCL2m++nlPS2cSu8fql7DTzvttOj1SSedFNqDBg2KlmmovIYn+ffyf9cqF6adG9v1ftWHZClfffOwww5rc72vf/3r0etTTjkltBctWhQt+8xnPmNmcZWyrnLOOedEr/W+NFepSb+//nvelZVgtc/pNdN/D3T//f2rjisa0ux/7xx66KGhXbW6D6qpGtp69tlnh7a/z/r+978f2scdd1xo+1BM/X3r75+qhoE2s9zvRb1W+fOU+s3pwxL1N2LVseLcc8+NXuv35cYbb6y0jRxm4gAAAAAAANQAD3EAAAAAAABqgIc4AAAAAAAANdBwTpxcvHxn5DPYa6+9QltLOX7sYx+L1tP8DhpP6Mux5eLjdBv6OXOlF338nS8jmtoPLbl7+OGHR8tuu+22NrfR3XK5STQW18do6vHT74gvqZiKa6xaNtf/ncY1+nwEug3ycLTN54LSY5s7P/rd0PPTnhLlqe+C72/arzQ3RW+SywWkeRPMzObMmRPams/A9w89lprLwfftBQsWtPk3ZnG+nKVLl4a2z6GBdRs1alT0Wr/3ev79mKpSOer8a79Mx8cBAwZU3OPmljqWvi+uWrUqtDV3hV9Xt5fLVZEbC3N5B/UarN8Rf/3UUtW+P+u4rmO5z7vV3Xbaaafo9cc//vHQ3m677aJleo3TcWnjjTeO1luzZk1oL1myJFqm45xuL3f91PtEn+9Ez6O/z9Jzp98fnwtFz92uu+4aLXvxxRdDWz+n5vYxM3vmmWdC218fTjzxRDMzu/LKK62rjRgxInqt93n6Pff37QsXLgxt3xer5mDsaPq+/tqq5yZXflz7ol9Pr8/kwOlYqVxx559/frSenh9/P3bEEUeEtvY3fx51bKpLKfHc77RcXhkd1zoiz6VuI9cH/vCHP4T2fffdFy3TEu85uXxzOv7kcs9VxUwcAAAAAACAGuAhDgAAAAAAQA00HE7VnjLLWk5Np4ONHDkyWk+X+dAinUau0yb99Cydntq/f//Q1qmjZvE0Ux/itPnmm4e2Tm30U0m1ZKOfdqvhXzqNy5cR1ylxu+22m9VBbiqaftZcGbdc+czU9nJhOH5aXmpaeq7katXp671N1ZCLRkvAN7ofqmqZ8t5qzz33jF5r+V+d3ulDJ7Skopav1dABs3wY5RZbbNHmPg0ePDh6rePu8uXLo2WUkG+x/fbbR6819EGvJT40Q+k42p4+pdddDa2bOHFitJ4vZdxb6HH139GXXnoptH0IR4o/N6lwOX+ecuFyqVAoL1euNhVO3Z4w2c4ycOBAO+qoo8zs3feQetz9cdHPq33Hh8Xr3/l7Pj0/r7/+emhrCJZZOhTKh13pe/mQID3W+rn8NvSz6FhuFodHrl69us1/99vv7pC5oUOHhra/H9fQBF3mv8u5e8pUaKPvz1X7ovL3w6lwc1/WWK+1PoRGr9d6ffbncMstt0zuV09TtWR3Z76vHx/0N6IfE0aPHh3al112WWhrWJRZfA7OOOOMaFnq3nnHHXeMXmsI4UMPPdTm33SWXGn63DJtd+X59HL3jTfddFNoz549O7T/5V/+Jfk3vq+nxgQ/Ts2aNWvdO9sO/PIBAAAAAACoAR7iAAAAAAAA1AAPcQAAAAAAAGqg4Zw4Pn/LtGnTQnvgwIHRsj59+oR2LoZaY4d9TOerr74a2hrj6mPxNDeDxuZ/+tOfjtZ79NFHQ9vH+WpMqpaM83bYYYfkNrRsr8ZQ+nh4jasePnx48r3qSOOXzeK4az33Ph40F9PfCN2ejynW7feEmP6eqCOOSy5+VuVia3U//D7lSio3s1zcvsZgjxkzJlqmOXF0fPalo5999tnQ3mijjUJ76623jtbTsVtj83Nee+216PUxxxwT2pdffnm0rDfnwVH77rtv9DqVWyzXj6r8u9m7+5iuO3/+/NA++eSTo/V6U06c1PHzx1+vfT5fUSpnW67Eey6XW+6cprbh30vvU3xOF593ZV3/3pVWrVplP/3pT80sLhVrFuduGjt2bLRM7730Xq5v377Renqd8fkd9HjqPbC/H07lZPG5GavmWtFxVHPxmMX3yv6eWt8vlyNSt+nztdx+++1m9u5cj53F53ZTej70M/icOPpZNV+nWXx/mMul2Mh4WpXfX/394PdDv6v6ffG57ep0b5vKm5K7b+yI4577barnwP+u0fw2//u//xva/jfykUce2e598p9L98vn5ulsfl+q5sPM0XxCxx9/fLRM8wv5kuwqdQ/sr0faJ/R5hVmcj3Hq1Knr2u13vVdumf8u6b2T18gxZSYOAAAAAABADfAQBwAAAAAAoAbaHYPQOjXoyiuvjP5dy8jmSunlpoDpFEi/DQ2TUr7UrU6L/eY3v5n8e50Cnis/fu+994a2hiCYxSXStZy5WbpkpZ8Wq9M3c1PGepKq07z89F2VO9epEtbtKXGn09n0+PvpwLqNXFleSoy/Q89X7hykpoC3p5R7ahv+vXQc8KVUm1luSucBBxwQ2nPnzo2W6VRTPV4+fHTJkiWhrVNf/ftqqetx48ZFy7S8so6TGmJiFk9T3nbbbaNlGtbVm/kp2nr9yJVI1X5VNfTQ9z39zug1cvfdd6+0PbTw07xTIVT++KfCCdoznuprvUfx76XhVL7vadnbXGh7d2ndjzlz5kT/PnPmzOTfaAlvDRX145COj0OGDImW6XnNnUc931oW24eXrly5MrR9SJu+1ra/z616v507d7qPPlyrq++LfDi80nu7XKighg/n7sdzocq6TNs+FCoXBpcKccqFf/llGg6m28vde9dVZ3zXUuEruVLY559/fvRafz+OHz8+tI866qj13j+/Hxru7r8LnaEoinC/kPuN5b9vGq504oknhvayZcuS7+VD9A855JDQ3m677ZJ/l7p++pBCTS/g06scdNBBbW7bpz/R8TU3rmsYrh87fve737X5XmaEUwEAAAAAADQtHuIAAAAAAADUQLvCqfr3728HH3ywmb27kpJmXNaKS/61zwavNJzFh0lptSedvrbhhhtG6+nU/Z/85Cehfeihh0br3XbbbaHtQwh0fydMmBDakyZNitbLTaPU6bk+27/S6XI+nKd1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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Okay so we see that the data set contains the digits and our aim is to train a network that can learn latent representation of this data and help us represent the same data by very few dimensions (32 instead of 784).</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>I have purposely chosen an example of a image datasets as its easy to see the reconstruction of an image as compared to raw data.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Lets begin by creating the model architecture , there are multiple ways you can build up an auto-encoder. You can use any of the following to perform dimensionality reduction:</p>
<ul>
<li>simple autoencoder based on a fully-connected layer: Use just one hidden layer(bottleneck)</li>
<li>sparse autoencoder: Make use of regularisation </li>
<li>deep fully-connected autoencoder : Build a full scale deep NN</li>
<li>deep convolutional autoencoder: Use CNN to extract features from your image and build a compressed representation</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>To fully give you a flavor of how the compression is achieved in auto encoder , I am going to build it using a deep fully-connected autoencoder. The way it works is as follows:</p>
<ul>
<li>The encoder is a <b>Fully Connected Feed Forward NN </b>, consisting of 2 hidden layer each having 128 and 64 neurons respectively.</li>
<li>We use <b>relu</b> as an activation function entirely across our network , except for the output layer which uses <b>sigmoid</b>.</li>
<li>We then create one bottleneck or the code layer with just <b>32 neurons</b>.</li>
<li>Next comes our decoder which is also <b>Fully Connected Feed Forward NN </b>having 2 hidden layer each having 64 and 128 neurons respectively.</li>
<li>In the last we have our output layer with same no of neurons as in input layer(784).</li>
<li>The loss function compares the predicted image with the input image and uses <b>log loss or binary corssentropy</b>.</li>
<li>We use <b>RmsProp</b> as our numerical optimizer to optimize the above loss function.</li>
<li>We plan to train the model for 25 epochs, with a batch size of 512.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">input_img</span> <span class="o">=</span> <span class="n">Input</span><span class="p">(</span><span class="n">shape</span><span class="o">=</span><span class="p">(</span><span class="mi">784</span><span class="p">,))</span> <span class="c1"># specify the size of the single observation</span>
<span class="c1"># Set the encoder </span>
<span class="n">encoded</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="mi">128</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">)(</span><span class="n">input_img</span><span class="p">)</span> <span class="c1"># hidden layer 1</span>
<span class="n">encoded</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="mi">64</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">)(</span><span class="n">encoded</span><span class="p">)</span> <span class="c1"># hidden layer 2</span>
<span class="n">encoded</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">)(</span><span class="n">encoded</span><span class="p">)</span> <span class="c1"># code/ bottleneck layer</span>

<span class="c1"># set the decoder</span>
<span class="n">decoded</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="mi">64</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">)(</span><span class="n">encoded</span><span class="p">)</span> <span class="c1"># hidden layer 4</span>
<span class="n">decoded</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="mi">128</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">)(</span><span class="n">decoded</span><span class="p">)</span> <span class="c1"># hidden layer 5</span>
<span class="n">decoded</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="mi">784</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;sigmoid&#39;</span><span class="p">)(</span><span class="n">decoded</span><span class="p">)</span> <span class="c1"># output layer layer 3</span>


<span class="n">autoencoder</span> <span class="o">=</span> <span class="n">Model</span><span class="p">(</span><span class="n">input_img</span><span class="p">,</span> <span class="n">decoded</span><span class="p">)</span> <span class="c1"># set the input to output flow</span>
<span class="n">autoencoder</span><span class="o">.</span><span class="n">summary</span><span class="p">()</span> <span class="c1"># print out the summary</span>
<span class="n">autoencoder</span><span class="o">.</span><span class="n">compile</span><span class="p">(</span><span class="n">optimizer</span><span class="o">=</span><span class="s1">&#39;rmsprop&#39;</span><span class="p">,</span> <span class="n">loss</span><span class="o">=</span><span class="s1">&#39;binary_crossentropy&#39;</span><span class="p">)</span> <span class="c1"># use the optimizer to start the training</span>

<span class="n">start_time</span> <span class="o">=</span> <span class="n">time</span><span class="o">.</span><span class="n">time</span><span class="p">()</span>
<span class="n">autoencoder</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span><span class="n">x_train</span><span class="p">,</span>
                <span class="n">epochs</span><span class="o">=</span><span class="mi">25</span><span class="p">,</span>
                <span class="n">batch_size</span><span class="o">=</span><span class="mi">512</span><span class="p">,</span>
                <span class="n">shuffle</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
                <span class="n">validation_data</span><span class="o">=</span><span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="n">x_test</span><span class="p">))</span> <span class="c1"># fit to our mnist dataset</span>

<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;</span><span class="se">\n</span><span class="s2"> Time elapsed to train the model </span><span class="si">{}</span><span class="s2"> seconds&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">time</span><span class="o">.</span><span class="n">time</span><span class="p">()</span> <span class="o">-</span> <span class="n">start_time</span><span class="p">))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
input_1 (InputLayer)         (None, 784)               0         
_________________________________________________________________
dense_1 (Dense)              (None, 128)               100480    
_________________________________________________________________
dense_2 (Dense)              (None, 64)                8256      
_________________________________________________________________
dense_3 (Dense)              (None, 32)                2080      
_________________________________________________________________
dense_4 (Dense)              (None, 64)                2112      
_________________________________________________________________
dense_5 (Dense)              (None, 128)               8320      
_________________________________________________________________
dense_6 (Dense)              (None, 784)               101136    
=================================================================
Total params: 222,384
Trainable params: 222,384
Non-trainable params: 0
_________________________________________________________________
Train on 60000 samples, validate on 10000 samples
Epoch 1/25
60000/60000 [==============================] - 3s 58us/step - loss: 0.4098 - val_loss: 0.3631
Epoch 2/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.3506 - val_loss: 0.3406
Epoch 3/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.3342 - val_loss: 0.3270
Epoch 4/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.3252 - val_loss: 0.3243
Epoch 5/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.3198 - val_loss: 0.3179
Epoch 6/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.3156 - val_loss: 0.3134
Epoch 7/25
60000/60000 [==============================] - 1s 19us/step - loss: 0.3121 - val_loss: 0.3124
Epoch 8/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.3090 - val_loss: 0.3067
Epoch 9/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.3063 - val_loss: 0.3059
Epoch 10/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.3042 - val_loss: 0.3033
Epoch 11/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.3025 - val_loss: 0.3016
Epoch 12/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.3008 - val_loss: 0.3028
Epoch 13/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.2994 - val_loss: 0.3036
Epoch 14/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.2983 - val_loss: 0.3018
Epoch 15/25
60000/60000 [==============================] - 1s 19us/step - loss: 0.2971 - val_loss: 0.3010
Epoch 16/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.2961 - val_loss: 0.2967
Epoch 17/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.2952 - val_loss: 0.2983
Epoch 18/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.2944 - val_loss: 0.2953
Epoch 19/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.2936 - val_loss: 0.2959
Epoch 20/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.2929 - val_loss: 0.2925
Epoch 21/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.2921 - val_loss: 0.2933
Epoch 22/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.2916 - val_loss: 0.2927
Epoch 23/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.2910 - val_loss: 0.2952
Epoch 24/25
60000/60000 [==============================] - 1s 18us/step - loss: 0.2905 - val_loss: 0.2959
Epoch 25/25
60000/60000 [==============================] - 1s 17us/step - loss: 0.2899 - val_loss: 0.2909

 Time elapsed to train the model 29.089777946472168 seconds
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Okay so we have our model trained and we have got pretty decent training and testing error , but lets have a look at the reconstructed image , i.e compare the images with original 784 dimensions with the one that was reconstructed with just 32 dimensions.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">decoded_imgs</span> <span class="o">=</span> <span class="n">autoencoder</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_test</span><span class="p">)</span> <span class="c1"># predict the test images by getting the reconstrcution</span>
<span class="n">show_images</span><span class="p">(</span><span class="n">x_test</span><span class="p">,</span><span class="mi">10</span><span class="p">,</span> <span class="n">decoded_imgs</span><span class="p">,</span><span class="s1">&#39;Original vs Reconstructed Images&#39;</span> <span class="p">,</span><span class="kc">True</span><span class="p">)</span> <span class="c1"># plot the original vs reconstructed </span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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puvfRz/60aJMz5caL8fP1Ks5ayMAdBB44gAAAAAAAAAAdAC8xAEAAAAAAAAA6ACQU8GgUfd+T2+5ZMmSbKsUqok3vOENxWdNkaq2uwOrzMfTeNZdz+9J3aMnTpxYlGnqXE9pDX1oimJPSayuxSpvUzlHROn+r9K3ger2s+222w7+ZiGj8qelS5dmW9OIR5QSOZVH+jzaZJNNsu2ptPXvdM5OnTp1sLfd0Xi71MkbNP17RNlXKoGJiHjxxRezrXPMU0Zfd9112X7Xu96VbV2vI8r55ven/aUpzGfMmFHUe+KJJ7LtUqsvfelL2f7whz8cEHHiiSdme8iQIdlesGBBUU9lM03rqZapVMuvsfHGG2d76623Lurtvffe2b799tubfwBERCllevDBB7OtYz4i4oorrsj2UUcdle3tt9++9tq+Jvg6UAcSqlejY/v4448vynQe3HDDDdnW/S2ilICrBFVlyhGlnErTkkeU516VrvqZevLkydl2CbKfuQCgt8ATBwAAAAAAAACgA+AlDgAAAAAAAABAB8BLHAAAAAAAAACADoCYODBovvjFL2bb09BqzAtPkbrVVlsNeD1PkarXUJ35+uuvX9RTvb9qlCPKOCsa98ZjrmicCk8jqSkghw4dmu1e1yFr6k1F43NElHp8jdPg6am1jz2duV5Dx5prz2FwzJs3L9u77757tr399bPq+z3tqfavx1nROB9ar9dSjDfFxNEYTyNGjCjqzZkzJ9sag8p55plnsu1zdPbs2QNeb8yYMUU9XUdvueWWokzXQ4354XFX1ltvvWx76mrdA0499dRsn3feeUW9XkqN/JGPfCTbixcvzrbGqooo1zxdM4cPH17U03nq81njw+k1fLzst99+2e6FmDh1483j9e21117Z9jgperYYPXp0tnfZZZei3jHHHJPtxx9/PNva9xERO+64Y+39jh07dsDvXbRoUVFPYwX6+cbHRrfiKbuvvfbabPtZTvek++67L9vbbbddUe/9739/tnV+aHyciHJtPPbYY4uyq6++OtvTpk3L9gEHHFDUO/LII7M9YcKEouziiy/O9qxZswIAegs8cQAAAAAAAAAAOgBe4gAAAAAAAAAAdADIqWDQaGrSpvSmLp/67ne/m+1zzjkn2+6urW7F6ir+1FNPFfXmz5+fbZfXqNxD00YuXLiwqKf3rymxI0pZgKZe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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The results are pretty amazing with just 0.25 percent of the original dimensions we are able to get quite a close approximation of the original data. This would have given you a sense that how powerful can be these auto encoders when it comes to dimensionality reduction</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="2.-AutoEncoders-for-image-denoising">2. AutoEncoders for image denoising<a class="anchor-link" href="#2.-AutoEncoders-for-image-denoising">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><img src="http://ncia.snu.ac.kr/xe/files/attach/images/317/408/cc3cad516cfb258a9317c1323e080a17.png" alt=""></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>One of the fundamental challenges in the field of image processing and computer vision is image denoising, where the underlying goal is to estimate the original image by suppressing noise from a noise-contaminated version of the image.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>We will train the autoencoder to map noisy digits images to clean digits images. The aim is that we need a model to learn how to remove any noise from the data , such the an effectively trained model can be used for performing task like denosing sound signal, or denoising image data etc...</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>First we start by taking our original image data and add some gaussian noise.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">_</span><span class="p">),</span> <span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="n">_</span><span class="p">)</span> <span class="o">=</span> <span class="n">mnist</span><span class="o">.</span><span class="n">load_data</span><span class="p">()</span> <span class="c1"># download the data set and split it into train and test</span>

<span class="c1"># scale the values of pixel between 0 and 1</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">x_train</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;float32&#39;</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.</span>
<span class="n">x_test</span> <span class="o">=</span> <span class="n">x_test</span><span class="o">.</span><span class="n">astype</span><span class="p">(</span><span class="s1">&#39;float32&#39;</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.</span>

<span class="c1"># reshape the 28*28 image into one long vector of size 784</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">x_train</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="nb">len</span><span class="p">(</span><span class="n">x_train</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">prod</span><span class="p">(</span><span class="n">x_train</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">:])))</span>
<span class="n">x_test</span> <span class="o">=</span> <span class="n">x_test</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="nb">len</span><span class="p">(</span><span class="n">x_test</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">prod</span><span class="p">(</span><span class="n">x_test</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">:])))</span>



<span class="n">x_train_new</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">x_train</span><span class="p">),</span> <span class="mi">28</span><span class="p">,</span> <span class="mi">28</span><span class="p">,</span> <span class="mi">1</span><span class="p">))</span> <span class="c1"># set the channel first format</span>
<span class="n">x_test_new</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">x_test</span><span class="p">),</span> <span class="mi">28</span><span class="p">,</span> <span class="mi">28</span><span class="p">,</span> <span class="mi">1</span><span class="p">))</span>  <span class="c1"># set the channel first format</span>

<span class="n">noise_factor</span> <span class="o">=</span> <span class="mf">0.4</span> <span class="c1"># set the amount of noise </span>
<span class="n">x_train_noisy</span> <span class="o">=</span> <span class="n">x_train_new</span> <span class="o">+</span> <span class="n">noise_factor</span> <span class="o">*</span> <span class="n">np</span><span class="o">.</span><span class="n">random</span><span class="o">.</span><span class="n">normal</span><span class="p">(</span><span class="n">loc</span><span class="o">=</span><span class="mf">0.0</span><span class="p">,</span> <span class="n">scale</span><span class="o">=</span><span class="mf">1.0</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="n">x_train_new</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span> <span class="c1"># create noised dataset</span>
<span class="n">x_test_noisy</span> <span class="o">=</span> <span class="n">x_test_new</span> <span class="o">+</span> <span class="n">noise_factor</span> <span class="o">*</span> <span class="n">np</span><span class="o">.</span><span class="n">random</span><span class="o">.</span><span class="n">normal</span><span class="p">(</span><span class="n">loc</span><span class="o">=</span><span class="mf">0.0</span><span class="p">,</span> <span class="n">scale</span><span class="o">=</span><span class="mf">1.0</span><span class="p">,</span> <span class="n">size</span><span class="o">=</span><span class="n">x_test_new</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span> 

<span class="n">x_train_noisy</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">clip</span><span class="p">(</span><span class="n">x_train_noisy</span><span class="p">,</span> <span class="mf">0.</span><span class="p">,</span> <span class="mf">1.</span><span class="p">)</span> <span class="c1"># scale the pixels between 0 and 1</span>
<span class="n">x_test_noisy</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">clip</span><span class="p">(</span><span class="n">x_test_noisy</span><span class="p">,</span> <span class="mf">0.</span><span class="p">,</span> <span class="mf">1.</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>So here is our original data.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">show_images</span><span class="p">(</span><span class="n">x_train_new</span><span class="p">,</span><span class="mi">10</span><span class="p">,</span><span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([</span><span class="mi">1</span><span class="p">]),</span><span class="s1">&#39;Original Image&#39;</span><span class="p">,</span><span class="kc">False</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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AAAAAEAEMIgDAAAAAAAQAQziAAAAAAAARACDOAAAAAAAABHAIA4AAAAAAEAEHJfpDgAl1bx5c8133HGH19anTx/NL774ouZx48Z553344Ycp6h0AAMAP8vLyNN95552aV69e7Z3XuXNnzZs2bUp9xwAAJfLWW29pds5pvvTSS1P6vMzEAQAAAAAAiAAGcQAAAAAAACIg65ZTHXvssZpPOumkuB4TXopTuXJlzQ0aNND829/+1jvviSee0Hz99dd7bd9++63mUaNGaX744Yfj6hN+rFmzZt7xggULNOfk5HhtQRBovvHGGzV36dLFO69atWrJ7CIypF27dpqnT5/utbVt21bzJ598krY+4ceGDh2qOfxeeMwxP/x/CpdcconXtmTJkpT2C8gWJ554ouYqVap4bVdeeaXmGjVqaB4zZox33qFDh1LUu/KnVq1a3nHv3r01//e//9XcsGFD77yzzz5bM8upMqt+/frecYUKFTS3adNG84QJE7zz7OtbUnPnztXcs2dPr+3w4cOlvn55Zl/HVq1aaR4xYoR33sUXX5y2PiEa/vznP3vH9vfHbuGRaszEAQAAAAAAiAAGcQAAAAAAACKgzC6nOuuss7zj448/XrOdttS6dWvvvKpVq2q+9tprS92PLVu2aB47dqzXdvXVV2vet2+f1/bRRx9pZilAyV1wwQWaX3nlFa/NLpezy6dE/NfDTjkNL5+66KKLNIcrVWXjVFU79df+t5g9e3YmupM0LVq00LxixYoM9gRh/fr103zvvfdqLmqqefh+BvADu0TH3lMiIi1bttTcuHHjuK53+umne8e2ahJKZ+fOnd7x0qVLNYeXdyOzfvGLX2i2f7e6d+/unWeX/p5xxhmaw3/TkvF3zP6OTJw40Wu7++67Ne/du7fUz1Xe2O8QixYt0rxt2zbvvNNOOy1mG8oPuzXKb37zG6/tyJEjmm2lqlRjJg4AAAAAAEAEMIgDAAAAAAAQAQziAAAAAAAARECZ2hPHlpBeuHCh1xZvufBksOtabUnc/fv3e+fZUsZbt2712nbv3q2ZssZFsyXdRUTOO+88zdOmTdMcXrdflPXr12sePXq05hkzZnjnvfvuu5rtay0iMnLkyLifLyps6eZ69eppjtqeOHZNuohI7dq1Nefm5nptzrm09AmFs6/HCSeckMGelF8XXnihZlviuG3btt55dk+IsEGDBmn+z3/+ozm8L519z16+fHninYWI+CWmRfz9L3r16qW5UqVK3nn2/e7zzz/32uxecbakdY8ePbzzbKnkdevWJdJthBw4cMA7plx42WU/83Xq1CmDPSlcnz59vONnn31Ws/0si9Kxe+CEj9kTp/yye6ja8vQiIu+8847ml156KW19YiYOAAAAAABABDCIAwAAAAAAEAFlajnV5s2bNX/55ZdeW2mXU4Wnde/Zs0fzL3/5S6/NlpaeOnVqqZ4XxZs0aZJ3fP3115f6mnZJVpUqVTSHy73b5UVNmjQp9fOWdXY67rJlyzLYk9IJL6379a9/rdku5xBhOUC6tW/f3jseOHBgoeeFX5fOnTtr3r59e/I7Vo5cd9113nFeXp7m6tWraw4vNVy8eLHmGjVqeG2PP/54oc8VvoZ9XM+ePePrcDlmP9s89thjmsOv4YknnhjX9exS4o4dO3ptdgq4vf/s70Rhxyi5qlWresdNmzbNUE9QnAULFmguajnVjh07NNslTeFl3uGS41arVq00h5e1IrNYgh8dbdq00TxkyBDN4e+RX331VcLXDl+jcePGmjdu3Oi12eXm6cRMHAAAAAAAgAhgEAcAAAAAACACGMQBAAAAAACIgDK1J45dszZ48GCvze6X8M9//lPz2LFjY15v1apVmjt06OC12bKP4bKqd911V5w9Rkk1b95c85VXXum1xVqPGt7PZt68eZqfeOIJr82WwLW/L7b0u4jIpZdeWuzzZpPwmu2omjJlSsw2uycE0sOWmX7++ee9tlj7mYX3WKH0buKOO+6HP+Hnn3++5smTJ3vnVa5cWfPSpUs1P/LII955tkxmxYoVvTZbNvOyyy6L2aeVK1cW120YV199teZbb7014ceH1+bbzzrhEuN169ZN+PooHXvviYicddZZcT2uRYsWmsP7h/FemRpPP/205jlz5sQ878iRI5pLWnI6JydH8+rVqzWfccYZMR8T7hPvtakRBIF3fMIJJ2SoJyjOM888o7levXqaGzVq5J1nP9vE64EHHvCOq1Wrptnuwyki8tFHHyV8/WTIjm90AAAAAAAAWY5BHAAAAAAAgAgoU8uprPC0wYULF2ret2+f5nC5xltuuUWzXWJjl0+FrVmzxju+7bbbEuss4tKsWTPNtpSjnVYq4k9lfOONNzSHy73ZsoxDhw712uxym507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fPPNcfW9rGAmDgAAAAAAQAQwiAMAAAAAABABWb2cylq9erV33KNHD81XXXWV12bLkd9+++2a69Wr553XoUOHZHYxksLLWmx53B07dnhtM2fOTEufwipWrKh52LBhMc9buHChd2zL1UXVgAEDvONNmzZpbtWqVYmuuXnzZs1z5szRvHbtWu+8999/v0TXt2677TbNdimJXb6D5Ln33nu943ingxdVfhyJ2bNnj3dsy7y/9tprXpstm7lx40bNc+fO9c574YUXNH/11VeaZ8yY4Z1npxmH21By9u+iXe4kIjJr1qxCH/Pwww97x/bv07vvvqvZ/g6EzwuXULbs++nIkSO9tljv8SIihw4dinlNJCbecvBt2rTxjsePH5+yPpUn4e8Fl1xyiWZb8nj+/Pneed9++23Cz3XLLbd4xwMHDkz4GkidRYsWaQ5vE4HkuO6667xj+137yJEjXpv9HHTDDTdo3r17t3fek08+qblt27aa7dIqEX95ZHjpefXq1TV//vnnmu37gYj/GausYCYOAAAAAABABDCIAwAAAAAAEAEM4gAAAAAAAERAudkTJ8yut5s6darXZkud2TKc4XXJdr3c4sWLk9vBLBBeO79169a0PbfdB2fo0KGaBw8e7J1ny1bbtZUiIvv3709R7zLnsccey3QXEtKuXbtC/z3e0tcoXrNmzTRfdtllcT0mvOfKJ598ktQ+4QfLly/XHC4xXhL275hdQy7i78vBvlMlFy4jbve3Cf8Nsmw54XHjxnlt9jOL/T14/fXXvfPOOecczeHy4KNHj9Zs98sJl2OdPn265n/84x9em/0bEt6fwFq1alXMNuSz91t4nwYrXAK+UaNGmj/++OPkd6ycsnsGDh8+PKnXDu/HyJ44ZYvdByzMvp/n5uZ6bfZ3BkWze8yK+P/NH330Ua/N7pdTFHsfTZo0SXPLli3j7pfdL8fujVQW98AJYyYOAAAAAABABDCIAwAAAAAAEAHlZjlVkyZNvONf/epXmlu0aOG12SVUVnja6tKlS5PUu+z06quvpu257JIQEX/Kui1rF14Gcu2116a2Y0iJ2bNnZ7oLWePNN9/UfPLJJ8c8z5aM79evXyq7hBSqVKmS5nBZY7ukgxLjiTn22GM1P/LII17boEGDNB84cMBru++++zTb/+bhUvO2ZKotMX3uued6561fv15z//79vTY7VTwnJ0dzq1atvPN69eqluUuXLl7bggULpDC2NKuISO3atQs9Dz+YOHGi5vBSg6Lcdtttmu++++6k9gmp0bFjx0x3AUU4evRozDa73MZu1YDEhL9/zZo1S3P470e8bHlwu0Q47Prrr9e8evXqmOfZLTaigJk4AAAAAAAAEcAgDgAAAAAAQARk3XKqBg0aaL7jjjs0h3f3P+200+K63nfffac5XF0pPBW9PLLTDMPH3bp189ruuuuupD737373O81//OMfvbaTTjpJs6200adPn6T2AYi6atWqaS7qPW3ChAmas7FyW3kxf/78THchK9klLnb5lIjIwYMHNYeXzdjljBdddJHmm266yTvviiuu0GyXxP3pT3/yzrNVPYqaor53717Nf//73702e2ynoYuI3HDDDYVez/49RnzWrVuX6S5kvXClOFuBceHChV7bN998k9TntvdwXl5eUq+N5LJLfcL35dlnn605vHxxwIABqe1YFknGPWC/24mIdO/eXbNdIhyuLPXSSy+V+rnLImbiAAAAAAAARACDOAAAAAAAABHAIA4AAAAAAEAERHJPHLufTXi9tt0Hp1atWiW6/sqVKzUPHz5cczpLZkeFLUkbPg7vOzR27FjNzz33nOYvv/zSO8/uC3DjjTdqbtq0qXfemWeeqXnz5s1em933we7lgeiy+y3Vr1/fa7Plr1E8u2/GMcfEN5b/3nvvpao7SCNK3abGgw8+GLPNlh8fPHiw1zZs2DDNdevWjeu57GNGjhzptdl9/JLhr3/9a5HHKLlx48ZpHjhwoNdWp06dmI+z+wvaa4T3gSivWrdurXnIkCFeW4cOHTTXrl3baytJmeNTTjlFc6dOnby2MWPGaK5cuXLMa9i9eL799tuE+4DksvuUiYjUrFlT8+9///t0dwdGeA+i/v37a96xY4fmSy+9NG19yiRm4gAAAAAAAEQAgzgAAAAAAAARUGaXU5166qnecaNGjTSPHz9esy39lojly5drfvzxx702W2qOMuIlZ6eQi/jT4K699lrNttSpiEi9evXiur5d3rFo0SKvraip7Ygmu1Qv3iVAyNesWTPvuH379prte9zhw4e985566inN27dvT1HvkE4///nPM92FrLRt2zbNNWrU8NoqVqyoObws2Hr99dc1L1261GubM2eO5s8++0xzspdPITPWrFnjHRd1n/K5tGj2O0Ljxo1jnveHP/zBO963b1/Cz2WXZ5133nleW3i7AWvx4sWan376ac3hz7LIPPs6hj8jIfVyc3M133rrrV6bfW2eeeYZzVu2bEl9x8oAvgkBAAAAAABEAIM4AAAAAAAAEcAgDgAAAAAAQARkdE8cW5pPRGTSpEmaw3s4lGQdv90z5cknn/TabAlqW94PiVm2bJl3vGLFCs0tWrSI+Thbfjy8/5Fly4/PmDHDa7NlNlG+tGzZ0jt+4YUXMtORiKhatap3bO8/64svvvCOBw0alLI+ITPefvttzeG9pdhro+TatGmjuVu3bl6b3SvDlkEVEXnuuec07969WzN7L5Qvdj8HEZGrrroqQz0pP2x54lSw9/q8efO8Nvv5lbLiZVtOTo7mrl27em2zZ89Od3fKnQULFmi2++OIiEybNk3zQw89lLY+lRXMxAEAAAAAAIgABnEAAAAAAAAiIC3LqS688ELNgwcP1nzBBRd459WsWTPhax88eNA7Hjt2rOYRI0ZoPnDgQMLXRvHCZdyuueYazbfffrvXNnTo0LiumZeXp9mWXtywYUNJuogs4ZzLdBeAyFu9erXm9evXe2122XKdOnW8tp07d6a2YxFnyxNPnTrVawsfA2Eff/yxd7x27VrNDRs2THd3Iq1fv36aBw4c6LX17du31NffuHGjZvsdxC5VFfGXyNn3XZRtPXr08I4PHTqk2d6XSI/nn39e8yOPPOK1zZ07N93dKVOYiQMAAAAAABABDOIAAAAAAABEgAuCIP6TnYv/ZGPUqFGa7XKqooSnlr722muajx49qjlcdWrPnj0l6WKZFwRBUtaSlPQ1RFJ8EATB+cm4UHl5He20aFvFZfLkyd554aV7qRTFezFcjWrmzJmaW7durfnTTz/1zqtbt25qO5Y53Ivi318iIlOmTNG8ZMkSr80uSwj/fc6UKN6L+BHuxSxQVu/FihUresf2Pe/RRx/12k4++WTNc+bM0Wyr44j4Szi2bduWjG6WFdyL8uNKuHY5Y5cuXby2TZs2paVPiSir9yISEte9yEwcAAAAAACACGAQBwAAAAAAIAIYxAEAAAAAAIiAtOyJg9JjjWNWYL1xFuBezArciyKSk5PjHb/00kua27dv77XNmjVL80033aT5wIEDKepd8bgXswL3YhbgXswK3ItZgHsxK7AnDgAAAAAAQLZgEAcAAAAAACACjst0BwAAQPrt3bvXO+7Ro4fm4cOHe239+/fXPGzYMM1lpdw4AABAecFMHAAAAAAAgAhgEAcAAAAAACACGMQBAAAAAACIAEqMRwQl47IC5RuzAPdiVuBezALci1mBezELcC9mBe7FLMC9mBUoMQ4AAAAAAJAtGMQBAAAAAACIgERLjO8SkU2p6AiKlJvEa/EaZg6vY/TxGmYHXsfo4zXMDryO0cdrmB14HaOP1zA7xPU6JrQnDgAAAAAAADKD5VQAAAAAAAARwCAOAAAAAABABDCIAwAAAAAAEAEM4gAAAAAAAEQAgzgAAAA+wBGDAAAAMUlEQVQAAAARwCAOAAAAAABABDCIAwAAAAAAEAEM4gAAAAAAAEQAgzgAAAAAAAAR8P9bppgA6b/73gAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>And here is our noisy data</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">show_images</span><span class="p">(</span><span class="n">x_train_noisy</span><span class="p">,</span><span class="mi">10</span><span class="p">,</span><span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([</span><span class="mi">1</span><span class="p">]),</span><span class="s2">&quot;Noisy Images&quot;</span><span class="p">,</span> <span class="kc">False</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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33336PNll10W4s022yzEOujygvrpp5+O2vQmKdhnn32iz/xA/Oijj0ZtPGgdf/zxIdaH1McffzzEd999d9T21ltv1XkcjcWRRx4Z4hNPPLGivzn88MOjzyeffHKI11xzzaiNF3+HHnpoiP/0pz9F2/FCKTXYMbpI5E7K12L06NHRdrwoTy2omFtvvTX6zB39l7/8ZdTGg/CsWbM+RiNw2mmnRZ8POOCAED/yyCNRG5+L7bffPsQ333xztN0555wT4tNPPz1q40GOJ5VPP/002o4n6l//+tchHjNmTLQd3+dPPPFE1KYTVSXccsst0eett946xD169Ajxq6++Gm3HDysfffRR1FYsyvnBZH7p0KEDDjroIADAc889F7V17949xDpx3HfffXXuT8en888/P8T6oo/HvLLxrqHwohOIF2nHHntsiPXFIU+62k8//PDDEPM9rce+8sorh1gfiGWyb5S+qLz44osh/s1vfhO1Pf/88yFOjVH80krnBO4fPObpwonn2sGDB4f4tddei7b77W9/W+d2QDwup7bj8ad///4og8/HnXfeGbXxvazXcdCgQaX7nB+KsVof3Pll0yWXXBK1PfXUUyHmvxs4cGDp9xx99NHRZ54/Tj311NK/4zmOF9D/+c9/Sv9myJAh0Wd+qcMvE954443Sfeyyyy7R5y222CLEhxxySIh32223aLvLL7+8zu+q4/sapS/ygysQL6Z5QQ/ELy74777++utoO14v8PwJANdee22IU33gxhtvDPEmm2xSdvjR9daHDr4neX3Ja7h5wf+Iw+u4fv36VbyPE044AUA818wvLVq0CC9N9DrxC5hKXzb98Y9/jD4/9NBDIea1AQA888wzIeaHcz0nvH5l9J7gsVFfVjD8skofPnmMP/DAA6O2M844o3SfDK+/9AXFHXfcwR8bpS8W90nBBRdcEGJ9Nttoo41CzC8v+drodjp+/eUvfwkxn/ezzz679Bh79eoVYp5zAeCss84KcWp9w+y4447RZ/4HSZ13GX7Jz/8gAgAvvPBCiPfaa6+obcMNNwRQv/47P5x00kkhvvrqq6M2Xr/ee++9Fe1Pz4n2gwLtY7reL+D1ChD/g9q//vWv0uPgvs3/6AHE/Tn1Mo9fMFb6EqsOKuqLWX3eDi+xxBJ5sXjjBzQAePbZZ0OsNzkPULzQaegbKn7olwEogidc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a9euURvLFFkmVh+OP/54ADWyyXHjxlV9XnziiSeitt/+9rcV7WObbbYJsdoasxRY7XBZ8spjKKeGA3EaNlsIc/8FgD322CPEO++8c9TG9sq89mN7YiCWt5177rloCPy7UpJQVFFO1bVr17ywsee1JhDLZfWashybZWAKz11sSQwA1157bYhPOeWUELPFLhDLWVgOqbIovsZ6fbgUwY033hjiww8/vPTYq4GugTt37gygZv6dPn16Vfpis2bN8uJ+0TGI+xj/biCWuqnlcRm8LgFiGQjLDVN06NAhxLoe7tevX4hVSqJjb4Hem2w5XQ30mY+lHz179qxaX+zYsWNerN9VtjZr1qzSv9ttt91CzHO2roNU2lcJ2o/4GrOcJyVN53sQqH1dCzbcMD6Nr732Wr2PUa3iU/JIplrPi23atMlXW201ALUlzzy+6tqfWX755UPMFun14eyzzw5x6nkk9T6Dn4vUzpz/juctvdbcF3fdddeobciQIXV+r67nuHwES7AA4J577gnxK6+8YjmVMcYYY4wxxhhjzMKCX+IYY4wxxhhjjDHGNAHqJadiCYemhrFblVbSVzeago4dO0af2f0kJbVKSSKYq6++OsSawpyCpRlc0VoZPnx4iDnlHYjTXdklJVVRXKtpjx49OsTVSo9r3bp1XqS3abV3dnRSt5wydtxxx+gzp2srnM7M6f5a9fzxxx+v6LsZrmIPALfddlud26244orRZ07rVoemlASF4ft9iy22SG1atVTVFi1a5EVFdXUbYDQ1V6UCBXztgfj6r7POOlGbOnwVaJ/VdPYCrr4PxOPDv//976iNZTrsRqZjCqcxa1/kFPOTTz45xJr+qOmvTJE6+eSTT2LixIlV6YurrLJKftlllwGo7VrHqFNTIScBYmc3HctZiqgV8dlNilM6P/jgg2g7Tp9nGY7eE0svvXSI1RGN3UF4LFQXoEpd3goJGgCMHTs2auPjKrtP51C1vtipU6e8kJqp5HO55ZYLscow+Xcw6667bvSZJYUiQ4lIpVrzPt98880Qp+Z/vY48TnN/43RpIL7GOrazuwofkx4HX7uUu0O15sVu3brlhYSU3WaAWGKm4w47zvB1UtdGRqWTfC75PKSuDZ+D//u//4va1J2PqdQdtJAkAcALL7wQtfHvZHmcOuCxRFddddid5vnnn69aX1x00UXzwqVI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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>In this use-case we will make use of the convolution auto encoders that will help us understand both the working of CNN as autoencoder and the way we can design it in a way to perform denosing.</p>
<p>The input to the network will be a noised version of the image and we instruct the network to learn to remove noise by minimising the error between the predicted and denoised image , thus the trained model can be use to effectively remove noise.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The architecture that i have use to construct this is as follows:</p>
<ul>
<li>We design the encoder part using <b>2 CNN + MaxPooling layer</b> , in each of the 2 layer we use <b>32 filters of size 3*3 size</b>.</li>
<li>We use <b>relu</b> as an activation function entirely across our network , except for the output layer which uses <b>sigmoid</b>.</li>
<li>Since we are using a CNN we are going to keep the padding scheme to be 'same' which means we are going to add zero padding across the activations so that the size of the activations does not get shrink as we pass it through the CNN.</li>
<li>The <b>MaxPooling will act as a regularisation scheme</b> helping to reduce the height and width of the activations.</li>
<li>The encoder will shrink the activation to a shape of <b>7,7,32</b></li>
<li>We then design the decoder by using <b>2 CNN+ UpSampling layer</b> in each of the 2 layer we use <b>32 filters of size 3*3 size</b>.</li>
<li>While decoding we want the image height and width to increase and the channels to decrease and hence we use the <b>UpSampling</b> techniques to achieve this.</li>
<li>The loss function compared the predicted image with the denoised image and uses <b>log loss or binary crossentropy</b>.</li>
<li>We use <b>RmsProp</b> as our numerical optimizer to optimize the above loss function.</li>
<li>We plan to train the model for 25 epochs, with a batch size of 128.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The UpSampling operation repeats the rows and columns of the data by size[0] and size[1] respectively.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">input_img</span> <span class="o">=</span> <span class="n">Input</span><span class="p">(</span><span class="n">shape</span><span class="o">=</span><span class="p">(</span><span class="mi">28</span><span class="p">,</span> <span class="mi">28</span><span class="p">,</span> <span class="mi">1</span><span class="p">))</span>  <span class="c1"># adapt this if using `channels_first` image data format</span>

<span class="n">x</span> <span class="o">=</span> <span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">,</span> <span class="n">padding</span><span class="o">=</span><span class="s1">&#39;same&#39;</span><span class="p">)(</span><span class="n">input_img</span><span class="p">)</span> <span class="c1"># perform convolution operation with 32 filters, hidden layer 1</span>
<span class="n">x</span> <span class="o">=</span> <span class="n">MaxPooling2D</span><span class="p">((</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">),</span> <span class="n">padding</span><span class="o">=</span><span class="s1">&#39;same&#39;</span><span class="p">)(</span><span class="n">x</span><span class="p">)</span> <span class="c1"># use max pololing, hidden layer 1</span>
<span class="n">x</span> <span class="o">=</span> <span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">,</span> <span class="n">padding</span><span class="o">=</span><span class="s1">&#39;same&#39;</span><span class="p">)(</span><span class="n">x</span><span class="p">)</span><span class="c1"># hidden layer 2</span>
<span class="n">encoded</span> <span class="o">=</span> <span class="n">MaxPooling2D</span><span class="p">((</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">),</span> <span class="n">padding</span><span class="o">=</span><span class="s1">&#39;same&#39;</span><span class="p">)(</span><span class="n">x</span><span class="p">)</span> <span class="c1"># hidden layer 2</span>

<span class="c1"># at this point the representation is (7, 7, 32)</span>

<span class="n">x</span> <span class="o">=</span> <span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">,</span> <span class="n">padding</span><span class="o">=</span><span class="s1">&#39;same&#39;</span><span class="p">)(</span><span class="n">encoded</span><span class="p">)</span> <span class="c1"># hidden layer 3</span>
<span class="n">x</span> <span class="o">=</span> <span class="n">UpSampling2D</span><span class="p">((</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">))(</span><span class="n">x</span><span class="p">)</span> <span class="c1"># hidden layer 3</span>
<span class="n">x</span> <span class="o">=</span> <span class="n">Conv2D</span><span class="p">(</span><span class="mi">32</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">,</span> <span class="n">padding</span><span class="o">=</span><span class="s1">&#39;same&#39;</span><span class="p">)(</span><span class="n">x</span><span class="p">)</span> <span class="c1"># hidden layer 4</span>
<span class="n">x</span> <span class="o">=</span> <span class="n">UpSampling2D</span><span class="p">((</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">))(</span><span class="n">x</span><span class="p">)</span> <span class="c1"># hidden layer 4</span>
<span class="n">decoded</span> <span class="o">=</span> <span class="n">Conv2D</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">),</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;sigmoid&#39;</span><span class="p">,</span> <span class="n">padding</span><span class="o">=</span><span class="s1">&#39;same&#39;</span><span class="p">)(</span><span class="n">x</span><span class="p">)</span> <span class="c1">#hidden layer 5</span>

<span class="n">denoiser</span> <span class="o">=</span> <span class="n">Model</span><span class="p">(</span><span class="n">input_img</span><span class="p">,</span> <span class="n">decoded</span><span class="p">)</span> <span class="c1"># set up the data flow</span>
<span class="n">denoiser</span><span class="o">.</span><span class="n">summary</span><span class="p">()</span> <span class="c1"># print the model summary</span>
<span class="n">denoiser</span><span class="o">.</span><span class="n">compile</span><span class="p">(</span><span class="n">optimizer</span><span class="o">=</span><span class="s1">&#39;rmsprop&#39;</span><span class="p">,</span> <span class="n">loss</span><span class="o">=</span><span class="s1">&#39;binary_crossentropy&#39;</span><span class="p">)</span> <span class="c1"># run through the optimizer</span>

<span class="n">start_time</span> <span class="o">=</span> <span class="n">time</span><span class="o">.</span><span class="n">time</span><span class="p">()</span>

<span class="n">denoiser</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">x_train_noisy</span><span class="p">,</span> <span class="n">x_train_new</span><span class="p">,</span>
                <span class="n">epochs</span><span class="o">=</span><span class="mi">25</span><span class="p">,</span>
                <span class="n">batch_size</span><span class="o">=</span><span class="mi">128</span><span class="p">,</span>
                <span class="n">shuffle</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
                <span class="n">validation_data</span><span class="o">=</span><span class="p">(</span><span class="n">x_test_noisy</span><span class="p">,</span> <span class="n">x_test_new</span><span class="p">))</span> <span class="c1"># pass the data </span>

<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;</span><span class="se">\n</span><span class="s2"> Time elapsed to train the model </span><span class="si">{}</span><span class="s2"> seconds&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">time</span><span class="o">.</span><span class="n">time</span><span class="p">()</span> <span class="o">-</span> <span class="n">start_time</span><span class="p">))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
input_3 (InputLayer)         (None, 28, 28, 1)         0         
_________________________________________________________________
conv2d_6 (Conv2D)            (None, 28, 28, 32)        320       
_________________________________________________________________
max_pooling2d_3 (MaxPooling2 (None, 14, 14, 32)        0         
_________________________________________________________________
conv2d_7 (Conv2D)            (None, 14, 14, 32)        9248      
_________________________________________________________________
max_pooling2d_4 (MaxPooling2 (None, 7, 7, 32)          0         
_________________________________________________________________
conv2d_8 (Conv2D)            (None, 7, 7, 32)          9248      
_________________________________________________________________
up_sampling2d_3 (UpSampling2 (None, 14, 14, 32)        0         
_________________________________________________________________
conv2d_9 (Conv2D)            (None, 14, 14, 32)        9248      
_________________________________________________________________
up_sampling2d_4 (UpSampling2 (None, 28, 28, 32)        0         
_________________________________________________________________
conv2d_10 (Conv2D)           (None, 28, 28, 1)         289       
=================================================================
Total params: 28,353
Trainable params: 28,353
Non-trainable params: 0
_________________________________________________________________
Train on 60000 samples, validate on 10000 samples
Epoch 1/25
60000/60000 [==============================] - 7s 115us/step - loss: 0.1529 - val_loss: 0.1064
Epoch 2/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.1022 - val_loss: 0.0992
Epoch 3/25
60000/60000 [==============================] - 6s 104us/step - loss: 0.0962 - val_loss: 0.0959
Epoch 4/25
60000/60000 [==============================] - 6s 106us/step - loss: 0.0934 - val_loss: 0.0909
Epoch 5/25
60000/60000 [==============================] - 7s 114us/step - loss: 0.0916 - val_loss: 0.0896
Epoch 6/25
60000/60000 [==============================] - 6s 107us/step - loss: 0.0905 - val_loss: 0.0881
Epoch 7/25
60000/60000 [==============================] - 6s 106us/step - loss: 0.0896 - val_loss: 0.0877
Epoch 8/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.0889 - val_loss: 0.0885
Epoch 9/25
60000/60000 [==============================] - 6s 106us/step - loss: 0.0884 - val_loss: 0.0884
Epoch 10/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.0879 - val_loss: 0.0869
Epoch 11/25
60000/60000 [==============================] - 6s 104us/step - loss: 0.0875 - val_loss: 0.0862
Epoch 12/25
60000/60000 [==============================] - 6s 104us/step - loss: 0.0872 - val_loss: 0.0867
Epoch 13/25
60000/60000 [==============================] - 6s 106us/step - loss: 0.0869 - val_loss: 0.0868
Epoch 14/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.0867 - val_loss: 0.0864
Epoch 15/25
60000/60000 [==============================] - 6s 103us/step - loss: 0.0865 - val_loss: 0.0853
Epoch 16/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.0863 - val_loss: 0.0863
Epoch 17/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.0861 - val_loss: 0.0851
Epoch 18/25
60000/60000 [==============================] - 6s 106us/step - loss: 0.0860 - val_loss: 0.0858
Epoch 19/25
60000/60000 [==============================] - 6s 107us/step - loss: 0.0859 - val_loss: 0.0849
Epoch 20/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.0857 - val_loss: 0.0849
Epoch 21/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.0857 - val_loss: 0.0852
Epoch 22/25
60000/60000 [==============================] - 6s 105us/step - loss: 0.0855 - val_loss: 0.0847
Epoch 23/25
60000/60000 [==============================] - 6s 104us/step - loss: 0.0854 - val_loss: 0.0864
Epoch 24/25
60000/60000 [==============================] - 6s 107us/step - loss: 0.0853 - val_loss: 0.0850
Epoch 25/25
60000/60000 [==============================] - 7s 111us/step - loss: 0.0853 - val_loss: 0.0849

 Time elapsed to train the model 159.6751983165741 seconds
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>So our model is trained lets have a look at how the model behaves when we pass in the noisy images.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Below is the noised image</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[13]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">show_images</span><span class="p">(</span><span class="n">x_test_noisy</span><span class="p">,</span><span class="mi">10</span><span class="p">,</span><span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([</span><span class="mi">1</span><span class="p">]),</span><span class="s2">&quot;Nosiy Images passed as Input to Model&quot;</span> <span class="p">,</span><span class="kc">False</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Below is the denoised image</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">denoised_imgs</span> <span class="o">=</span> <span class="n">denoiser</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_test_noisy</span><span class="p">)</span> <span class="c1"># get the predicted image</span>
<span class="n">show_images</span><span class="p">(</span><span class="n">denoised_imgs</span><span class="p">,</span><span class="mi">10</span><span class="p">,</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([</span><span class="mi">1</span><span class="p">]),</span> <span class="s1">&#39;Denosied Images generated from model&#39;</span><span class="p">,</span><span class="kc">False</span><span class="p">)</span> <span class="c1"># plot the predicted images</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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mk9RWez32dZ8e/bZZ6N+djr4rbfeOmqz1z7NmjULcXrdYn8LbVtaO8fW42zSpEnUZl9n66va6aglafr06UJx6XWordto62im9w+2llHbtm1DbI9fKZ5iPL32nDRpUojt/Wce7k0YiQMAAAAAAJADPMQBAAAAAADIgVymU9WUHTLVvXv3qM0O8U+nfjv//PNDbId0YcXsUMN0ije7P+x2HT58eNTPTjlthxGXmuaxlNoeUm4/V2Mevp5+djuM1e67zz77rM7WqTFJh4imx4tl942N031j39P269mzZ9Tv2GOPDfEOO+wQtbVo0SLENg0k/b7Mnj07xI888kjU1piPqwULFoR4r732itp69OgR4m222SbErVu3jvrZ1Bx77k2HqE+YMCHEu+66a9R2xRVXhNimz6WpbuWYehnfnVb6Rz/6UYjtcZmmI3PNkh82neP000+P2mxKiL0mkuIUS6YVLx+bZnzDDTeE2G5vKT7+7P1Dqd+p9D5jxIgRIf7DH/4QYvs7K0lDhw4N8T777BO1VeK51m5DO9343/72t6if3X5pinCHDh1CfN5554XYThsvxdcmdv/Y9BpJev7550N8wAEHRG2dO3cOcfPmzUPcr1+/qN/VV19d7bKwYvY7kR5j3bp1C/F1110X4vT+014Pp6mNNlU5DylUFiNxAAAAAAAAcoCHOAAAAAAAADlQcelUdpijrfb/97//Pepn036efvrpqM0OnWOo6sqx6RKlhnraoW2HHnpo1GbTB2yKRToE0Q7jT5dVbEicXT8prmzerl27qG277bYLsU1bSIe7vvLKKyFOh3za4bmVLk3f2Wmnnaptmzp1atTPVv7HqktnXrCpUWlqRtOmTUM8bNiwEI8ePTrqt8UWW4S4d+/eId5yyy2jfnYYcXqMFUs3TI8NOytAOty1MbPHx7x586K2e++9N8T33Xdfjd6v1NBku69sypQUH8P2dQsXLiz6/lh16e+MndnN/t69+uqrUb8vvvgixOyL+pGmtlr2PG3Pr4cddljUz+67UaNGRW2Naba+hqA20l+WLFkSYpuuNWjQoKifLQVhZ9iRvnstVcnSc5k9B6bX/3a72Hs/e00qSeutt16I7fXIE088EfWbOXNmiHfbbbeozd4j2uPepuhI0k033RRiZpRbOfac2aVLl6jN3nPZ1Kr0etj+Lqbn2jRdNU8YiQMA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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The results are pretty impressive ,we can clearly see that the trained model is in the position of removing the noise in the dataset.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="3.-Varational-AutoEncoder-for-generating-new-MNIST-images">3. Varational AutoEncoder for generating new MNIST images<a class="anchor-link" href="#3.-Varational-AutoEncoder-for-generating-new-MNIST-images">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><img src="https://cdn-images-1.medium.com/max/2600/1*22cSCfmktNIwH5m__u2ffA.png" alt=""></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Variational Autoencoders (VAEs) are powerful generative models, now having applications as diverse as from generating fake human faces, to producing purely synthetic music.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Variational Autoencoders (VAEs) have one fundamentally unique property that separates them from vanilla autoencoders, and it is this property that makes them so useful for generative modeling: their latent spaces are, by design, continuous, allowing easy random sampling and interpolation.</p>
<p>It achieves this by doing something that seems rather surprising at first: making its encoder not output an encoding vector of size n, rather, outputting two vectors of size n: a vector of means, μ, and another vector of standard deviations, σ.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The architecture that i have use to construct this is as follows:</p>
<ul>
<li><b>Encoder :-</b> 1 input layer + 1 Feed Forward layer with 256 neurons</li>
<li><b>Activation Function :-</b> Relu  + Sigmoid </li>
<li><b>Code  Layer Size :-</b> 2 layers with 2 neurons one for each mean and std </li>
<li><b>Decoder :-</b>  1 Feed Forward layer with 256 neurons + 1 output layer</li>
<li><b>Loss Function :-</b> Binary crossentropy</li>
<li><b>Optimizer :-</b> RmsProp </li>
<li><b>Epochs :-</b> 100</li>
<li><b>Batch Size :-</b> 512</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[15]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">original_dim</span> <span class="o">=</span> <span class="mi">784</span>
<span class="n">intermediate_dim</span> <span class="o">=</span> <span class="mi">256</span>
<span class="n">latent_dim</span> <span class="o">=</span> <span class="mi">2</span>
<span class="n">batch_size</span> <span class="o">=</span> <span class="mi">512</span>
<span class="n">epochs</span> <span class="o">=</span> <span class="mi">100</span>
<span class="n">epsilon_std</span> <span class="o">=</span> <span class="mf">1.0</span>


<span class="k">def</span> <span class="nf">nll</span><span class="p">(</span><span class="n">y_true</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">):</span>
    <span class="k">return</span> <span class="n">K</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">K</span><span class="o">.</span><span class="n">binary_crossentropy</span><span class="p">(</span><span class="n">y_true</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">),</span> <span class="n">axis</span><span class="o">=-</span><span class="mi">1</span><span class="p">)</span> <span class="c1"># use negative log likelihood</span>


<span class="k">class</span> <span class="nc">KLDivergenceLayer</span><span class="p">(</span><span class="n">Layer</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="o">*</span><span class="n">args</span><span class="p">,</span> <span class="o">**</span><span class="n">kwargs</span><span class="p">):</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">is_placeholder</span> <span class="o">=</span> <span class="kc">True</span>
        <span class="nb">super</span><span class="p">(</span><span class="n">KLDivergenceLayer</span><span class="p">,</span> <span class="bp">self</span><span class="p">)</span><span class="o">.</span><span class="fm">__init__</span><span class="p">(</span><span class="o">*</span><span class="n">args</span><span class="p">,</span> <span class="o">**</span><span class="n">kwargs</span><span class="p">)</span>

    <span class="k">def</span> <span class="nf">call</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">inputs</span><span class="p">):</span>
        <span class="n">mu</span><span class="p">,</span> <span class="n">log_var</span> <span class="o">=</span> <span class="n">inputs</span>
        <span class="n">kl_batch</span> <span class="o">=</span> <span class="o">-</span> <span class="o">.</span><span class="mi">5</span> <span class="o">*</span> <span class="n">K</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="mi">1</span> <span class="o">+</span> <span class="n">log_var</span> <span class="o">-</span>
                                <span class="n">K</span><span class="o">.</span><span class="n">square</span><span class="p">(</span><span class="n">mu</span><span class="p">)</span> <span class="o">-</span>
                                <span class="n">K</span><span class="o">.</span><span class="n">exp</span><span class="p">(</span><span class="n">log_var</span><span class="p">),</span> <span class="n">axis</span><span class="o">=-</span><span class="mi">1</span><span class="p">)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">add_loss</span><span class="p">(</span><span class="n">K</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">kl_batch</span><span class="p">),</span> <span class="n">inputs</span><span class="o">=</span><span class="n">inputs</span><span class="p">)</span> <span class="c1"># add kl divergence to the loss</span>
        <span class="k">return</span> <span class="n">inputs</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">decoder</span> <span class="o">=</span> <span class="n">Sequential</span><span class="p">([</span>
    <span class="n">Dense</span><span class="p">(</span><span class="n">intermediate_dim</span><span class="p">,</span> <span class="n">input_dim</span><span class="o">=</span><span class="n">latent_dim</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">),</span>
    <span class="n">Dense</span><span class="p">(</span><span class="n">original_dim</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;sigmoid&#39;</span><span class="p">)</span>
<span class="p">])</span> <span class="c1"># set the decoder network to have 2 dense layer </span>

<span class="n">x</span> <span class="o">=</span> <span class="n">Input</span><span class="p">(</span><span class="n">shape</span><span class="o">=</span><span class="p">(</span><span class="n">original_dim</span><span class="p">,))</span> <span class="c1"># set the input layer</span>
<span class="n">h</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="n">intermediate_dim</span><span class="p">,</span> <span class="n">activation</span><span class="o">=</span><span class="s1">&#39;relu&#39;</span><span class="p">)(</span><span class="n">x</span><span class="p">)</span> <span class="c1"># set the 1st hidden layer</span>

<span class="n">z_mu</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="n">latent_dim</span><span class="p">)(</span><span class="n">h</span><span class="p">)</span> <span class="c1"># create a code layer to learn the mean of data </span>
<span class="n">z_log_var</span> <span class="o">=</span> <span class="n">Dense</span><span class="p">(</span><span class="n">latent_dim</span><span class="p">)(</span><span class="n">h</span><span class="p">)</span> <span class="c1"># create a code layer to learn the std of data</span>

<span class="n">z_mu</span><span class="p">,</span> <span class="n">z_log_var</span> <span class="o">=</span> <span class="n">KLDivergenceLayer</span><span class="p">()([</span><span class="n">z_mu</span><span class="p">,</span> <span class="n">z_log_var</span><span class="p">])</span> 
<span class="n">z_sigma</span> <span class="o">=</span> <span class="n">Lambda</span><span class="p">(</span><span class="k">lambda</span> <span class="n">t</span><span class="p">:</span> <span class="n">K</span><span class="o">.</span><span class="n">exp</span><span class="p">(</span><span class="o">.</span><span class="mi">5</span><span class="o">*</span><span class="n">t</span><span class="p">))(</span><span class="n">z_log_var</span><span class="p">)</span>

<span class="n">eps</span> <span class="o">=</span> <span class="n">Input</span><span class="p">(</span><span class="n">tensor</span><span class="o">=</span><span class="n">K</span><span class="o">.</span><span class="n">random_normal</span><span class="p">(</span><span class="n">stddev</span><span class="o">=</span><span class="n">epsilon_std</span><span class="p">,</span>
                                   <span class="n">shape</span><span class="o">=</span><span class="p">(</span><span class="n">K</span><span class="o">.</span><span class="n">shape</span><span class="p">(</span><span class="n">x</span><span class="p">)[</span><span class="mi">0</span><span class="p">],</span> <span class="n">latent_dim</span><span class="p">)))</span>
<span class="n">z_eps</span> <span class="o">=</span> <span class="n">Multiply</span><span class="p">()([</span><span class="n">z_sigma</span><span class="p">,</span> <span class="n">eps</span><span class="p">])</span>
<span class="n">z</span> <span class="o">=</span> <span class="n">Add</span><span class="p">()([</span><span class="n">z_mu</span><span class="p">,</span> <span class="n">z_eps</span><span class="p">])</span>

<span class="n">x_pred</span> <span class="o">=</span> <span class="n">decoder</span><span class="p">(</span><span class="n">z</span><span class="p">)</span>

<span class="n">vae</span> <span class="o">=</span> <span class="n">Model</span><span class="p">(</span><span class="n">inputs</span><span class="o">=</span><span class="p">[</span><span class="n">x</span><span class="p">,</span> <span class="n">eps</span><span class="p">],</span> <span class="n">outputs</span><span class="o">=</span><span class="n">x_pred</span><span class="p">)</span> <span class="c1"># set the data flow in model</span>
<span class="n">vae</span><span class="o">.</span><span class="n">compile</span><span class="p">(</span><span class="n">optimizer</span><span class="o">=</span><span class="s1">&#39;rmsprop&#39;</span><span class="p">,</span> <span class="n">loss</span><span class="o">=</span><span class="n">nll</span><span class="p">)</span> <span class="c1"># complie the network</span>
<span class="n">vae</span><span class="o">.</span><span class="n">summary</span><span class="p">()</span> <span class="c1"># print out the summary</span>

<span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">),</span> <span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="n">y_test</span><span class="p">)</span> <span class="o">=</span> <span class="n">mnist</span><span class="o">.</span><span class="n">load_data</span><span class="p">()</span> <span class="c1"># load the dataset</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">x_train</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">,</span> <span class="n">original_dim</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.</span> <span class="c1"># scale it between 0 and 1</span>
<span class="n">x_test</span> <span class="o">=</span> <span class="n">x_test</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">,</span> <span class="n">original_dim</span><span class="p">)</span> <span class="o">/</span> <span class="mf">255.</span>

<span class="n">start_time</span> <span class="o">=</span> <span class="n">time</span><span class="o">.</span><span class="n">time</span><span class="p">()</span>

<span class="n">vae</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span>
        <span class="n">x_train</span><span class="p">,</span>
        <span class="n">shuffle</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
        <span class="n">epochs</span><span class="o">=</span><span class="n">epochs</span><span class="p">,</span>
        <span class="n">batch_size</span><span class="o">=</span><span class="n">batch_size</span><span class="p">,</span>
        <span class="n">validation_data</span><span class="o">=</span><span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="n">x_test</span><span class="p">))</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;</span><span class="se">\n</span><span class="s2"> Time elapsed to train the model </span><span class="si">{}</span><span class="s2"> seconds&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">time</span><span class="o">.</span><span class="n">time</span><span class="p">()</span> <span class="o">-</span> <span class="n">start_time</span><span class="p">))</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>__________________________________________________________________________________________________
Layer (type)                    Output Shape         Param #     Connected to                     
==================================================================================================
input_4 (InputLayer)            (None, 784)          0                                            
__________________________________________________________________________________________________
dense_9 (Dense)                 (None, 256)          200960      input_4[0][0]                    
__________________________________________________________________________________________________
dense_10 (Dense)                (None, 2)            514         dense_9[0][0]                    
__________________________________________________________________________________________________
dense_11 (Dense)                (None, 2)            514         dense_9[0][0]                    
__________________________________________________________________________________________________
kl_divergence_layer_1 (KLDiverg [(None, 2), (None, 2 0           dense_10[0][0]                   
                                                                 dense_11[0][0]                   
__________________________________________________________________________________________________
lambda_1 (Lambda)               (None, 2)            0           kl_divergence_layer_1[0][1]      
__________________________________________________________________________________________________
input_5 (InputLayer)            (None, 2)            0                                            
__________________________________________________________________________________________________
multiply_1 (Multiply)           (None, 2)            0           lambda_1[0][0]                   
                                                                 input_5[0][0]                    
__________________________________________________________________________________________________
add_1 (Add)                     (None, 2)            0           kl_divergence_layer_1[0][0]      
                                                                 multiply_1[0][0]                 
__________________________________________________________________________________________________
sequential_1 (Sequential)       (None, 784)          202256      add_1[0][0]                      
==================================================================================================
Total params: 404,244
Trainable params: 404,244
Non-trainable params: 0
__________________________________________________________________________________________________
Train on 60000 samples, validate on 10000 samples
Epoch 1/100
60000/60000 [==============================] - 2s 37us/step - loss: 234.9104 - val_loss: 192.3357
Epoch 2/100
60000/60000 [==============================] - 1s 23us/step - loss: 186.5784 - val_loss: 181.0162
Epoch 3/100
60000/60000 [==============================] - 1s 22us/step - loss: 178.6773 - val_loss: 175.1911
Epoch 4/100
60000/60000 [==============================] - 1s 22us/step - loss: 174.2515 - val_loss: 172.9111
Epoch 5/100
60000/60000 [==============================] - 1s 23us/step - loss: 171.5355 - val_loss: 170.3217
Epoch 6/100
60000/60000 [==============================] - 1s 22us/step - loss: 169.6911 - val_loss: 169.0792
Epoch 7/100
60000/60000 [==============================] - 1s 22us/step - loss: 168.4322 - val_loss: 168.1663
Epoch 8/100
60000/60000 [==============================] - 1s 22us/step - loss: 167.3823 - val_loss: 166.9796
Epoch 9/100
60000/60000 [==============================] - 1s 21us/step - loss: 166.4135 - val_loss: 167.1353
Epoch 10/100
60000/60000 [==============================] - 1s 23us/step - loss: 165.6024 - val_loss: 165.8053
Epoch 11/100
60000/60000 [==============================] - 1s 22us/step - loss: 164.8787 - val_loss: 165.0401
Epoch 12/100
60000/60000 [==============================] - 1s 23us/step - loss: 164.2053 - val_loss: 165.2607
Epoch 13/100
60000/60000 [==============================] - 1s 22us/step - loss: 163.6489 - val_loss: 164.3496
Epoch 14/100
60000/60000 [==============================] - 1s 23us/step - loss: 163.1289 - val_loss: 163.2703
Epoch 15/100
60000/60000 [==============================] - 1s 22us/step - loss: 162.6436 - val_loss: 163.1854
Epoch 16/100
60000/60000 [==============================] - 1s 23us/step - loss: 162.1711 - val_loss: 163.1525
Epoch 17/100
60000/60000 [==============================] - 1s 23us/step - loss: 161.7417 - val_loss: 162.3797
Epoch 18/100
60000/60000 [==============================] - 1s 23us/step - loss: 161.2951 - val_loss: 162.1096
Epoch 19/100
60000/60000 [==============================] - 1s 23us/step - loss: 160.8510 - val_loss: 161.3820
Epoch 20/100
60000/60000 [==============================] - 1s 23us/step - loss: 160.4277 - val_loss: 161.3295
Epoch 21/100
60000/60000 [==============================] - 1s 23us/step - loss: 159.9978 - val_loss: 160.8269
Epoch 22/100
60000/60000 [==============================] - 1s 23us/step - loss: 159.5668 - val_loss: 160.5462
Epoch 23/100
60000/60000 [==============================] - 1s 23us/step - loss: 159.1577 - val_loss: 159.7400
Epoch 24/100
60000/60000 [==============================] - 1s 23us/step - loss: 158.8066 - val_loss: 159.8707
Epoch 25/100
60000/60000 [==============================] - 1s 23us/step - loss: 158.4376 - val_loss: 159.9845
Epoch 26/100
60000/60000 [==============================] - 1s 22us/step - loss: 158.0947 - val_loss: 158.7971
Epoch 27/100
60000/60000 [==============================] - 1s 22us/step - loss: 157.7457 - val_loss: 158.6334
Epoch 28/100
60000/60000 [==============================] - 1s 22us/step - loss: 157.4913 - val_loss: 158.5484
Epoch 29/100
60000/60000 [==============================] - 1s 22us/step - loss: 157.1803 - val_loss: 158.5117
Epoch 30/100
60000/60000 [==============================] - 1s 22us/step - loss: 156.9216 - val_loss: 157.8205
Epoch 31/100
60000/60000 [==============================] - 1s 21us/step - loss: 156.6489 - val_loss: 157.9257
Epoch 32/100
60000/60000 [==============================] - 1s 23us/step - loss: 156.3994 - val_loss: 157.5149
Epoch 33/100
60000/60000 [==============================] - 1s 23us/step - loss: 156.2074 - val_loss: 157.5822
Epoch 34/100
60000/60000 [==============================] - 1s 22us/step - loss: 155.9994 - val_loss: 157.3981
Epoch 35/100
60000/60000 [==============================] - 1s 22us/step - loss: 155.7571 - val_loss: 157.1518
Epoch 36/100
60000/60000 [==============================] - 1s 23us/step - loss: 155.5578 - val_loss: 157.1819
Epoch 37/100
60000/60000 [==============================] - 1s 22us/step - loss: 155.3806 - val_loss: 156.7611
Epoch 38/100
60000/60000 [==============================] - 1s 23us/step - loss: 155.2012 - val_loss: 156.6896
Epoch 39/100
60000/60000 [==============================] - 1s 21us/step - loss: 154.9812 - val_loss: 156.7668
Epoch 40/100
60000/60000 [==============================] - 1s 22us/step - loss: 154.8103 - val_loss: 156.3583
Epoch 41/100
60000/60000 [==============================] - 1s 22us/step - loss: 154.6671 - val_loss: 156.6438
Epoch 42/100
60000/60000 [==============================] - 1s 23us/step - loss: 154.5455 - val_loss: 156.1162
Epoch 43/100
60000/60000 [==============================] - 1s 23us/step - loss: 154.3551 - val_loss: 156.3259
Epoch 44/100
60000/60000 [==============================] - 1s 22us/step - loss: 154.2049 - val_loss: 155.7684
Epoch 45/100
60000/60000 [==============================] - 1s 23us/step - loss: 154.0789 - val_loss: 156.2242
Epoch 46/100
60000/60000 [==============================] - 1s 22us/step - loss: 153.9382 - val_loss: 155.7789
Epoch 47/100
60000/60000 [==============================] - 1s 23us/step - loss: 153.7479 - val_loss: 155.7379
Epoch 48/100
60000/60000 [==============================] - 1s 23us/step - loss: 153.6737 - val_loss: 156.2381
Epoch 49/100
60000/60000 [==============================] - 1s 24us/step - loss: 153.5355 - val_loss: 156.3142
Epoch 50/100
60000/60000 [==============================] - 1s 23us/step - loss: 153.4282 - val_loss: 156.8041
Epoch 51/100
60000/60000 [==============================] - 1s 23us/step - loss: 153.2801 - val_loss: 156.3907
Epoch 52/100
60000/60000 [==============================] - 1s 22us/step - loss: 153.1587 - val_loss: 155.7791
Epoch 53/100
60000/60000 [==============================] - 1s 22us/step - loss: 153.0714 - val_loss: 154.9173
Epoch 54/100
60000/60000 [==============================] - 1s 22us/step - loss: 152.9349 - val_loss: 154.7544
Epoch 55/100
60000/60000 [==============================] - 1s 22us/step - loss: 152.8554 - val_loss: 154.9752
Epoch 56/100
60000/60000 [==============================] - 1s 22us/step - loss: 152.7203 - val_loss: 155.2010
Epoch 57/100
60000/60000 [==============================] - 1s 22us/step - loss: 152.6773 - val_loss: 154.8780
Epoch 58/100
60000/60000 [==============================] - 1s 23us/step - loss: 152.5351 - val_loss: 154.5578
Epoch 59/100
60000/60000 [==============================] - 1s 22us/step - loss: 152.4476 - val_loss: 155.6259
Epoch 60/100
60000/60000 [==============================] - 1s 22us/step - loss: 152.3511 - val_loss: 154.9918
Epoch 61/100
60000/60000 [==============================] - 1s 22us/step - loss: 152.2615 - val_loss: 155.2616
Epoch 62/100
60000/60000 [==============================] - 1s 23us/step - loss: 152.1447 - val_loss: 155.0990
Epoch 63/100
60000/60000 [==============================] - 1s 22us/step - loss: 152.0820 - val_loss: 154.4859
Epoch 64/100
60000/60000 [==============================] - 1s 23us/step - loss: 151.9916 - val_loss: 154.4727
Epoch 65/100
60000/60000 [==============================] - 1s 23us/step - loss: 151.9183 - val_loss: 154.0028
Epoch 66/100
60000/60000 [==============================] - 1s 22us/step - loss: 151.8348 - val_loss: 154.0699
Epoch 67/100
60000/60000 [==============================] - 1s 22us/step - loss: 151.7396 - val_loss: 154.1101
Epoch 68/100
60000/60000 [==============================] - 1s 22us/step - loss: 151.6684 - val_loss: 154.2410
Epoch 69/100
60000/60000 [==============================] - 1s 23us/step - loss: 151.5826 - val_loss: 154.9938
Epoch 70/100
60000/60000 [==============================] - 1s 22us/step - loss: 151.5165 - val_loss: 154.0476
Epoch 71/100
60000/60000 [==============================] - 1s 22us/step - loss: 151.4143 - val_loss: 154.1996
Epoch 72/100
60000/60000 [==============================] - 1s 23us/step - loss: 151.3643 - val_loss: 153.9309
Epoch 73/100
60000/60000 [==============================] - 1s 22us/step - loss: 151.2858 - val_loss: 153.8714
Epoch 74/100
60000/60000 [==============================] - 1s 22us/step - loss: 151.2477 - val_loss: 154.2708
Epoch 75/100
60000/60000 [==============================] - 1s 22us/step - loss: 151.1333 - val_loss: 154.1023
Epoch 76/100
60000/60000 [==============================] - 1s 23us/step - loss: 151.1102 - val_loss: 153.8809
Epoch 77/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.9951 - val_loss: 154.2788
Epoch 78/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.9169 - val_loss: 154.1629
Epoch 79/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.9079 - val_loss: 154.4757
Epoch 80/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.8050 - val_loss: 153.6610
Epoch 81/100
60000/60000 [==============================] - 1s 22us/step - loss: 150.7630 - val_loss: 153.3357
Epoch 82/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.7020 - val_loss: 154.1864
Epoch 83/100
60000/60000 [==============================] - 1s 22us/step - loss: 150.6278 - val_loss: 153.5816
Epoch 84/100
60000/60000 [==============================] - 1s 22us/step - loss: 150.5541 - val_loss: 153.4668
Epoch 85/100
60000/60000 [==============================] - 1s 21us/step - loss: 150.5154 - val_loss: 154.0894
Epoch 86/100
60000/60000 [==============================] - 1s 22us/step - loss: 150.4466 - val_loss: 153.7805
Epoch 87/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.3828 - val_loss: 153.4874
Epoch 88/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.3477 - val_loss: 153.4577
Epoch 89/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.3145 - val_loss: 153.6972
Epoch 90/100
60000/60000 [==============================] - 1s 22us/step - loss: 150.2430 - val_loss: 153.4721
Epoch 91/100
60000/60000 [==============================] - 1s 22us/step - loss: 150.1462 - val_loss: 153.4662
Epoch 92/100
60000/60000 [==============================] - 1s 22us/step - loss: 150.1221 - val_loss: 153.7196
Epoch 93/100
60000/60000 [==============================] - 1s 23us/step - loss: 150.0817 - val_loss: 152.9837
Epoch 94/100
60000/60000 [==============================] - 1s 22us/step - loss: 149.9932 - val_loss: 154.5758
Epoch 95/100
60000/60000 [==============================] - 1s 23us/step - loss: 149.9806 - val_loss: 153.9324
Epoch 96/100
60000/60000 [==============================] - 1s 22us/step - loss: 149.8812 - val_loss: 153.6572
Epoch 97/100
60000/60000 [==============================] - 1s 22us/step - loss: 149.8875 - val_loss: 153.1628
Epoch 98/100
60000/60000 [==============================] - 1s 22us/step - loss: 149.8087 - val_loss: 153.3031
Epoch 99/100
60000/60000 [==============================] - 1s 22us/step - loss: 149.7823 - val_loss: 153.3017
Epoch 100/100
60000/60000 [==============================] - 1s 22us/step - loss: 149.6818 - val_loss: 153.5316

 Time elapsed to train the model 135.9676914215088 seconds
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># display a 2D manifold of the digits</span>
<span class="n">n</span> <span class="o">=</span> <span class="mi">10</span>  <span class="c1"># figure with 15x15 digits</span>
<span class="n">digit_size</span> <span class="o">=</span> <span class="mi">28</span>
<span class="n">u_grid</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">dstack</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">meshgrid</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mf">0.05</span><span class="p">,</span> <span class="mf">0.95</span><span class="p">,</span> <span class="n">n</span><span class="p">),</span>
                               <span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mf">0.05</span><span class="p">,</span> <span class="mf">0.95</span><span class="p">,</span> <span class="n">n</span><span class="p">)))</span>
<span class="n">z_grid</span> <span class="o">=</span> <span class="n">norm</span><span class="o">.</span><span class="n">ppf</span><span class="p">(</span><span class="n">u_grid</span><span class="p">)</span>
<span class="n">x_decoded_n</span> <span class="o">=</span> <span class="n">decoder</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">z_grid</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="n">n</span><span class="o">*</span><span class="n">n</span><span class="p">,</span> <span class="mi">2</span><span class="p">))</span>
<span class="n">x_decoded_w</span> <span class="o">=</span> <span class="n">x_decoded_n</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="n">n</span><span class="p">,</span> <span class="n">n</span><span class="p">,</span> <span class="n">digit_size</span><span class="p">,</span> <span class="n">digit_size</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">13</span><span class="p">,</span> <span class="mi">13</span><span class="p">))</span>
<span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">block</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="nb">map</span><span class="p">(</span><span class="nb">list</span><span class="p">,</span> <span class="n">x_decoded_w</span><span class="p">))),</span> <span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;gray&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

<div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>In this notebook we saw the various application and architectures of Auto Encoders and by this time you would have got an idea about how useful this network can be. With the robustness and versatility this network brings i am sure it would inspire you all to give it a try and see it for yourself how useful it can be.</p>
<p>Once again thanks for going though this notebook.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><img src="https://images.pexels.com/photos/908301/pexels-photo-908301.jpeg?cs=srgb&amp;dl=blackboard-board-close-up-908301.jpg&amp;fm=jpg" alt=""></p>

</div>
</div>
</div>
    </div>
  </div>
</body>

 


</html>
