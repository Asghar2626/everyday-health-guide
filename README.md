
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Everyday Health Guide</title>
<meta name="description" content="Everyday health tips, nutrition and wellness advice.">
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#f5faf6;color:#26382f;line-height:1.7}
header{background:#176b50;color:white;text-align:center;padding:28px 15px}
header h1{margin:0}
nav{background:#10523d;text-align:center;padding:12px}
nav a{color:white;text-decoration:none;margin:0 10px}
main{max-width:900px;margin:auto;padding:20px 15px}
.hero,.article{background:white;border-radius:12px;padding:20px;margin-bottom:16px}
.hero{background:#e4f4e9;text-align:center}
h2{color:#176b50}
.article h3{margin-top:0}
.article a{color:#176b50;text-decoration:none}
.article a:hover{text-decoration:underline}
.date{font-size:13px;color:#68776e}
footer{background:#10523d;color:white;text-align:center;padding:20px}
</style>
</head>
<body>
<header>
<h1>Everyday Health Guide</h1>
<p>Simple guidance for a healthier everyday life</p>
</header>
<nav>
<a href="#home">Home</a>
<a href="#articles">Health Articles</a>
<a href="#about">About</a>
</nav>
<main>
<section class="hero" id="home">
<h2>Your Guide to Better Health</h2>
<p>Explore health tips, nutrition, wellness and healthy living.</p>
</section>
<section id="articles">
<h2>Latest Health Articles</h2>
<div id="posts">Loading articles...</div>
</section>
<section class="article" id="about">
<h2>About Us</h2>
<p>Everyday Health Guide shares general health and wellness information for educational purposes. It is not a substitute for professional medical advice.</p>
</section>
</main>
<footer>© 2026 Everyday Health Guide</footer>
<script>
function showPosts(data){
 const box=document.getElementById('posts');
 box.textContent='';
 const entries=data.feed && data.feed.entry;
 if(!entries || !entries.length){
   box.textContent='No public articles found. Please check Blogger feed settings.';
   return;
 }
 entries.forEach(function(post){
   const card=document.createElement('article');
   card.className='article';
   const title=document.createElement('h3');
   const link=(post.link||[]).find(x=>x.rel==='alternate');
   const a=document.createElement('a');
   a.textContent=post.title.$t;
   a.href=link?link.href:'https://everydayhealthguide0047.blogspot.com/';
   const date=document.createElement('p');
   date.className='date';
   date.textContent=new Date(post.published.$t).toLocaleDateString();
   const excerpt=document.createElement('p');
   const raw=(post.summary&&post.summary.$t)||(post.content&&post.content.$t)||'';
   const temp=document.createElement('div');
   temp.innerHTML=raw;
   excerpt.textContent=(temp.textContent||'').slice(0,180)+'...';
   title.appendChild(a);
   card.appendChild(title);
   card.appendChild(date);
   card.appendChild(excerpt);
   box.appendChild(card);
 });
}
</script>
<script 
<script>
(function(){
  var s=document.createElement('script');
  s.src='https://everydayhealthguide0047.blogspot.com/feeds/posts/default?alt=json-in-script&max-results=10&callback=showPosts';
  s.onerror=function(){
    document.getElementById('posts').textContent='Articles load nahi ho sake. Blogger feed settings check karein.';
  };
  document.body.appendChild(s);
})();
</script>
