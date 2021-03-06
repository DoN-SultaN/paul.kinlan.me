---
slug: using-web-mentions-in-a-static-sitehugo-
date: 2019-10-07T20:11:30.489Z
title: 'Using Web Mentions in a static site (Hugo)'
link: ''
tags: [webmentions, hugo]
---

எனது வலைப்பதிவு முற்றிலும் நிலையான தளமாகும், இது ஹ்யூகோவுடன் கட்டப்பட்டது மற்றும் ஜீட் உடன் வழங்கப்படுகிறது. இது எனக்கு ஒரு சிறந்த தீர்வாகும், ஒரு எளிய வலைப்பதிவில் ஒரு அழகான எளிமையான வரிசைப்படுத்தல் செயல்முறை உள்ளது, மேலும் இது வேகமாக வேகமாக ஏற்றப்படுகிறது.

நிலையான முறையில் உருவாக்கப்பட்ட தளங்கள் சில குறைபாடுகளைக் கொண்டுள்ளன, உங்கள் பக்கத்தில் ஒருங்கிணைக்க உங்களுக்கு ஏதேனும் மாறும் போது மிகப்பெரியது (எடுத்துக்காட்டாக கருத்துகள்). டைனமிக் உள்ளடக்கத்தை எளிதில் ஹோஸ்ட் செய்ய முடியாமல் போவதால், நீங்கள் 3 வது தரப்பு ஜாவாஸ்கிரிப்டை நம்பியிருப்பீர்கள், அது உங்கள் பக்கத்திற்கு முழு அணுகலைப் பெறும், மேலும் அது என்ன செய்கிறது என்று உங்களுக்குத் தெரியாது - இது உங்கள் பயனர்களைக் கண்காணிக்கும் அல்லது உங்கள் பக்கத்தை மெதுவாக்குகிறது ஏற்ற.

பயனர் கருத்துகளுக்கு ( `IntersectionObserver` ஐப் பயன்படுத்தி) உருட்டும் போது மட்டுமே ஏற்றுவதன் மூலம் எனது தற்போதைய கருத்து விட்ஜெட்டை ( `IntersectionObserver` ) முக்கியமான ரெண்டர் பாதையில் இருந்து `IntersectionObserver` , இது சுமை செயல்திறன் மற்றும் கண்காணிப்பு சிக்கல்களுக்கு ஒரு நியாயமான தீர்வாக இருக்கும்போது, நான் உண்மையில் அகற்ற விரும்பினேன் அனைத்தையும் ஒன்றாக இணைக்கவும்.

