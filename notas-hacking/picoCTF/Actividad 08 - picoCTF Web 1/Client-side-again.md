# Client-side-again
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/56816/` ([link](https://jupiter.challenges.picoctf.org/problem/56816/)) or http://jupiter.challenges.picoctf.org:56816
What is obfuscation?

## Solución
Para este reto entre a la pagina, vi el código fuente y copie el código de javascript y usando jsnice se identó el código para que fuera mas legible, y arme la bandera que estaba en ese código
```
picoCTF{not_this_again_337115}

/** @type {Array} */
var _0x5a46 = ["37115}", "_again_3", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
(function(paths, opt_attributes) {
  /**
   * @param {number} val
   * @return {undefined}
   */
  var setter = function(val) {
    for (;--val;) {
      paths["push"](paths["shift"]());
    }
  };
  setter(++opt_attributes);
})(_0x5a46, 435);
/**
 * @param {string} key
 * @param {?} dataAndEvents
 * @return {?}
 */
var _0x4b5b = function(key, dataAndEvents) {
  /** @type {number} */
  key = key - 0;
  var label = _0x5a46[key];
  return label;
};
/**
 * @return {undefined}
 */
function verify() {
  checkpass = document[_0x4b5b("0x0")]("pass")[_0x4b5b("0x1")];
  /** @type {number} */
  split = 4;
  if (checkpass[_0x4b5b("0x2")](0, split * 2) == _0x4b5b("0x3")) {
    if (checkpass[_0x4b5b("0x2")](7, 9) == "{n") {
      if (checkpass[_0x4b5b("0x2")](split * 2, split * 2 * 2) == _0x4b5b("0x4")) {
        if (checkpass[_0x4b5b("0x2")](3, 6) == "oCT") {
          if (checkpass[_0x4b5b("0x2")](split * 3 * 2, split * 4 * 2) == _0x4b5b("0x5")) {
            if (checkpass["substring"](6, 11) == "F{not") {
              if (checkpass[_0x4b5b("0x2")](split * 2 * 2, split * 3 * 2) == _0x4b5b("0x6")) {
                if (checkpass[_0x4b5b("0x2")](12, 16) == _0x4b5b("0x7")) {
                  alert(_0x4b5b("0x8"));
                }
              }
            }
          }
        }
      }
    }
  } else {
    alert(_0x4b5b("0x9"));
  }
}
;
```
