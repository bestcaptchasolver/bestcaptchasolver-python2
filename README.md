BestCaptchaSolver.com python2 API wrapper
=========================================

bestcaptchasolverapi2 is a super easy to use bypass captcha python2 API wrapper for bestcaptchasolver.com captcha service

## Installation    
    git clone https://github.com/bestcaptchasolver/bestcaptchasolver-python2

## Dependencies
    pip install requests

## Usage
    # make sure you've changed access_key, page_url, etc in main.py
    python main.py  

## How to use?

Simply require the module, set the auth details and start using the captcha service:

``` python
from bestcaptchasolverapi2 import BestCaptchaSolverAPI
```
Set access_token for authentication

``` python
access_token = 'access_token_here'
# get your access token from https://bestcaptchasolver.com/account
bcs = BestCaptchaSolverAPI(ACCESS_TOKEN)
```

Once you've set your authentication details, you can start using the API

**Get balance**

``` python
balance = bcs.account_balance()                 
```

**Submit image captcha**

``` python
bcs.submit_image_captcha('captcha.jpg', False)    # submit image captcha (case_sensitive param optional)
```
The image submission works with both files and b64 encoded strings.
Also for case-sensitive captchas, the 2nd parameter set to True, will make sure case is taken into account.

**Submit recaptcha details**

For recaptcha submission there are two things that are required.
- page_url
- site_key
- proxy (optional)
``` python
bcs.submit_recaptcha(PAGE_URL, SITE_KEY)   
```
This method returns a captchaID. This ID will be used next, to retrieve the g-response, once workers have 
completed the captcha. This takes somewhere between 10-80 seconds.

**Retrieve captcha response (both image and recaptcha)**

```
image_text = bcs.retrieve(captcha_id)
gresponse = bcs.retrieve(recaptcha_id)
```

**Set captcha bad**

When a captcha was solved wrong by our workers, you can notify the server with it's ID,
so we know something went wrong.

``` python
bcs.set_captcha_bad(captcha_id)
```

## Examples
Check main.py

## License
API library is licensed under the MIT License

## More information
More details about the server-side API can be found [here](https://bestcaptchasolver.com/api )


<sup><sub>captcha, bypasscaptcha, decaptcher, decaptcha, 2captcha, deathbycaptcha, anticaptcha, 
bypassrecaptchav2, bypassnocaptcharecaptcha, bypassinvisiblerecaptcha, captchaservicesforrecaptchav2, 
recaptchav2captchasolver, googlerecaptchasolver, recaptchasolverpython, recaptchabypassscript, bestcaptchasolver</sup></sub>
