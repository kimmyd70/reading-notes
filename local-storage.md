## Local Storage [Article](http://diveinto.html5doctor.com/storage.html)

- For native applications, the operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state. These values may be stored in the registry, INI files, XML files, or some other place according to platform convention. 

- If your native client application needs local storage beyond key/value pairs, you can embed your own database, invent your own file format, or any number of other solutions.

- Web Applications use Cookies, but:
    - Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over

    - Cookies are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)

    - Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful

- Before HTML5, specific to a single browser or dependent on 3rd-party plugin

- HTML5 has solved what used to be hard to achieve:
    - a lot of storage space
    - on the client
    - that persists beyond a page refresh
    - and isn’t transmitted to the server

- "Local Storage" or "DOM Storage" is an HTML5 specification named **Web Storage**

- Check in .js if browser supports the `localStorage` object:
```
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}
```
- or use `Modernizer`
```
if (Modernizr.localstorage) {
  // window.localStorage is available!
} else {
  // no native support for HTML5 storage :(
  // maybe try dojox.storage or a third-party solution
}
```
use `localStorage.setItem(key,value);` to send something to local storage

**Use `JSON.stringify()` to convert javascript object literal to string for local storage**

[object literal](./images/object-literal.png)

[set local storage](./images/set-local-storage.png)


**COME BACK TO THIS ARTICLE FOR SPECIFIC COMMANDS TO USE, TRACK CHANGES, AND FURTHER READING SUGGESTIONS**
