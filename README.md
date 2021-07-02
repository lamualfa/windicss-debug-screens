# windicss-debug-screens
Alternative [tailwindcss-debug-screens](https://github.com/jorenvanhee/tailwindcss-debug-screens) in Windi CSS.

![image](https://user-images.githubusercontent.com/39755201/124317822-f7e30500-dba1-11eb-8273-e5be4937b9ae.png)
> Source: https://github.com/jorenvanhee/tailwindcss-debug-screens

## Features

- Zero dependencies
- Really fully customizable
- No need to install any additional dependencies
- Just copy and paste it

See the Demo [here](https://windicss.org/play.html?html=DwEwlgbgBAxgNgQwM5ILwHIQFMBGBXAcwFokYAnLLAOyXQD5gB6cCOoA&css=HQEwpgRgrg5gtAZwMYCcxgHYIAQG8BQAkAAICGADuQDYCe2EYAZgPZoBcEzALl8wLZwADPSaswbKky5CRLdowCWADzAhZYtgC84AbQBMARgAsAdiMAOAMwA2UwF117ckrgHH4rmCXSEfdx3gIKlIkAGt-T284AHcACwVPfwRY0hBmaLglKmxiXw5RdiRmDE8S3QAiZDRMNl9yh2I%2BEHy5cSKSzGkdStR0DDYm%2BpyqGBaNdtKunur%2BkaHiLLHC4smKqr62LPm9RYZWtgnOtd6anaohgB48vfGVo%2B71moxisHqAbnwAXyA).

## Preparation

Base class names:

`before:change-position-y-0 before:change-position-x-0 before:fixed before:z-[2147483647] before:px-1 before:text-sm before:bg-black before:text-white before:shadow-xl @sm:before:content-["screen:sm"] @md:before:content-["screen:md"] @lg:before:content-["screen:lg"] @xl:before:content-["screen:xl"] @2xl:before:content-["screen:2xl"] <sm:before:content-["screen:none"]`

**Important**

- Change `change-position-y` to `top` or `bottom`.
- Change `change-position-x` to `left` or `right`.
- `2147483647` is the max value of CSS `z-index`. See [this answer for more details](https://stackoverflow.com/a/856569/10861398).

## Installation

Just paste the _Base class names_ above to your `body` or `div` or any other HTML element that you want.

**Example**

```html
<body class='before:bottom-0 before:left-0 before:fixed before:z-[2147483647] before:px-1 before:text-sm before:bg-black before:text-white before:shadow-xl @sm:before:content-["screen:sm"] @md:before:content-["screen:md"] @lg:before:content-["screen:lg"] @xl:before:content-["screen:xl"] @2xl:before:content-["screen:2xl"] <sm:before:content-["screen:none"]'>
<!--  Your code  -->
</body>
```

> Important to use single quote (') instead double quotes (") to wrap the attribute class.


**Hey! But it looks dirty. is there a cleaner and neater way?**

Yes. You can put the _Base class names_ to `shortcuts` field in `windi.config.js` file.

**`windi.config.js`**

```js
export default {
  shortcuts: {
    "debug-screens": 'before:bottom-0 before:left-0 before:fixed before:z-[2147483647] before:px-1 before:text-sm before:bg-black before:text-white before:shadow-xl @sm:before:content-["screen:sm"] @md:before:content-["screen:md"] @lg:before:content-["screen:lg"] @xl:before:content-["screen:xl"] @2xl:before:content-["screen:2xl"] <sm:before:content-["screen:none"]'
  }
}
```
and then use it in your HTML element.

**Example**

```html
<body class="debug-screens">
<!--  Your code  -->
</body>
```

## Notes

Make sure the class is only present during development.

```jsx
<body class={ devMode ? 'debug-screens' : '' }>
```

<hr/>

Watch this [issue](https://github.com/windicss/plugins/issues/7) to follow any update about the availability of `tailwindcss-debug-screens` as a Windi CSS plugin.
