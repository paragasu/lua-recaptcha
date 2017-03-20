# lua-recaptcha
Google backend implementation for lua.


# Installation

```
  #luarocks install lua-recaptcha
```

# Client side integration

Paste the following snippet in the HEAD section

```
<script src='https://www.google.com/recaptcha/api.js'></script>
```

Paste the following at the end of the form. You need to specify the callback function to
handle the result.

```
<button class="g-recaptcha" data-sitekey="<your-site-key>" data-callback="YourOnSubmitFn"> Submit </button>
```

  

# API

new(site_key, secret_key)
- param site_key string  from google dashboard
- param secret_key string from google dashboard


valid(g_captcha_response, remote_ip)
- param g_captcha_reponse string the value of g-captcha-response
- param remote_ip string client remote ip address  
- return boolean


# Usage

```lua
  local recaptcha = require 'recaptcha'
  local captcha   = recaptcha:new(site_key, secret_key) 
  if captcha.valid(g_captcha_response, remote_ip) then
    ngx.say('valid captcha')
  end
```


# Reference
[Recaptcha API](https://developers.google.com/recaptcha/docs/invisible)