[Webmention](https://webmention.net/draft/) விவரக்குறிப்பை உள்ளிடவும். வெப்மென்ட் என்பது ஒரு விவரக்குறிப்பாகும், இது உங்கள் தளத்தில் உள்ளடக்கத்தை மற்றொரு தளம் &#39;குறிப்பிடும்போது&#39; (அல்லது விரும்புகிறது) ஒரு தள ஆசிரியரை எவ்வாறு தொடர்பு கொள்ளலாம் என்பதை விவரிக்கிறது. இது இறுதியில் உங்கள் தளத்துடன் இணைக்கும் உள்ளடக்கத்தைக் கண்டுபிடிப்பதற்கான ஒரு பரவலாக்கப்பட்ட முறையை அனுமதிக்கிறது, வட்டம் மதிப்பு மற்றும் நுண்ணறிவை வழங்குகிறது.

&#39;குறிப்பிடும் தளம்&#39; கூறியதைத் தொடர்புகொள்வதற்குப் பயன்படுத்தப்பட வேண்டிய எந்தவொரு தரவு வடிவங்களையும் வெப்மெஷன் ஸ்பெக் விவரிக்கவில்லை, இது பக்கத்தின் உள்ளடக்கத்தைப் புரிந்துகொள்ள நிலையான மைக்ரோஃபார்மாட்கள் அல்லது பிற வழிமுறைகளைப் பயன்படுத்தி அலசுவதற்கு உங்களை விட்டுச்செல்கிறது. இது சிறந்தது, இருப்பினும் இது [webmention.io](https://webmention.io/) போன்ற மையப்படுத்தப்பட்ட சேவைகளுக்கு வழிவகுக்கிறது என்று நான் நம்புகிறேன்.

வெப்மென்ஷனைப் பயன்படுத்துவதற்கான யோசனை எனக்கு பிடித்திருந்தது, ஆனால் உங்கள் தளத்தை யாராவது குறிப்பிடும்போது அறிவிப்புகளைப் பெற (மற்றும் சேமிக்க) சேவையக பக்க அமைப்பு தேவைப்படுகிறது, இது எனது தளத்தில் இருப்பதைப் போன்ற நிலையான பில்டருடன் எப்போதும் சாத்தியமில்லை. இந்த இடுகையின் மீதமுள்ளவை எனது ஜீட் ஹோஸ்ட் செய்யப்பட்ட ஹ்யூகோ உருவாக்கத்தில் எனக்கு எப்படி விருப்பங்கள், குறிப்புகள் மற்றும் மறுபதிவுகள் கிடைத்தன என்பதை விரைவாக விவரிக்கும்.

### படி ஒன்று - ஒரு வலைப்பக்க மையத்தைக் கண்டறியவும்

நான் webmention.io ஐக் கண்டேன், அது தந்திரத்தை செய்கிறது. இது உள்வரும் பிங்க்பேக்குகளைக் கையாளுகிறது மற்றும் குறிப்பிடுகிறது, இது அழைப்பு தளம் உண்மையில் உங்கள் உள்ளடக்கத்துடன் இணைக்கப்படுவதையும் சரிபார்க்கும், மேலும் இது தரவைப் பக்கத்திலிருந்து அலசும், இதனால் சூழலைப் பற்றி உங்களுக்கு கொஞ்சம் புரிதல் இருக்கும்.

ஒரு திறந்த அங்கீகார செயல்முறை மூலம் நீங்கள் தளத்தை சொந்தமாக வைத்திருப்பதை Webmention.io சரிபார்க்கும் (இது ஒரு அங்கீகார வழங்குநரை சுட்டிக்காட்டும் rel = me ஐ தேடுவது சுத்தமாக இருந்தது)

### படி இரண்டு - நீங்கள் குறிப்பிடக்கூடிய பக்கங்களைக் கூறவும்

பின்வரும் இரண்டு `link` குறிச்சொற்களைச் சேர்ப்பது போல இது எளிது

```html
<link rel="webmention" href="https://webmention.io/paul.kinlan.me/webmention">
<link rel="pingback" href="https://webmention.io/paul.kinlan.me/xmlrpc">
```

### படி மூன்று - உங்கள் தளத்தில் webmention.io API ஐ ஒருங்கிணைக்கவும்

உங்களிடம் இங்கே இரண்டு விருப்பங்கள் உள்ளன, உங்கள் பக்கத்தில் ஒரு விட்ஜெட்டை நீங்கள் சேர்க்கலாம், அது webmention.io API ஐ அழைக்கும், அல்லது webmention.io API ஐ உங்கள் உருவாக்க கட்டத்தில் ஒருங்கிணைக்கலாம். முடிந்தவரை சிறிய 3 வது தரப்பு JS ஐ ஹோஸ்ட் செய்ய விரும்புகிறேன், எனவே நான் பிந்தையதைத் தேர்ந்தெடுத்தேன். எனது வரிசைப்படுத்தல் செயல்முறைக்கு நான் வலைதளங்களை ஒருங்கிணைத்தேன்.

உருவாக்கம் வேகமாக இருப்பதால் நான் ஹ்யூகோவைப் பயன்படுத்துகிறேன், அதை மனதில் கொண்டு, வெப்மென்ட் ஏபிஐ ஐ ஹ்யூகோவுடன் எவ்வாறு உகந்த முறையில் ஒருங்கிணைப்பது என்பதை நான் செய்ய வேண்டியிருந்தது. எனது தளத்தின் ஒவ்வொரு பக்கத்திற்கும் ஏபிஐ எண்ட்பாயிண்ட் என்று அழைக்காதது கடினமான தடை, எனக்கு நிறைய பக்கங்கள் உள்ளன, இன்னும் நிறைய கருத்துகள் இல்லை.

அதிர்ஷ்டவசமாக Webmention.io தளம் ஒரு எளிதான இறுதிப் புள்ளியை வழங்குகிறது, இது உங்கள் டொமைனுக்கான அனைத்து குறிப்புகளையும் பெற அனுமதிக்கும். துரதிர்ஷ்டவசமான பிட் என்னவென்றால், உங்கள் தளத்திற்கு எதிராக செய்யப்பட்ட ஒவ்வொரு செயலுக்கும் ஒரு கோப்பு இந்த கோப்பில் உள்ளது.

எந்தவொரு பக்கத்திற்கும் நேரடியாக வார்ப்புருவில் இழுக்கக்கூடிய தரவுக் கோப்புகளின் கருத்தையும் ஹ்யூகோ கொண்டுள்ளது, எனவே நீங்கள் ஒரு புதிய கட்டமைப்பிற்கு வெப்மென்ஷன் தரவுக் கோப்பை வரைபடமாக்க வேண்டும், இது ஹ்யூகோ வார்ப்புருவுக்குள் எளிதாகப் படிக்க உதவுகிறது.

நான் தேர்ந்தெடுத்த செயல்முறை கீழே உள்ளது, ஆனால் சுருக்கம் என்னவென்றால், செயல்களின் பட்டியலிலிருந்து வரிசையை URL இன் அகராதிக்கு மாற்றுகிறேன், ஒவ்வொன்றும் ஏபிஐ வெளிப்படுத்திய செயல்களைக் கொண்டிருக்கின்றன (போன்றவை, மறுபதிவு மற்றும் பதில் போன்றவை), மற்றும் இறுதி படி பின்னர் URL களின் அகராதியை URL இன் md5 ஹாஷ் என பெயரிடப்பட்ட தனிப்பட்ட கோப்புகளாக பிரிக்கவும்.

```javascript
"use strict";

const fs = require('fs');
const fetch = require('node-fetch');
const md5 = require('md5');

const processMentionsJson = (data) => {
  const urlData = {};
  data.children.forEach(item => {
    const wmProperty = item["wm-property"];
    const url = item[wmProperty];

    if(url in urlData === false) urlData[url] = {};
    const urlDataItem = urlData[url];

    if(wmProperty in urlDataItem === false) urlDataItem[wmProperty] = [];
    urlDataItem[wmProperty].push(item);
  });

  console.log(urlData);

  // For each URL in the blog we now have a JSON stucture that has all the like, mentions and reposts
  if(fs.existsSync('./data') === false) fs.mkdirSync('./data');
  Object.keys(urlData).forEach(key => {
    const item = urlData[key];
    const md5url = md5(key);
    console.log(key, md5url)
    fs.writeFileSync(`./data/${md5url}.json`, JSON.stringify(item));
  });
}

(async () => {
  const mentionsUrl = new URL(process.argv[2]); // Fail hard if it's not a uRL

  const mentionsResponse = await fetch(mentionsUrl);
  const mentiosnJson = await mentionsResponse.json();

  processMentionsJson(mentiosnJson);
})();
```

தரவு பாகுபடுத்தப்பட்டு சரியாக சேமிக்கப்பட்டதும், இது வார்ப்புருவை அமைப்பதற்கான விரைவான செயல்முறையாகும், இதனால் வார்ப்புருவின் தரவு பண்புக்கூறுகளில் அதைப் படிக்க முடியும்.

```html
{{ $urlized := .Page.Permalink | md5 }}
{{ if index .Site.Data $urlized }}
  {{ $likes := index (index .Site.Data $urlized) "like-of" }}
  {{ $replys := index (index .Site.Data $urlized) "in-reply-to" }}
  {{ $reposts := index (index .Site.Data $urlized) "repost-of"}}
  <h4>Likes</h4>
  {{ range $i, $like := $likes }}
    <a href="{{$like.url}}"><img src="{{ $like.author.photo}}" alt="{{ $like.author.name }}" class="profile photo"></a>
  {{end}}

  <h4>Reposts</h4>
  {{ range $i, $repost := $reposts }}
    <a href="{{$repost.url}}"><img src="{{ $repost.author.photo}}" alt="{{ $repost.author.name }}" class="profile photo"></a>
  {{end}}

  <h4>Comments and Replies</h4>
  {{ range $i, $reply := $replys }}
    <a href="{{$reply.url}}"><img src="{{ $reply.author.photo}}" alt="{{ $reply.author.name }}" class="profile photo"></a>
  {{end}}
{{end}}
```

எல்லாம் சரியாக நடந்தால், பக்கத்தின் அடிப்பகுதியில் சில ஐகான்களை நீங்கள் காண வேண்டும், அவை தளத்துடன் தொடர்பு கொள்ளும் உண்மையான நபர்கள்.

### படி 4 - கருத்துகள் நிகழும்போது தளத்தை வெளியிடுங்கள்

மேற்கூறிய படிகள் குறிப்புகளைக் கூட்டி அவற்றை தளங்களின் வெளியீட்டில் வழங்க அனுமதிக்கும் அதே வேளையில், தளங்கள் தொடர்ந்து புனரமைக்கப்படுவதை உறுதி செய்ய வேண்டும், இதனால் கருத்துகள் பொதுவில் தோன்றும்.

ஒரு எளிய கிரான் சேவையைப் பயன்படுத்த நான் தேர்வுசெய்தேன், இது ஒவ்வொரு மணி நேரத்திற்கும் மேலாக தளத்தின் மறு-டிபோலியை கட்டாயப்படுத்த ஜீட்டின் வரிசைப்படுத்தல் API ஐ அழைக்கும்.
