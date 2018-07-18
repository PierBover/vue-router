# Vue Router fork for Chrome OS

This is a fork from Vue Router `3.0.1` to overcome some Chrome OS limitations for Chrome apps.

Chrome OS apps crash when accessing the `window.history` object. The problem is that even when using Vue Router in hash mode it still accesses `window.history`. This fork fixes that.

This fork is really a **quick hack** only intended to be used in hash mode, but I personally use it in a Chrome OS app and it works fine for that purpose.

To use this repo in your project simply:
```
npm install pierbover/vue-router#chrome-os
```
And then:
```
import Vue from 'vue';
import Router from 'vue-router-chrome-os';

Vue.use(Router);

const router = new Router(...);
```

For the moment it's not possible to use `router.go(n) `, but otherwise it behaves like Vue Router in hash mode.

I have created a [feature request](https://github.com/vuejs/vue-router/issues/2304) to solve this but I doubt there will be interest by the Vue team since Chrome OS is still pretty exotic thing.
