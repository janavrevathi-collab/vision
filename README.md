<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>KIDPRENEUR – Student Startup Ideas</title>
<style>
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:"Segoe UI", Arial, sans-serif; color:#333; line-height:1.6; 
      background:url('images/bg.jpg') no-repeat center center/cover; }

/* Navbar */
header { background:rgba(43,103,119,0.9); color:white; padding:15px 40px;
         display:flex; justify-content:space-between; align-items:center;
         position:sticky; top:0; z-index:100; backdrop-filter: blur(6px);}
header h1 { font-size:1.8rem; letter-spacing:1px; }
nav a { margin-left:20px; color:white; text-decoration:none; font-weight:500; transition:0.3s;}
nav a:hover { color:#ffd166; }

/* Hero */
.hero { text-align:center; padding:70px 20px; background:rgba(200,216,228,0.85);}
.hero h2 { font-size:2.8rem; margin-bottom:15px; color:#2b6777;}
.hero p { font-size:1.2rem; max-width:700px; margin:auto; }

/* Sections */
section { padding:40px 20px; }
h2.section-title { text-align:center; margin-bottom:20px; font-size:2rem; color:#2b6777; }

/* Forms */
.auth-form, #ideaForm, .profile-card {
  background:white; padding:25px; margin:20px auto; width:90%; max-width:500px;
  border-radius:16px; box-shadow:0 4px 10px rgba(0,0,0,0.1);
}
input, textarea, select { width:100%; padding:12px; margin:10px 0;
  border:1px solid #bbb; border-radius:10px; font-size:1rem; }
button { background:#2b6777; color:white; border:none; padding:12px 20px;
  font-size:1rem; cursor:pointer; border-radius:10px; transition:0.3s; }
button:hover { background:#ffd166; color:#333; }

/* Cards */
.cards { display:grid; grid-template-columns: repeat(auto-fit, minmax(260px,1fr)); gap:20px; margin:20px; }
.card { background:white; padding:20px; border-radius:16px; box-shadow:0 4px 10px rgba(0,0,0,0.1); transition: transform 0.2s; }
.card:hover { transform:translateY(-5px); }
.card h3 { color:#2b6777; margin-bottom:8px; }
.card p { margin:5px 0; }
.vote-btn { background:#ffd166; border:none; padding:8px 14px; border-radius:8px; cursor:pointer; font-size:0.9rem; margin-top:10px; }
.vote-btn:hover { background:#ffb703; }

/* Competition + Certificates */
#competition { background:rgba(230,240,243,0.9); }
.certificate { border:2px dashed #2b6777; padding:20px; border-radius:12px; background:#fff3cd; margin:10px 0; }

/* Profile */
.profile-card h3 { color:#2b6777; margin-bottom:10px; }
#profilePic { width:100px; height:100px; border-radius:50%; object-fit:cover; margin-bottom:10px; }

/* Footer */
footer { text-align:center; padding:15px; background:#2b6777; color:white; margin-top:20px; }

#logoutBtn { display:none; margin:10px auto; display:block; }
</style>
</head>
<body>

<header>
<h1>KIDPRENEUR</h1>
<nav>
<a href="#home">Home</a>
<a href="#submit">Submit Idea</a>
<a href="#leaderboard">Leaderboard</a>
<a href="#ideas">Ideas</a>
<a href="#competition">Competition</a>
<a href="#about">About</a>
<a href="#contact">Contact</a>
<a href="#profile">Profile</a>
</nav>
</header>

<section class="hero" id="home">
<h2>💡 Share Your Startup Ideas</h2>
<p>A platform where middle & senior students showcase their innovative startup ideas and inspire the world.</p>
</section>

<!-- Login / Signup -->
<div class="auth-form" id="authForm">
<h3>Login</h3>
<input type="text" id="loginUsername" placeholder="Username">
<input type="password" id="loginPassword" placeholder="Password">
<button id="loginBtn">Login</button>
<hr>
<h3>Signup</h3>
<input type="text" id="signupUsername" placeholder="New Username">
<input type="password" id="signupPassword" placeholder="New Password">
<button id="signupBtn">Signup</button>
</div>
<button id="logoutBtn">Logout</button>

<!-- Profile -->
<section id="profile" style="display:none;">
<div class="profile-card">
<h3>👤 My Profile</h3>
<img id="profilePic" src="images/default-avatar.png" alt="Profile Picture">
<br>
<input type="file" id="profilePicUpload" accept="image/*">
<p><strong>Username:</strong> <span id="profileUser"></span></p>
<p><strong>Ideas Submitted:</strong> <span id="profileIdeas"></span></p>
<p><strong>Total Votes:</strong> <span id="profileVotes"></span></p>
</div>
</section>

<!-- Submit Idea Form -->
<section id="submit" style="display:none;">
<form id="ideaForm">
<h2>🚀 Submit Your Idea</h2>
<input type="text" id="name" placeholder="Your Name" required>
<input type="text" id="title" placeholder="Startup Idea Title" required>
<textarea id="problem" rows="4" placeholder="What problem does it solve?" required></textarea>
<input type="file" id="file">
<button type="submit">Submit Idea</button>
</form>
</section>

<!-- Leaderboard -->
<section id="leaderboard">
<h2 class="section-title">🏅 Leaderboard – Top Ideas</h2>
<div class="cards" id="leaderboardContainer"></div>
</section>

<!-- All Ideas -->
<section id="ideas">
<h2 class="section-title">✨ Student Startup Ideas</h2>
<div class="cards" id="ideasContainer"></div>
</section>

<!-- Competition -->
<section id="competition">
<h2 class="section-title">🏆 Competition Center</h2>
<p>Weekly & Monthly Competitions are always live! Winners are shown here ⬇️</p>
<div id="winnersContainer"></div>
</section>

<section id="about">
<h2 class="section-title">About Kidpreneur</h2>
<p>Kidpreneur is a digital stage where student entrepreneurs can share their ideas, learn from others, and inspire innovation. Every idea is a step toward building a brighter future.</p>
</section>

<section id="contact">
<h2 class="section-title">📩 Contact Us</h2>
<form>
<input type="text" placeholder="Your Name" required>
<input type="email" placeholder="Your Email" required>
<textarea rows="4" placeholder="Your Message" required></textarea>
<button type="submit">Send Message</button>
</form>
</section>

<footer>
© 2025 Kidpreneur | Designed for Design Championship
</footer>

<script>
// Users & Ideas
let users = JSON.parse(localStorage.getItem("users")) || [];
let ideas = JSON.parse(localStorage.getItem("ideas")) || [];
let profiles = JSON.parse(localStorage.getItem("profiles")) || {};
let voted = JSON.parse(localStorage.getItem("voted")) || {};
let currentUser = localStorage.getItem("currentUser") || null;

// Signup
document.getElementById("signupBtn").onclick = () => {
  const username = document.getElementById("signupUsername").value.trim();
  const password = document.getElementById("signupPassword").value.trim();
  if(!username||!password) return alert("Enter all fields!");
  if(users.find(u=>u.username===username)) return alert("Username exists!");
  users.push({username,password});
  localStorage.setItem("users",JSON.stringify(users));
  alert("Signup successful! Please login.");
};

// Login
document.getElementById("loginBtn").onclick = () => {
  const username = document.getElementById("loginUsername").value.trim();
  const password = document.getElementById("loginPassword").value.trim();
  const user = users.find(u=>u.username===username && u.password===password);
  if(!user) return alert("Invalid login!");
  currentUser=username;
  localStorage.setItem("currentUser",currentUser);
  alert("Welcome "+currentUser);
  updateUI();
};

// Logout
document.getElementById("logoutBtn").onclick = () => {
  currentUser=null;
  localStorage.removeItem("currentUser");
  document.getElementById("authForm").style.display="block";
  document.getElementById("logoutBtn").style.display="none";
  document.getElementById("submit").style.display="none";
  document.getElementById("profile").style.display="none";
};

// Auto login
if(currentUser) updateUI();

// Submit Idea
document.getElementById("ideaForm").addEventListener("submit", e=>{
  e.preventDefault();
  if(!currentUser) return alert("Please login first!");
  const newIdea={
    id:Date.now(),
    name:document.getElementById("name").value,
    title:document.getElementById("title").value,
    problem:document.getElementById("problem").value,
    votes:0,
    by:currentUser
  };
  ideas.push(newIdea);
  localStorage.setItem("ideas",JSON.stringify(ideas));
  alert("🎉 Your idea is uploaded!");
  loadIdeas(); loadLeaderboard(); loadWinners(); loadProfile();
});

// Load Ideas
function loadIdeas(){
  const container=document.getElementById("ideasContainer");
  container.innerHTML="";
  ideas.forEach(i=>{
    const div=document.createElement("div");
    div.className="card";
    div.innerHTML=`<h3>${i.title}</h3><p><strong>By:</strong> ${i.name}</p><p>${i.problem}</p>
    <button class="vote-btn" onclick="voteIdea(${i.id})">👍 Vote (${i.votes})</button>`;
    container.appendChild(div);
  });
}

// Vote Idea (1 per account)
function voteIdea(id){
  voted[currentUser]=voted[currentUser]||[];
  if(voted[currentUser].includes(id)) return alert("You can vote only once per idea!");
  const idea=ideas.find(i=>i.id===id);
  idea.votes++; voted[currentUser].push(id);
  localStorage.setItem("ideas",JSON.stringify(ideas));
  localStorage.setItem("voted",JSON.stringify(voted));
  loadIdeas(); loadLeaderboard(); loadProfile();
}

// Leaderboard
function loadLeaderboard(){
  const container=document.getElementById("leaderboardContainer");
  container.innerHTML="";
  ideas.sort((a,b)=>b.votes-a.votes).slice(0,5).forEach((i,index)=>{
    const div=document.createElement("div");
    div.className="card";
    div.innerHTML=`<h3>#${index+1} ${i.title}</h3><p><strong>By:</strong> ${i.name}</p>
    <p>${i.problem}</p><p>Votes: ${i.votes}</p>`;
    container.appendChild(div);
  });
}

// Competition Winners (simulate)
function loadWinners(){
  const container=document.getElementById("winnersContainer");
  container.innerHTML="";
  ideas.sort((a,b)=>b.votes-a.votes).slice(0,3).forEach((i,index)=>{
    const div=document.createElement("div");
    div.className="certificate";
    div.innerHTML=`🏆 Winner #${index+1}: ${i.title} by ${i.name}`;
    container.appendChild(div);
  });
}

// Profile
function loadProfile(){
  document.getElementById("profileUser").innerText=currentUser;
  const userIdeas=ideas.filter(i=>i.by===currentUser);
  document.getElementById("profileIdeas").innerText=userIdeas.length;
  const totalVotes=userIdeas.reduce((a,b)=>a+b.votes,0);
  document.getElementById("profileVotes").innerText=totalVotes;
  document.getElementById("profile").style.display="block";
  document.getElementById("profilePic").src=profiles[currentUser]?.pic||"images/default-avatar.png";
}

// Profile Picture Upload
document.getElementById("profilePicUpload").addEventListener("change", function(){
  const file=this.files[0];
  if(file){
    const reader=new FileReader();
    reader.onload=function(e){
      profiles[currentUser]=profiles[currentUser]||{};
      profiles[currentUser].pic=e.target.result;
      localStorage.setItem("profiles",JSON.stringify(profiles));
      document.getElementById("profilePic").src=e.target.result;
    }
    reader.readAsDataURL(file);
  }
});

// Update UI
function updateUI(){
  document.getElementById("authForm").style.display="none";
  document.getElementById("logoutBtn").style.display="block";
  document.getElementById("submit").style.display="block";
  loadIdeas(); loadLeaderboard(); loadWinners(); loadProfile();
}
</script>

</body>
</html>

