Mehedi AI Assistant — প্রথম PWA প্রোটোটাইপ

এই সংস্করণে:
- Chrome Web Speech API দিয়ে Malay (ms-MY) অথবা Bengali (bn-BD) স্পিচ শনাক্ত করার চেষ্টা করে।
- MyMemory Translation API দিয়ে ms<->bn অনুবাদ করে। বেনামী ব্যবহারে দৈনিক সীমা আছে (প্রায় ৫,০০০ অক্ষর/দিন; পরিষেবা নীতি পরিবর্তন হতে পারে)।
- ফোনের browser speechSynthesis দিয়ে অনুবাদ পড়ে শোনায়; উপলভ্য বাংলা/মালয় ভয়েস ডিভাইসভেদে আলাদা।
- PWA shell cache হয়; অফলাইন ভয়েস ট্রান্সক্রিপশন/অনুবাদ এই সংস্করণে নেই।

চালানোর নিয়ম:
1. HTTPS-এ হোস্ট করতে হবে (যেমন GitHub Pages/Netlify static hosting)।
2. Android Chrome-এ ওয়েবসাইট খুলে মাইক্রোফোন অনুমতি দিন।
3. মালয়->বাংলা বা বাংলা->মালয় নির্বাচন করে Start চাপুন।
4. স্ক্রিন খোলা রেখে পরীক্ষা করুন।

সীমাবদ্ধতা:
- এটি পরীক্ষামূলক প্রোটোটাইপ, সম্পূর্ণ ২৪/৭ assistant নয়।
- Chrome-এর SpeechRecognition continuous session মাঝেমধ্যে বন্ধ হতে পারে; কোড পুনরায় চালুর চেষ্টা করে, নিশ্চয়তা নেই।
- স্ক্রিন বন্ধ/অন্য অ্যাপে গেলে ওয়েব পেজ মাইক্রোফোন চালিয়ে যেতে পারবে না। এর জন্য native Android foreground microphone service, ব্যবহারকারীর দৃশ্যমান অনুমতি ও স্থায়ী notification প্রয়োজন।
- SpeechRecognition browser/Google service availability ও language support-এর ওপর নির্ভরশীল।
- নাম ধরে ডাক শনাক্তকরণ খুব প্রাথমিক keyword heuristic; বক্তার পরিচয় বা উদ্দেশ্য নিশ্চিত করে না।
- আশেপাশের মানুষের কথার অডিও/টেক্সট তৃতীয় পক্ষের speech service ও MyMemory-তে পাঠানো হতে পারে। অন্যদের সম্মতি ও স্থানীয় আইন মেনে ব্যবহার করুন; গোপনে রেকর্ড করবেন না।
