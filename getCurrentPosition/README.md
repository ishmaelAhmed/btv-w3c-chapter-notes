# All about 
## navigator.geolocation.getCurrentPosition()

## Chrome

When the user denies Chrome you get the following as an error condition that you can then parse with the 
error hadeling call back. But to deny once is to deny for ever unless you change the permissions for the page.

```js
PositionError {
    message: "User denied Geolocation",
    code: 1,
    PERMISSION_DENIED: 1,
    POSITION_UNAVAILABLE: 2,
    TIMEOUT: 3
}
```

## Firefox 

Firefox allows for subtle gradations. You can allow or deny for just now. Denying for the session seems to stop processing the geolocation call. This kida sucks for the app dev. What is one to do, create custom listeners and timeouts?
If you deny forever then you get the error, just like in chrome, but why would you not get an error back? Why not tell the app directly instead of forcing the dev to handel it via time outs and fancy coding?


## Let try with out an internet connection

### Firefox

```js
Object {
    PERMISSION_DENIED = 1, POSITION_UNAVAILABLE = 2, TIMEOUT = 3
}
```

### Chrome

```js
PositionError {
    message: "Network location provider at 'https://www.googleapis.com/' : No response received.",
    code: 2,
    PERMISSION_DENIED: 1,
    POSITION_UNAVAILABLE: 2,
    TIMEOUT: 3
}

```

I like the chrome info better, it tells me more, firefox is functional but still not very verbose.


