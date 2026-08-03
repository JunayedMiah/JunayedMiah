# Md Junayed Miah — Portfolio Site

একটা single-page portfolio, GitHub Pages-এ পাবলিশ করার জন্য রেডি।
কোনো build step লাগবে না — শুধু `index.html` একটা ফাইল, browser-এ open করলেই কাজ করে।

## GitHub-এ পাবলিশ করবেন কীভাবে

1. GitHub-এ একটা নতুন repository বানান — নাম দিন `your-username.github.io`
   (এই নামটা দিলে site-টা সরাসরি `https://your-username.github.io` তে চলে যাবে।
   অন্য যেকোনো নাম দিলে site চলবে `https://your-username.github.io/repo-name` এই লিংকে।)
2. এই folder-এর সব ফাইল (`index.html`, `resume.pdf`, `images/`, `README.md`) সেই repo-তে push করুন:
   ```
   git init
   git add .
   git commit -m "Add portfolio site"
   git branch -M main
   git remote add origin https://github.com/your-username/your-username.github.io.git
   git push -u origin main
   ```
3. Repo-র **Settings → Pages**-এ গিয়ে Source হিসেবে `main` branch, `/ (root)` folder সিলেক্ট করে Save করুন।
4. ১-২ মিনিট পর site live হয়ে যাবে।

## যা এখনই বদলাতে হবে

`index.html` ফাইলে এই দুই জায়গায় placeholder link আছে (৩ বার করে আসে — hero, footer):
```
https://linkedin.com/in/REPLACE-WITH-YOUR-LINKEDIN
https://github.com/REPLACE-WITH-YOUR-GITHUB
```
এগুলো নিজের আসল লিংক দিয়ে replace করুন (Find & Replace ব্যবহার করলে সহজ হবে)।

## নতুন প্রজেক্ট যোগ করবেন কীভাবে

`index.html`-এর একদম নিচে `<script>` ব্লকের ভেতর `projectsData` নামে একটা array আছে।
নতুন প্রজেক্ট যোগ করতে, এই shape কপি করে নিচে বসান:

```js
{
  title: "Project Name",
  subtitle: "One-line tech/summary",
  dates: "Month Year – Month Year",
  stages: ["Extract", "Clean"],   // Extract, Clean, Transform, Validate, Join, Load, Analyze, Visualize, Report, Document — যেগুলো relevant
  bullets: ["What you did", "What it produced or improved"],
  link: "https://github.com/you/repo",   // না থাকলে "" রাখুন
  image: ""                              // ছবি থাকলে "images/project5.png", না থাকলে "" রাখুন
},
```

Save করে refresh করলেই নতুন কার্ড automatically grid-এ যোগ হয়ে যাবে — HTML-এ হাত দেওয়া লাগবে না।

নতুন চাকরি/experience যোগ করতে একইভাবে উপরে `experienceData` array-তে entry যোগ করুন।

## ছবি যোগ করবেন কীভাবে

- **প্রোফাইল ছবি**: `images/` folder-এ আপনার ছবি রাখুন (যেমন `profile.jpg`), তারপর `index.html`-এ
  `<div class="avatar">MJM</div>` অংশটা খুঁজে বের করে এটা দিয়ে replace করুন:
  ```html
  <div class="avatar"><img src="images/profile.jpg" alt="Md Junayed Miah" style="width:100%;height:100%;border-radius:50%;object-fit:cover;"></div>
  ```
- **প্রজেক্ট স্ক্রিনশট**: ছবিটা `images/` folder-এ রেখে, সেই প্রজেক্টের `image: ""` কে
  `image: "images/your-file.jpg"` করে দিন। Placeholder box automatically আসল ছবি দিয়ে replace হয়ে যাবে।

## Resume link

"Download CV" বাটন এই folder-এর `resume.pdf`-কে point করে (আপনার আপলোড করা resume থেকেই কপি করা)। নতুন resume version হলে শুধু `resume.pdf` ফাইলটা replace করে দিলেই হবে।

## Local-এ preview করতে চাইলে

শুধু `index.html` ডাবল-ক্লিক করে browser-এ খুলুন — server লাগবে না।
"# mjm.github.io" 
