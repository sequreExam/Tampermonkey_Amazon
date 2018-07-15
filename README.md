# Tampermonkey_Amazon
どうして日本Amazonだけtarget=blankなのか、これがわからない

  // ==UserScript==
  // @name         Amazon
  // @namespace    http://tampermonkey.net/
  // @version      0.1
  // @description  Kills `target="_blank"` on search result screen
  // @author       sequre
  // @match        https://www.amazon.co.jp/*
  // @grant        none
  // ==/UserScript==
  "use strict";

  const targets = document.querySelectorAll("a");
  const lengthTarget = targets.length;
  let i;

  for(i = 0; i < lengthTarget; i++)
  {
      targets[i].setAttribute("target", "_self");
  }
