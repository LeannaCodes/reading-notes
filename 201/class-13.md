# Data Persistance (saving)

Cookies can be used for persistent local storage of small amounts of data. 

The downsides to cookies are: 
1. cookies are inlucded with every HTTP request which slows things down by needlessly transmitting the same data over and over. 
2. included with every HTTP request, therefore sending data. unencrypted over the internet. 
3. cookies are limited to 4KB of data - enough to slow down your application but not enough to be terribly useful. 

What we really want is 

1. a lot of space
2. on the client
3. that persists beyond a page refresh 
4. and isn't transmitted to the server 

Before HTML 5, all attempts to achieve this were ultimatley unsatisfactory in different ways. 

## Introducing HTML5 Storage

also known as local storage or DOM storage. Simply put, it's a way for web pages to store named key/value pairs locally, within the client web browser. Like cookies, this data persists even after you navigate away from the web site, close your browser tab, exit your browser, or what have you. Unlike cookies, this data is never transmitted to the remote web server (unless you go out of your way to send it manually). Unlike all previous attempts at providing persistent local storage, it is implemented natively in web browsers, so it is available even when third-party browser plugins are not.

From your javascript code, you'll access HTML5 Storage through the localStorage object on the global window object. Before you can use it, you should detect whether the browser supports it. 

How to check for HTML storage: 

```
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}
```

Instead of writing the code yourself, you can use `Modernizr` to detect support for HTML5 storage.
```
if (Modernizr.localstorage) {
  // window.localStorage is available!
} else {
  // no native support for HTML5 storage :(
  // maybe try dojox.storage or a third-party solution
}
```

## Using HTML5 Storage 

HTML5 Storage is based on named key/value pairs. You store data based on a named key, then you can retrieve that data with the same key. The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats. However, the data is actually stored as a string. If you are storing and retrieving anything other than strings, you will need to use functions like `parseInt()` or parseFloat() to coerce your retrieved data into the expected JavaScript datatype.

```
interface Storage {
  getter any getItem(in DOMString key);
  setter creator void setItem(in DOMString key, in any data);
};
```

Calling `setItem()` with a named key that already exists will silently overwrite the previous value. Calling `getItem()` with a non-existent key will return null rather than throw an exception.

Like other JavaScript objects, you can treat the localStorage object as an associative array. Instead of using the `getItem()` and `setItem()` methods, you can simply use square brackets. For example, this snippet of code:

```
let foo = localStorage.getItem("bar");
```
// ...
```localStorage.setItem("bar", foo);
…could be rewritten to use square bracket syntax instead:

var foo = localStorage["bar"];
// ...
localStorage["bar"] = foo;
There are also methods for removing the value for a given named key, and clearing the entire storage area (that is, deleting all the keys and values at once).

interface Storage {
  deleter void removeItem(in DOMString key);
  void clear();
};
Calling removeItem() with a non-existent key will do nothing.

Finally, there is a property to get the total number of values in the storage area, and to iterate through all of the keys by index (to get the name of each key).

interface Storage {
  readonly attribute unsigned long length;
  getter DOMString key(in unsigned long index);
};
If you call key() with an index that is not between 0–(length-1), the function will return null.

