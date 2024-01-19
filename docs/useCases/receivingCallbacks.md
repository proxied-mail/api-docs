---
sidebar_position: 1
---

# Receiving callbacks on emails

This document describes how to receive callbacks on emails.

Case: you have email address using which you want to get information about incoming emails into your system.

Example: you have: receive-callback@proxiedmail.com and want information send from astrid@aeriscocktails.com being forwarded into your system via HTTP.
Let's say your url for receiving callback is: https://example.com/callback

Please note, that if you wish to omit email delivery somewhere and use only webhook, please use the following email addresses domains:

    @int.proxiedmail.com
    @proxiedmail-int.int

Example: testingadw@proxiedmail-int.int



Steps to do it:

1. Sign up to ProxiedMail 
2. Login to ProxiedMail using your credentials via [login endpoint](/docs/endpoints/login) or manually via UI.
3. Obtain access token via [api-token endpoint](/docs/endpoints/apiToken) or [UI](https://proxiedmail.com/en/settings)
4. Create proxy-email via [proxy-bindings endpoint](/docs/endpoints/postProxyBindings) with specified callback_url: https://example.com/callback or using [UI](https://proxiedmail.com/en/board).
You can also use the UI to create proxy-email with callback_url. Just create proxy-email, click "More" and specify callback url you want to use.

**Important:** If you want to prevent messages of being forwarded to your primary email please use "@int.proxiedmail.com" domain in a real address. Example: aeris1@int.proxiedmail.com


 

![Set up callback img](/img/setupcallback.png)

AND


![Set up callback img](/img/setupcallback2.png)
5. Check out the [main documentation marketing along with marketing materials about it](https://proxiedmail.com/en/webhook-on-email)

6. Check out payload example:


```json
{
"id":"E706070F-2400-0000-00003CC8",
"payload":{
"Content-Type":"multipart\/alternative; boundary=\"00000000000026ed020603f9413b\"",
"Date":"Mon, 28 Aug 2023 11:35:24 +0100",
"Dkim-Signature":"v=1; a=rsa-sha256; c=relaxed\/relaxed; d=holyeat-com.20221208.gappssmtp.com; s=20221208; t=1693218935; x=1693823735; h=to:subject:message-id:date:from:mime-version:from:to:cc:subject :date:message-id:reply-to; bh=DvlZhjB6zfSd4x+w7gp1CxW+6CKagmlXWtT0pE4V96o=; b=p5axjc4sOAtsSeM2Z0Zs23NgGKbde13b3avlr88v6xp2Kwp7kEt8zHurYL8IQBrYpx Ubwl38jJrVmppf2BY57WM8kf5o2Q5F34S5xPWVhSfF0Us+qU4XV1i72w9z35HpuAonb8 RHmcz1s+qXs7XwqzOacGBaIF2EnAfvhkOps2Xd1rYhoT2shGOfWtW6cH7O1E8lPfDhE2 Vh1IDTJU\/mlIdRAVzl3nLBp0YkUQ41BIThHyF11CxnHWakJ4k\/edeAME+rxDSOOX2MEk PhYqLN+igYgO\/76ArXFAZv2BhXmW1VUcXgAfgobBzRWPFeIU2NGMp3ulqc7WxlaWO0M5 4C0Q==",
"From":"Alex Yatsenko <alex@holyeat.com>",
"Message-Id":"<CACkEpfx6-Pj7hr=A9JQz7b1PYaK4i0ZbtcPxG+ZvpiUw4dOj5Q@mail.gmail.com>",
"Mime-Version":"1.0",
"Received":"by mail-ot1-f54.google.com with SMTP id 46e09a7af769-6bd066b0fd4so2034773a34.2 for <news-0197fc@proxiedmail.com>; Mon, 28 Aug 2023 03:35:35 -0700 (PDT)",
"Subject":"Hi man hi",
"To":"news-0197fc@proxiedmail.com",
"X-Envelope-From":"alex@holyeat.com",
"X-Gm-Message-State":"AOJu0YzdfcbOCYb059LkqPRmUwIkQ3Isf8nyLMh92p5lYWVlMOUSjWXE BeQpEj22dKRUpP\/tPyPzOEn0s1mTE8Z6rm4qi+qEzYe2ZQ2hriBxnWdajQ==",
"X-Google-Dkim-Signature":"v=1; a=rsa-sha256; c=relaxed\/relaxed; d=1e100.net; s=20221208; t=1693218935; x=1693823735; h=to:subject:message-id:date:from:mime-version:x-gm-message-state :from:to:cc:subject:date:message-id:reply-to; bh=DvlZhjB6zfSd4x+w7gp1CxW+6CKagmlXWtT0pE4V96o=; b=RESRktBr+d7GsL7AaGh8vvdr5QmI8GTBIBstHT1zwWQSue774dfWBqtJCxcZMsBNrV eZdx0\/7qSebRAEtZdWV4c95\/2amgWtEWlocvEsejq0ztc0aHkGKEjoMhb1m6u6SKUwSk 1GqyKICrK8hup5csJ0+vJSazfY7gaRf1D+L7rR\/CQdzAgcPKcey0W9Oy8pqkQTh81A4T VW2WSbnixs79wcznd\/B3wpMf9LKQVBLSI4yZgC2k7IeYEE3+RQ3SyuHqt5j7YH9afES3 0SeNu3FLQleQG8V6YRGSU7kadklvsaS+rXQfZy7YzOZChbzIltrzM2u5BTtzz7QL4BjA QUcw==",
"X-Google-Smtp-Source":"AGHT+IHdv2RgMkDAb4GuR2+ziXq19m1XSSgP\/QXqpmYCaXJhrQBJ1OswQ9Haov2m7u0uawa+TeTWIfqVZN8oEOxW\/Rk=",
"X-Received":"by 2002:a9d:7a9a:0:b0:6b9:8ea3:2ce0 with SMTP id l26-20020a9d7a9a000000b006b98ea32ce0mr11160533otn.33.1693218935066; Mon, 28 Aug 2023 03:35:35 -0700 (PDT)",
"body-html":"<div dir=\"ltr\">hey man hey<br clear=\"all\"><div><br><\/div><span class=\"gmail_signature_prefix\">-- <\/span><br><div dir=\"ltr\" class=\"gmail_signature\" data-smartmail=\"gmail_signature\"><div dir=\"ltr\"><b><font color=\"#38761d\">Alex<\/font><\/b><div>Co-Founder at HolyEat<\/div><div>Email: <a href=\"mailto:alex@holyeat.com\" target=\"_blank\">alex@holyeat.com<\/a><br><\/div><\/div><\/div><\/div>\r\n",
      "body-plain":"hey man hey\r\n\r\n-- \r\n*Alex*\r\nCo-Founder at HolyEat\r\nEmail: alex@holyeat.com\r\n",
      "domain":"proxiedmail.com",
      "from":"Alex Yatsenko <alex@holyeat.com>",
      "message-headers":"[[\"Received\",\"from mail-ot1-f54.google.com (mail-ot1-f54.google.com [209.85.210.54]) by e6ba948ee866 with SMTP id <undefined> (version=TLS1.3, cipher=TLS_AES_128_GCM_SHA256); Mon, 28 Aug 2023 10:35:35 GMT\"],[\"Received\",\"by mail-ot1-f54.google.com with SMTP id 46e09a7af769-6bd066b0fd4so2034773a34.2 for <news-0197fc@proxiedmail.com>; Mon, 28 Aug 2023 03:35:35 -0700 (PDT)\"],[\"X-Envelope-From\",\"alex@holyeat.com\"],[\"X-Mailgun-Incoming\",\"Yes\"],[\"Dkim-Signature\",\"v=1; a=rsa-sha256; c=relaxed\/relaxed; d=holyeat-com.20221208.gappssmtp.com; s=20221208; t=1693218935; x=1693823735; h=to:subject:message-id:date:from:mime-version:from:to:cc:subject :date:message-id:reply-to; bh=DvlZhjB6zfSd4x+w7gp1CxW+6CKagmlXWtT0pE4V96o=; b=p5axjc4sOAtsSeM2Z0Zs23NgGKbde13b3avlr88v6xp2Kwp7kEt8zHurYL8IQBrYpx Ubwl38jJrVmppf2BY57WM8kf5o2Q5F34S5xPWVhSfF0Us+qU4XV1i72w9z35HpuAonb8 RHmcz1s+qXs7XwqzOacGBaIF2EnAfvhkOps2Xd1rYhoT2shGOfWtW6cH7O1E8lPfDhE2 Vh1IDTJU\/mlIdRAVzl3nLBp0YkUQ41BIThHyF11CxnHWakJ4k\/edeAME+rxDSOOX2MEk PhYqLN+igYgO\/76ArXFAZv2BhXmW1VUcXgAfgobBzRWPFeIU2NGMp3ulqc7WxlaWO0M5 4C0Q==\"],[\"X-Google-Dkim-Signature\",\"v=1; a=rsa-sha256; c=relaxed\/relaxed; d=1e100.net; s=20221208; t=1693218935; x=1693823735; h=to:subject:message-id:date:from:mime-version:x-gm-message-state :from:to:cc:subject:date:message-id:reply-to; bh=DvlZhjB6zfSd4x+w7gp1CxW+6CKagmlXWtT0pE4V96o=; b=RESRktBr+d7GsL7AaGh8vvdr5QmI8GTBIBstHT1zwWQSue774dfWBqtJCxcZMsBNrV eZdx0\/7qSebRAEtZdWV4c95\/2amgWtEWlocvEsejq0ztc0aHkGKEjoMhb1m6u6SKUwSk 1GqyKICrK8hup5csJ0+vJSazfY7gaRf1D+L7rR\/CQdzAgcPKcey0W9Oy8pqkQTh81A4T VW2WSbnixs79wcznd\/B3wpMf9LKQVBLSI4yZgC2k7IeYEE3+RQ3SyuHqt5j7YH9afES3 0SeNu3FLQleQG8V6YRGSU7kadklvsaS+rXQfZy7YzOZChbzIltrzM2u5BTtzz7QL4BjA QUcw==\"],[\"X-Gm-Message-State\",\"AOJu0YzdfcbOCYb059LkqPRmUwIkQ3Isf8nyLMh92p5lYWVlMOUSjWXE BeQpEj22dKRUpP\/tPyPzOEn0s1mTE8Z6rm4qi+qEzYe2ZQ2hriBxnWdajQ==\"],[\"X-Google-Smtp-Source\",\"AGHT+IHdv2RgMkDAb4GuR2+ziXq19m1XSSgP\/QXqpmYCaXJhrQBJ1OswQ9Haov2m7u0uawa+TeTWIfqVZN8oEOxW\/Rk=\"],[\"X-Received\",\"by 2002:a9d:7a9a:0:b0:6b9:8ea3:2ce0 with SMTP id l26-20020a9d7a9a000000b006b98ea32ce0mr11160533otn.33.1693218935066; Mon, 28 Aug 2023 03:35:35 -0700 (PDT)\"],[\"Mime-Version\",\"1.0\"],[\"From\",\"Alex Yatsenko <alex@holyeat.com>\"],[\"Date\",\"Mon, 28 Aug 2023 11:35:24 +0100\"],[\"Message-Id\",\"<CACkEpfx6-Pj7hr=A9JQz7b1PYaK4i0ZbtcPxG+ZvpiUw4dOj5Q@mail.gmail.com>\"],[\"Subject\",\"Hi man hi\"],[\"To\",\"news-0197fc@proxiedmail.com\"],[\"Content-Type\",\"multipart\/alternative; boundary=\\\"00000000000026ed020603f9413b\\\"\"]]",
      "message-url":"https:\/\/storage-us-west1.api.mailgun.net\/v3\/domains\/proxiedmail.com\/messages\/BAABAQUk2a4FYZS5kJNHy7HJFhDKiocHYQ==",
      "recipient":"news-0197fc@proxiedmail.com",
      "sender":"alex@holyeat.com",
      "signature":"7eefdecd51a628c81205961216c269afb48dca53fcb2f71fe13918d6fc8192cc",
      "stripped-html":"<div dir=\"ltr\">hey man hey<br clear=\"all\"><div><br><\/div><span class=\"gmail_signature_prefix\">-- <\/span><br><div dir=\"ltr\" class=\"gmail_signature\" data-smartmail=\"gmail_signature\"><div dir=\"ltr\"><b><font color=\"#38761d\">Alex<\/font><\/b><div>Co-Founder at HolyEat<\/div><div>Email: <a href=\"mailto:alex@holyeat.com\" target=\"_blank\">alex@holyeat.com<\/a><br><\/div><\/div><\/div><\/div>\n",
      "stripped-signature":"-- \r\n*Alex*\r\nCo-Founder at HolyEat\r\nEmail: alex@holyeat.com",
      "stripped-text":"hey man hey",
      "subject":"Hi man hi",
      "timestamp":"1693218935",
      "token":""
   },
   "attachments":[

   ],
   "recipient":{
      "address":"news-0197fc@proxiedmail.com"
   },
   "receivedAt":"Mon Aug 28 2023 10:35:36 GMT+0000",
   "user":{
      "id":"A79E7F62-0000-0000-00009BC6",
      "username":"yatsenkolesh+clao@gmail.com",
      "token":"Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIzIiwianRpIjoiMDkwYTBiY2QyY2NkNmJkN2I2OWI4Nzg3N2NmODYzM2VmMTRiYzYwYTkyZjc0ZmFlMzc4NTRmMGJkODdkYzNkMTcyYjM4MGRhOGE0YjdiNjEiLCJpYXQiOjE2OTMyMTg5MzgsIm5iZiI6MTY5MzIxODkzOCwiZXhwIjoxNjkzMjE4OTM4LCJzdWIiOiI5OTc1Iiwic2NvcGVzIjpbXX0.icMfnGM1eLzW5z3Hz6VeNPtLWwbIW63bG7ZMqQuxDFAlHmprJa9nNBZXZyfFXprNAoN-AKBoBUijS0lgKawTjm6oInGFFU9ypsaJWHW7WIaVR4pc7iYOwJfrrDOqh2sgav9NptU_GTUxw8tOzr3J2Ch7EVXFy1y75khMOLY5sB5ZvrALO_-fVjDHuIDRbCszN0KglrU5xI6-37cYTB4Glo--uNx2TxZOgVj1si7ZHYz7qRmg-PRIxF_tkrQ_8o5bddLqsgdW6_6qEUqKjn5HsQAa71bOrjEkPfoCppzSmeNayC0KQ8MTZdSUovUd1idAwc0pWTVmPlUG3mUZEb2myhn1oMo0CklHc84y9gnNZW0kkH9VQdDDDWPBtChuYCj0zGC46HZjoT3lZceGtlk6pW-qOkfX8Kr_owid8iu4UyCfwc3UisxsilGxB28Y0BwCvz-TLRc_2CgbJNM2rpAMiUoNjr0PzcIylpDwngFRZO-6yvAUaqjRL7ZBLedkwzn-o14Uer2AVn65QBKLBOV-A0FwxNVJ5wzE2PCOd2DN-bpPrORE4WTrkH0USCC9zux1fcwLAQhwRO6YmDfxUA-CjyalicpRG6E7Rban0yy11VBjRjKNx5A8JvzuvwfWGylPO5inm0YBTFL0Q-JzSWhQbv-rVXyDtVKYjUh3m3kCpto"
   }
}
```