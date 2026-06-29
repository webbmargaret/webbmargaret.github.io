---
layout: archive
title: "Research Overview"
permalink: /research-overview/
author_profile: true
---

{% include base_path %}

<div class="research-statement-link" style="margin-bottom: 2em;">
  <a href="{{ base_path }}/files/research_statement.pdf" class="btn btn--primary"><i class="fas fa-file-pdf"></i> Download Research Statement (PDF)</a>
</div>

## Research Overview

My research focuses on how universities can better prepare engineers to solve 
complex real-world problems. My work examines three interconnected questions:

1. Why is it hard for students and professors to work across different fields?
2. How can we study education better and at larger scales without losing quality?
3. How do we actually create change in engineering education?

*All links go to the [Publications page](https://webbmargaret.github.io/publications/).*

<!-- ============================================================
     STYLES
     ============================================================ -->
<style>
.rvis-section { margin: 1.5em 0 2em; }
.rvis-subtitle { font-size: 13px; color: #888; margin: 0 0 0.5em; }
.rvis-legend { display: flex; gap: 14px; flex-wrap: wrap; font-size: 12px; color: #888; margin-bottom: 0.5em; align-items: center; }
.rvis-legend span { display: flex; align-items: center; gap: 5px; }
.rvis-legend i { width: 10px; height: 10px; border-radius: 50%; display: inline-block; flex-shrink: 0; }
.rvis-legend i.sq { border-radius: 2px; width: 11px; height: 11px; }
.rvis-filters { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 0.75em; align-items: center; font-size: 12px; color: #888; }
.rvis-filters button {
  font-size: 12px; padding: 3px 10px; cursor: pointer;
  border-radius: 6px; border: 1px solid #ccc;
  background: transparent; color: #555;
  transition: background 0.15s, color 0.15s;
  font-family: inherit;
}
.rvis-filters button:hover, .rvis-filters button.active {
  background: #f0f0ee; color: #111; border-color: #999;
}
.rvis-canvas-wrap canvas { display: block; width: 100%; border-radius: 8px; }

/* ── tooltip card ── */
#rvis-tip {
  position: fixed;
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 10px 13px;
  font-size: 12px;
  line-height: 1.55;
  color: #222;
  pointer-events: none;
  display: none;
  z-index: 9999;
  max-width: 230px;
  box-shadow: 0 3px 12px rgba(0,0,0,0.13);
  font-family: inherit;
}
#rvis-tip .tip-name { font-weight: 600; font-size: 13px; margin-bottom: 3px; }
#rvis-tip .tip-uni  { color: #555; font-size: 11px; margin-bottom: 2px; }
#rvis-tip .tip-disc { color: #777; font-size: 11px; margin-bottom: 6px; font-style: italic; }
#rvis-tip .tip-stat { color: #444; margin-bottom: 6px; }
#rvis-tip .tip-pubs { display: flex; flex-direction: column; gap: 3px; }
#rvis-tip .tip-pubs a { color: #2a78d6; text-decoration: none; font-size: 11px; line-height: 1.4; }
#rvis-tip .tip-pubs a:hover { text-decoration: underline; }

@media (prefers-color-scheme: dark) {
  .rvis-filters button { border-color: #555; color: #aaa; }
  .rvis-filters button:hover, .rvis-filters button.active { background: #2a2a28; color: #eee; border-color: #777; }
  #rvis-tip { background: #1e1e1c; border-color: #444; color: #eee; box-shadow: 0 3px 12px rgba(0,0,0,0.5); }
  #rvis-tip .tip-uni { color: #aaa; }
  #rvis-tip .tip-disc { color: #888; }
  #rvis-tip .tip-stat { color: #bbb; }
}
</style>

<!-- ============================================================
     COLLABORATOR NETWORK
     ============================================================ -->
<div class="rvis-section">
<p class="rvis-subtitle">Hover a node for details and direct links to shared papers. Drag to rearrange. Node size = number of co-authored papers.</p>
<div class="rvis-legend">
  <span><i style="background:#2a78d6"></i> 3+ papers</span>
  <span><i style="background:#1baf7a"></i> 2 papers</span>
  <span><i style="background:#aaa"></i> 1 paper</span>
  <span><i class="sq" style="background:#EF9F27"></i> You</span>
</div>
<div class="rvis-filters">
  <span>Filter:</span>
  <button class="active" onclick="rvNetFilter('all',this)">All</button>
  <button onclick="rvNetFilter('frequent',this)">Frequent (3+)</button>
  <button onclick="rvNetFilter('recent',this)">2024–2027</button>
</div>
<div class="rvis-canvas-wrap"><canvas id="rvNetCanvas"></canvas></div>
</div>

<!-- ============================================================
     KEYWORD BUBBLES
     ============================================================ -->
<div class="rvis-section">
<p class="rvis-subtitle">Hover a bubble for context. Click any bubble to browse related publications. Bubble size reflects prominence across the body of work.</p>
<div class="rvis-legend">
  <span><i style="background:#2a78d6"></i> Systems &amp; interdisciplinary</span>
  <span><i style="background:#1baf7a"></i> Identity &amp; equity</span>
  <span><i style="background:#e87ba4"></i> Digital justice &amp; community</span>
  <span><i style="background:#4a3aa7"></i> Methods &amp; assessment</span>
  <span><i style="background:#eda100"></i> Postdoc &amp; faculty development</span>
</div>
<div class="rvis-filters">
  <span>Highlight:</span>
  <button class="active" onclick="rvKwFilter('all',this)">All</button>
  <button onclick="rvKwFilter('systems',this)">Systems</button>
  <button onclick="rvKwFilter('identity',this)">Identity &amp; equity</button>
  <button onclick="rvKwFilter('digital',this)">Digital justice</button>
  <button onclick="rvKwFilter('methods',this)">Methods</button>
  <button onclick="rvKwFilter('postdoc',this)">Postdoc</button>
</div>
<div class="rvis-canvas-wrap"><canvas id="rvKwCanvas"></canvas></div>

<!-- shared tooltip for both canvases -->
<div id="rvis-tip"></div>
</div>

<script>
(function() {
var BASE = 'https://webbmargaret.github.io/publication/';

<!-- ============================================================
     COLLABORATOR NETWORK
     ============================================================ -->
/* ──────────────────────────────────────────
   COLLABORATOR DATA
   Each person has: uni, discipline, papers[]
   Each paper: title (short), slug (pub permalink slug)
   ────────────────────────────────────────── */
var collabs = {
  'Paretti': {
    full: 'Marie C. Paretti',
    uni: 'Virginia Tech', discipline: 'Engineering Education',
    count: 8, years: [2022,2023,2023,2023,2023,2024,2024,2025],
    papers: [
      { t: 'Systems to Transform Interdisciplinary Graduate Education (Dissertation)', s: '2025-01-01-systems-to-transform-interdisciplinary-graduate-education-an-ecological-systems' },
      { t: 'Navigating (Inter)disciplinary Systems', s: '2025-01-01-navigating-interdisciplinary-systems-ecological-systems-analysis-of-engineering' },
      { t: 'Beyond Barriers and Supports', s: '2026-01-01-beyond-barriers-and-supports-a-systems-interaction-analysis-of-how-microsystems' },
      { t: 'Breaking Silos', s: '2024-01-01-breaking-silos-rethinking-university-structures-to-facilitate-interdisciplinary' },
      { t: 'Tracking Interdisciplinary Identity-Based Motivation', s: '2025-01-01-tracking-the-evolution-of-interdisciplinary-identity-based-motivation-in-enginee' },
      { t: 'Understanding Ecosystems of Interdisciplinary Graduate Education', s: '2024-01-01-understanding-ecosystems-of-interdisciplinary-graduate-education-through-an-ecol' },
      { t: 'Investigating Graduate Students\' Perspectives', s: '2023-01-01-investigating-graduate-students-perspectives-of-influences-on-interdisciplinary' },
      { t: 'Influences on Displaced Engineering Student Identity', s: '2023-01-01-influences-on-displaced-engineering-student-professional-identity-development-a' },
    ]
  },
  'Baniya': {
    full: 'Sweta Baniya',
    uni: 'Virginia Tech', discipline: 'Technical & Scientific Communication',
    count: 6, years: [2023,2023,2024,2024,2025,2026],
    papers: [
      { t: 'Reimagining Information Architecture', s: '2026-01-01-hidden-curriculum' },
      { t: 'U.S. Hospital Educators\' Technology Needs', s: '2026-01-01-understanding-virginia-us-hospital-educators-work-practices-and-technology-needs_copy' },
      { t: 'Incorporating Community Knowledge in Design', s: '2025-01-01-incorporating-community-knowledge-in-design-a-reflective-account-of-designing-te' },
      { t: 'Enacting Digital Justice', s: '2025-01-01-enacting-digital-justice-in-partnership-with-displaced-refugee-and-immigrant-com' },
      { t: 'Towards Digital Justice (2024)', s: '2024-01-01-towards-digital-justice-and-consolidated-resettlement-resources-for-new-american' },
      { t: 'Towards Digital Justice: Citizenship App', s: '2023-01-01-towards-digital-justice-developing-us-citizenship-application-website-with-refug' },
    ]
  },
  'Powell': {
    full: 'Katrina M. Powell',
    uni: 'Virginia Tech', discipline: 'English / Rhetoric & Displacement Studies',
    count: 4, years: [2023,2023,2024,2025],
    papers: [
      { t: 'Incorporating Community Knowledge in Design', s: '2025-01-01-incorporating-community-knowledge-in-design-a-reflective-account-of-designing-te' },
      { t: 'Enacting Digital Justice', s: '2025-01-01-enacting-digital-justice-in-partnership-with-displaced-refugee-and-immigrant-com' },
      { t: 'Towards Digital Justice (2024)', s: '2024-01-01-towards-digital-justice-and-consolidated-resettlement-resources-for-new-american' },
      { t: 'Towards Digital Justice: Citizenship App', s: '2023-01-01-towards-digital-justice-developing-us-citizenship-application-website-with-refug' },
    ]
  },
  'Scott': {
    full: 'Layla Scott',
    uni: 'Virginia Tech', discipline: 'English / Writing Studies',
    count: 4, years: [2023,2023,2024,2025],
    papers: [
      { t: 'Incorporating Community Knowledge in Design', s: '2025-01-01-incorporating-community-knowledge-in-design-a-reflective-account-of-designing-te' },
      { t: 'Expanding Writing Abundance in the Community', s: '2024-01-01-expanding-writing-abundance-in-partnership-with-the-community' },
      { t: 'Enacting Digital Justice', s: '2025-01-01-enacting-digital-justice-in-partnership-with-displaced-refugee-and-immigrant-com' },
      { t: 'Towards Digital Justice: Citizenship App', s: '2023-01-01-towards-digital-justice-developing-us-citizenship-application-website-with-refug' },
    ]
  },
  'Coso Strong': {
    full: 'Alexandra Coso Strong',
    uni: 'Cornell University', discipline: 'Chemical & Biomolecular Engineering / Engineering Education',
    count: 3, years: [2026,2026,2026],
    papers: [
      { t: 'Building Capacity for Instructional Change', s: '2026-01-01-building-capacity-for-instructional-change-dber-postdoctoral-professional-development' },
      { t: 'Generative Stories Generating Research Insight', s: '2026-01-01-generative-stories-generating-research-insight-genai-enabled-research-fiction' },
      { t: 'Strategies for Hybrid Hands-on Courses', s: '2026-01-01-strategies-for-hybrid-hands-on-courses-in-robotics-embedded-systems-and-iot' },
    ]
  },
  'Werth': {
    full: 'Alexandra Werth',
    uni: 'Cornell University', discipline: 'Biomedical Engineering / Engineering Education',
    count: 3, years: [2026,2026,2026],
    papers: [
      { t: 'Building Capacity for Instructional Change', s: '2026-01-01-building-capacity-for-instructional-change-dber-postdoctoral-professional-development' },
      { t: 'Generative Stories Generating Research Insight', s: '2026-01-01-generative-stories-generating-research-insight-genai-enabled-research-fiction' },
      { t: 'Toward Scalable Assessment of Reflective Practice', s: '2026-01-01-toward-scalable-assessment-of-undergraduate-reflective-practice' },
    ]
  },
  'Deters': {
    full: 'Jessica Deters',
    uni: 'Univ. of Nebraska–Lincoln', discipline: 'Mechanical & Materials Engineering / Engineering Education',
    count: 3, years: [2022,2022,2023],
    papers: [
      { t: 'Building a Sustainable Interdisciplinary Graduate Program', s: '2022-01-01-building-a-sustainable-university-wide-interdisciplinary-graduate-program-to-add' },
      { t: 'Academic Integrity During COVID-19', s: '2022-01-01-exploring-mechanical-engineering-student-perspectives-of-academic-integrity-duri' },
      { t: 'Exploring Interdisciplinary Identity Development', s: '2022-01-01-exploring-interdisciplinary-identity-development-using-possible-selves-an-explor' },
    ]
  },
  'Menon': {
    full: 'Maya Menon',
    uni: 'Virginia Tech', discipline: 'Engineering Education',
    count: 3, years: [2022,2023,2023],
    papers: [
      { t: 'Building a Sustainable Interdisciplinary Graduate Program', s: '2022-01-01-building-a-sustainable-university-wide-interdisciplinary-graduate-program-to-add' },
      { t: 'Understanding Faculty Perspectives of Interdisciplinary Programs', s: '2023-01-01-understanding-faculty-perspectives-of-interdisciplinary-graduate-programs' },
      { t: 'Universities as Living Laboratories for SDGs', s: '2023-01-01-sustainable-development-goals-in-engineering-curriculum-a-document-analysis-on-d' },
    ]
  },
  'Feng': {
    full: 'Xiaoqi Feng',
    uni: 'Aalto University', discipline: 'Engineering / Design Education',
    count: 2, years: [2024,2027],
    papers: [
      { t: 'Finding Common Ground Across Two Institutions', s: '2024-01-01-finding-common-ground-comparing-engineering-and-design-graduate-students-concept' },
      { t: 'Hidden Curriculum of a PhD in EER', s: '2026-01-01-hidden-curriculum' },
    ]
  },
  'Aarnio': {
    full: 'Hanna Aarnio',
    uni: 'Aalto University', discipline: 'Engineering Education',
    count: 2, years: [2024,2027],
    papers: [
      { t: 'Finding Common Ground Across Two Institutions', s: '2024-01-01-finding-common-ground-comparing-engineering-and-design-graduate-students-concept' },
      { t: 'Hidden Curriculum of a PhD in EER', s: '2026-01-01-hidden-curriculum' },
    ]
  },
  'Salem': {
    full: 'Ahoo Salem',
    uni: 'Blue Ridge Literacy Center', discipline: 'Writing Studies / Community Engagement',
    count: 2, years: [2023,2024],
    papers: [
      { t: 'Incorporating Community Knowledge in Design', s: '2025-01-01-incorporating-community-knowledge-in-design-a-reflective-account-of-designing-te' },
      { t: 'Towards Digital Justice: Citizenship App', s: '2023-01-01-towards-digital-justice-developing-us-citizenship-application-website-with-refug' },
    ]
  },
  'McColley': {
    full: 'Campbell McColley',
    uni: 'Cornell University', discipline: 'Engineering Education',
    count: 2, years: [2026,2027],
    papers: [
      { t: 'Toward Scalable Assessment of Reflective Practice', s: '2026-01-01-toward-scalable-assessment-of-undergraduate-reflective-practice' },
      { t: 'Scaling Reflection Quality Assessment with GenAI', s: '2027-01-01-scaling-reflection-quality-assessment-genai-code-type' },
    ]
  },
  'Alrizqi': {
    full: 'Mohammed Alrizqi',
    uni: 'Cornell University', discipline: 'Engineering Education',
    count: 2, years: [2026,2027],
    papers: [
      { t: 'Toward Scalable Assessment of Reflective Practice', s: '2026-01-01-toward-scalable-assessment-of-undergraduate-reflective-practice' },
      { t: 'Scaling Reflection Quality Assessment with GenAI', s: '2027-01-01-scaling-reflection-quality-assessment-genai-code-type' },
    ]
  },
  'Rissler': {
    full: 'Grant Rissler',
    uni: 'Virginia Tech', discipline: 'Sociology / Community Engagement',
    count: 2, years: [2024,2026],
    papers: [
      { t: 'Towards Digital Justice (2024)', s: '2024-01-01-towards-digital-justice-and-consolidated-resettlement-resources-for-new-american' },
      { t: 'Reimagining Information Architecture', s: '2026-01-01-hidden-curriculum' },
    ]
  },
  'Singh': {
    full: 'Harman Singh',
    uni: 'Virginia Tech', discipline: 'Engineering Education',
    count: 2, years: [2025,2025],
    papers: [
      { t: 'Advancing Qualitative Analysis in Disaster Communication', s: '2025-01-01-advancing-qualitative-analysis-in-professional-disaster-and-risk-communication-a' },
      { t: 'Advancing Qualitative Analysis in Disaster Communication', s: '2025-01-01-advancing-qualitative-analysis-in-professional-disaster-and-risk-communication-a' },
    ]
  },
  'Katz': {
    full: 'Andrew Katz',
    uni: 'Virginia Tech', discipline: 'Engineering Education',
    count: 1, years: [2025],
    papers: [
      { t: 'Advancing Qualitative Analysis in Disaster Communication', s: '2025-01-01-advancing-qualitative-analysis-in-professional-disaster-and-risk-communication-a' },
    ]
  },
  'Inman': {
    full: 'Rachel Inman',
    uni: 'Virginia Tech', discipline: 'Engineering Education',
    count: 1, years: [2025],
    papers: [
      { t: 'Advancing Qualitative Analysis in Disaster Communication', s: '2025-01-01-advancing-qualitative-analysis-in-professional-disaster-and-risk-communication-a' },
    ]
  },
  'Bose': {
    full: 'Baisakhi Bose',
    uni: 'Virginia Tech', discipline: 'Engineering Education',
    count: 1, years: [2023],
    papers: [
      { t: 'Graduate Student Perspectives on Gender Equity', s: '2023-01-01-graduate-student-and-postdoctoral-fellow-perspectives-on-advancing-women-and-gen' },
    ]
  },
  'Jaramillo': {
    full: 'Jonathan Jaramillo',
    uni: 'Cornell University', discipline: 'Electrical & Computer Engineering',
    count: 1, years: [2026],
    papers: [
      { t: 'Strategies for Hybrid Hands-on Courses', s: '2026-01-01-strategies-for-hybrid-hands-on-courses-in-robotics-embedded-systems-and-iot' },
    ]
  },
  'Schiebel': {
    full: 'Johannes Schiebel',
    uni: 'Otto-von-Guericke-Universität Magdeburg', discipline: 'Engineering Education',
    count: 1, years: [2027],
    papers: [
      { t: 'Hidden Curriculum of a PhD in EER', s: '2026-01-01-hidden-curriculum' },
    ]
  },
  'Hingle': {
    full: 'Ashish Hingle',
    uni: 'Cal Poly', discipline: 'Engineering Education',
    count: 1, years: [2027],
    papers: [
      { t: 'Hidden Curriculum of a PhD in EER', s: '2026-01-01-hidden-curriculum' },
    ]
  },
  'Smith': {
    full: 'Alexa Smith',
    uni: 'Virginia Tech', discipline: 'Technical Communication',
    count: 1, years: [2026],
    papers: [
      { t: 'U.S. Hospital Educators\' Technology Needs', s: '2026-01-01-understanding-virginia-us-hospital-educators-work-practices-and-technology-needs_copy' },
    ]
  },
  'Williams': {
    full: 'Ihudiya Williams',
    uni: 'Virginia Tech', discipline: 'Technical Communication',
    count: 1, years: [2026],
    papers: [
      { t: 'U.S. Hospital Educators\' Technology Needs', s: '2026-01-01-understanding-virginia-us-hospital-educators-work-practices-and-technology-needs_copy' },
    ]
  },
};

var allEdgeIds = Object.keys(collabs);

/* ── helpers ── */
function isDark(){ return matchMedia('(prefers-color-scheme:dark)').matches; }
function netColor(c){ return c>=3?'#2a78d6':c===2?'#1baf7a':'#aaaaaa'; }
function netR(c){ return 7+Math.min(c,8)*2.5; }
function hexRGB(h){ return [parseInt(h.slice(1,3),16),parseInt(h.slice(3,5),16),parseInt(h.slice(5,7),16)]; }

/* ── shared tooltip ── */
var tip = null;
function showTip(e, html){
  if(!tip) tip=document.getElementById('rvis-tip');
  tip.innerHTML = html;
  tip.style.display = 'block';
  moveTip(e);
}
function moveTip(e){
  if(!tip||tip.style.display==='none') return;
  var x=e.clientX+16, y=e.clientY-10;
  var tw=tip.offsetWidth||230, th=tip.offsetHeight||120;
  if(x+tw>window.innerWidth-10) x=e.clientX-tw-10;
  if(y+th>window.innerHeight-10) y=window.innerHeight-th-10;
  tip.style.left=x+'px'; tip.style.top=y+'px';
}
function hideTip(){ if(tip) tip.style.display='none'; }

function tipHTML(id){
  var d = collabs[id];
  if(!d) return '';
  var uniquePapers = [];
  var seen = {};
  d.papers.forEach(function(p){ if(!seen[p.s]){ seen[p.s]=true; uniquePapers.push(p); } });
  var yrs = d.years.filter(function(v,i,a){return a.indexOf(v)===i;}).sort().join(', ');
  var links = uniquePapers.map(function(p){
    return '<a href="'+BASE+p.s+'" target="_blank">↗ '+p.t+'</a>';
  }).join('');
  return '<div class="tip-name">'+d.full+'</div>'
       + '<div class="tip-uni">'+d.uni+'</div>'
       + '<div class="tip-disc">'+d.discipline+'</div>'
       + '<div class="tip-stat">'+d.count+' paper'+(d.count>1?'s':'')+' · '+yrs+'</div>'
       + '<div class="tip-pubs">'+links+'</div>';
}

/* ══════════════════════════════════════════
   NETWORK
   ══════════════════════════════════════════ */
var NC,NX,NW,NH,Nds,Nls,NF='all',NDrag=null;

function filterEdgeIds(f){
  if(f==='frequent') return allEdgeIds.filter(function(id){return collabs[id].count>=3;});
  if(f==='recent')   return allEdgeIds.filter(function(id){return collabs[id].years.some(function(y){return y>=2024;});});
  return allEdgeIds;
}

function netInit(){
  var ids = filterEdgeIds(NF);
  NW = NC.offsetWidth||680;
  NH = Math.max(360,Math.min(480,NW*0.58));
  NC.width=NW*(window.devicePixelRatio||1); NC.height=NH*(window.devicePixelRatio||1);
  NC.style.height=NH+'px';
  NX.setTransform(1,0,0,1,0,0); NX.scale(window.devicePixelRatio||1,window.devicePixelRatio||1);

  Nds=[{id:'Webb',count:0,fx:NW/2,fy:NH/2,x:NW/2,y:NH/2,vx:0,vy:0}];
  var n=ids.length;
  ids.forEach(function(id,i){
    var a=(i/n)*2*Math.PI, r=Math.min(NW,NH)*0.32, c=collabs[id];
    Nds.push({id:id,count:c.count,years:c.years,x:NW/2+r*Math.cos(a),y:NH/2+r*Math.sin(a),vx:0,vy:0});
  });
  Nls=ids.map(function(id){return{s:'Webb',t:id,count:collabs[id].count};});
  for(var i=0;i<180;i++) netF();
}

function netF(){
  var cx=NW/2,cy=NH/2;
  Nds.forEach(function(n){n.vx*=0.85;n.vy*=0.85;});
  Nds.forEach(function(n){if(n.fx!=null)return;n.vx+=(cx-n.x)*0.004;n.vy+=(cy-n.y)*0.004;});
  for(var i=0;i<Nds.length;i++) for(var j=i+1;j<Nds.length;j++){
    var a=Nds[i],b=Nds[j],dx=b.x-a.x,dy=b.y-a.y,d=Math.sqrt(dx*dx+dy*dy)||1,mn=86;
    if(d<mn){var f=(mn-d)/d*0.28;if(a.fx==null){a.vx-=dx*f;a.vy-=dy*f;}if(b.fx==null){b.vx+=dx*f;b.vy+=dy*f;}}
  }
  Nls.forEach(function(lk){
    var s=Nds.find(function(n){return n.id===lk.s;}),t=Nds.find(function(n){return n.id===lk.t;});
    if(!s||!t) return;
    var dx=t.x-s.x,dy=t.y-s.y,d=Math.sqrt(dx*dx+dy*dy)||1,tg=140+lk.count*8,f=(d-tg)/d*0.05;
    if(s.fx==null){s.vx+=dx*f;s.vy+=dy*f;} if(t.fx==null){t.vx-=dx*f;t.vy-=dy*f;}
  });
  Nds.forEach(function(n){
    if(n.fx!=null){n.x=n.fx;n.y=n.fy;return;}
    n.x+=n.vx;n.y+=n.vy;
    var p=36;n.x=Math.max(p,Math.min(NW-p,n.x));n.y=Math.max(p,Math.min(NH-p,n.y));
  });
}

function netDraw(){
  NX.clearRect(0,0,NW,NH);
  var dark=isDark();
  Nls.forEach(function(lk){
    var s=Nds.find(function(n){return n.id===lk.s;}),t=Nds.find(function(n){return n.id===lk.t;});
    if(!s||!t) return;
    var rgb=hexRGB(netColor(lk.count));
    NX.beginPath();NX.moveTo(s.x,s.y);NX.lineTo(t.x,t.y);
    NX.strokeStyle='rgba('+rgb[0]+','+rgb[1]+','+rgb[2]+',0.33)';
    NX.lineWidth=0.8+lk.count*0.4; NX.stroke();
  });
  Nds.forEach(function(nd){
    var isY=nd.id==='Webb',r=isY?20:netR(nd.count||1),col=isY?'#EF9F27':netColor(nd.count||1);
    NX.beginPath();NX.arc(nd.x,nd.y,r,0,Math.PI*2);
    NX.globalAlpha=0.9;NX.fillStyle=col;NX.fill();NX.globalAlpha=1;
    NX.strokeStyle=dark?'rgba(255,255,255,0.2)':'rgba(255,255,255,0.85)';NX.lineWidth=1.5;NX.stroke();
    NX.fillStyle='#fff';
    NX.font=(isY?'600 11px':'500 10px')+' system-ui,sans-serif';
    NX.textAlign='center';NX.textBaseline='middle';
    var label=isY?'You':nd.id;
    if(r>=14||isY){ NX.fillText(label,nd.x,nd.y); }
    else{ NX.fillStyle=dark?'rgba(220,220,215,0.9)':'rgba(30,30,28,0.85)';NX.font='400 10px system-ui,sans-serif';NX.fillText(label,nd.x,nd.y+r+9); }
  });
}

function netHit(mx,my){
  return Nds.find(function(nd){var r=nd.id==='Webb'?20:netR(nd.count||1),dx=mx-nd.x,dy=my-nd.y;return Math.sqrt(dx*dx+dy*dy)<r+6;});
}

window.rvNetFilter=function(f,btn){
  NF=f;
  btn.closest('.rvis-filters').querySelectorAll('button').forEach(function(b){b.classList.remove('active');});
  btn.classList.add('active');
  Nds[0].fx=null;Nds[0].fy=null;
  netInit(); Nds[0].fx=NW/2;Nds[0].fy=NH/2;
};


<!-- ============================================================
     KEYWORD BUBBLES
     ============================================================ -->
/* ══════════════════════════════════════════
   KEYWORD BUBBLES
   ══════════════════════════════════════════ */
var PUB = 'https://webbmargaret.github.io/publications/';

var keywords=[
  {text:'interdisciplinary education',size:22,cat:'systems',  url:PUB, desc:'Core to dissertation & 8+ papers on how graduate students develop across fields'},
  {text:'ecological systems',          size:17,cat:'systems',  url:PUB, desc:'Bronfenbrenner\'s theory applied to engineering grad education across 5+ papers'},
  {text:'graduate education',          size:18,cat:'systems',  url:PUB, desc:'Primary context for research on identity, motivation, and structural change'},
  {text:'STEM systems',                size:12,cat:'systems',  url:PUB, desc:'How institutional structures collectively shape student development'},
  {text:'university structures',       size:11,cat:'systems',  url:PUB, desc:'Breaking Silos & Beyond Barriers — policy-level systemic change'},
  {text:'professional identity',       size:16,cat:'identity', url:PUB, desc:'How engineering students develop sense of self across interdisciplinary contexts'},
  {text:'identity-based motivation',   size:15,cat:'identity', url:PUB, desc:'Theoretical framework in dissertation; longitudinal tracking across 4+ papers'},
  {text:'displaced engineers',         size:11,cat:'identity', url:PUB, desc:'Scoping review & FIE paper on forced migration and engineering identity'},
  {text:'gender equity',               size:10,cat:'identity', url:PUB, desc:'ASEE 2023 paper on advancing women & gender equity in engineering'},
  {text:'refugee & immigrant communities',size:13,cat:'digital',url:PUB, desc:'Participatory design with resettled communities in Virginia'},
  {text:'digital justice',             size:14,cat:'digital',  url:PUB, desc:'3+ papers on technology & equity, incl. community writing conferences'},
  {text:'community-centered design',   size:12,cat:'digital',  url:PUB, desc:'Designing Technology with Justice book chapter; participatory methods'},
  {text:'information architecture',    size:10,cat:'digital',  url:PUB, desc:'Computers & Composition paper on refugee service digital infrastructure'},
  {text:'hospital educators',          size:9, cat:'digital',  url:PUB, desc:'IEEE TPC qualitative case study on AI integration opportunities'},
  {text:'GenAI in research',           size:13,cat:'methods',  url:PUB, desc:'Using LLMs for qualitative coding — 2025 disaster risk paper & 2027 SEE journal'},
  {text:'qualitative methods',         size:15,cat:'methods',  url:PUB, desc:'Foundational approach across nearly all studies; interview, document analysis'},
  {text:'reflective practice',         size:12,cat:'methods',  url:PUB, desc:'Scaling reflection quality assessment with GenAI & codebook validation papers'},
  {text:'codebook validation',         size:10,cat:'methods',  url:PUB, desc:'2026 ASEE & 2027 SEE papers on comparing approaches to coding reliability'},
  {text:'longitudinal research',       size:11,cat:'methods',  url:PUB, desc:'Multi-year tracking of identity-based motivation in engineering grad students'},
  {text:'research fiction',            size:9, cat:'methods',  url:PUB, desc:'Novel GenAI-enabled method for multi-perspective scholarly insight (ASEE 2026)'},
  {text:'DBER postdocs',               size:14,cat:'postdoc',  url:PUB, desc:'Three 2026–2027 papers on how postdocs build agency for instructional change'},
  {text:'instructional change',        size:12,cat:'postdoc',  url:PUB, desc:'Conceptual framework & empirical studies on change leadership in STEM ed'},
  {text:'faculty development',         size:11,cat:'postdoc',  url:PUB, desc:'Bidirectional learning between postdocs and faculty supervisors'},
  {text:'professional agency',         size:11,cat:'postdoc',  url:PUB, desc:'Cycles of recognition: how DBER postdocs accumulate (or fail to build) agency'},
  {text:'dyadic learning',             size:9, cat:'postdoc',  url:PUB, desc:'Beyond the Individual: agency as property of the postdoc-faculty interaction'},
];

var catColors={systems:'#2a78d6',identity:'#1baf7a',digital:'#e87ba4',methods:'#4a3aa7',postdoc:'#eda100'};
var KC,KX,KW,KH,KBubs,KF='all';

function kwInit(){
  KW=KC.offsetWidth||680; KH=Math.max(340,Math.min(440,KW*0.58));
  KC.width=KW*(window.devicePixelRatio||1); KC.height=KH*(window.devicePixelRatio||1);
  KC.style.height=KH+'px';
  KX.setTransform(1,0,0,1,0,0); KX.scale(window.devicePixelRatio||1,window.devicePixelRatio||1);
  var sizes=keywords.map(function(k){return k.size;}),maxS=Math.max.apply(null,sizes),minS=Math.min.apply(null,sizes);
  KBubs=keywords.map(function(kw,i){
    var r=18+((kw.size-minS)/(maxS-minS))*40,a=(i/keywords.length)*2*Math.PI,dist=80+Math.random()*110;
    return Object.assign({},kw,{r:r,x:KW/2+dist*Math.cos(a),y:KH/2+dist*Math.sin(a),vx:(Math.random()-0.5)*0.3,vy:(Math.random()-0.5)*0.3,opacity:1,tOp:1});
  });
  for(var i=0;i<220;i++) kwF();
}

function kwF(){
  var cx=KW/2,cy=KH/2;
  KBubs.forEach(function(b){b.vx*=0.88;b.vy*=0.88;b.vx+=(cx-b.x)*0.003;b.vy+=(cy-b.y)*0.003;});
  for(var i=0;i<KBubs.length;i++) for(var j=i+1;j<KBubs.length;j++){
    var a=KBubs[i],b=KBubs[j],dx=b.x-a.x,dy=b.y-a.y,d=Math.sqrt(dx*dx+dy*dy)||0.1,mn=a.r+b.r+6;
    if(d<mn){var f=(mn-d)/d*0.25;a.vx-=dx*f;a.vy-=dy*f;b.vx+=dx*f;b.vy+=dy*f;}
  }
  KBubs.forEach(function(b){
    b.x+=b.vx;b.y+=b.vy;
    var p=b.r+8;b.x=Math.max(p,Math.min(KW-p,b.x));b.y=Math.max(p,Math.min(KH-p,b.y));
    b.opacity+=(b.tOp-b.opacity)*0.1;
  });
}

function kwDraw(){
  KX.clearRect(0,0,KW,KH);
  var dark=isDark();
  KBubs.forEach(function(b){
    KX.globalAlpha=b.opacity*0.88;KX.beginPath();KX.arc(b.x,b.y,b.r,0,Math.PI*2);
    KX.fillStyle=catColors[b.cat];KX.fill();
    KX.globalAlpha=b.opacity;
    KX.strokeStyle=dark?'rgba(255,255,255,0.15)':'rgba(255,255,255,0.65)';KX.lineWidth=1;KX.stroke();
    if(b.opacity>0.3){
      KX.fillStyle='#fff';KX.textAlign='center';KX.textBaseline='middle';
      var words=b.text.split(' '),fs=Math.max(9,Math.min(11,b.r*0.37));
      KX.font='500 '+fs+'px system-ui,sans-serif';
      if(words.length===1||b.r<24){ KX.fillText(b.text,b.x,b.y); }
      else if(words.length===2){ KX.fillText(words[0],b.x,b.y-fs*0.62);KX.fillText(words[1],b.x,b.y+fs*0.62); }
      else{ var m=Math.ceil(words.length/2);KX.fillText(words.slice(0,m).join(' '),b.x,b.y-fs*0.65);KX.fillText(words.slice(m).join(' '),b.x,b.y+fs*0.65); }
    }
  });
  KX.globalAlpha=1;
}

function kwHit(mx,my){ return KBubs.find(function(b){var dx=mx-b.x,dy=my-b.y;return Math.sqrt(dx*dx+dy*dy)<b.r+4;}); }

window.rvKwFilter=function(cat,btn){
  KF=cat;
  btn.closest('.rvis-filters').querySelectorAll('button').forEach(function(b){b.classList.remove('active');});
  btn.classList.add('active');
  KBubs.forEach(function(b){b.tOp=(cat==='all'||b.cat===cat)?1:0.15;});
};

/* ── boot ── */
document.addEventListener('DOMContentLoaded',function(){
  tip = document.getElementById('rvis-tip');

  /* --- network --- */
  NC=document.getElementById('rvNetCanvas'); NX=NC.getContext('2d');
  netInit(); Nds[0].fx=NW/2; Nds[0].fy=NH/2;
  (function nl(){netF();netDraw();requestAnimationFrame(nl);})();

  NC.addEventListener('mousemove',function(e){
    var rect=NC.getBoundingClientRect(),mx=e.clientX-rect.left,my=e.clientY-rect.top,hit=netHit(mx,my);
    if(hit){
      NC.style.cursor='pointer';
      if(hit.id==='Webb'){
        showTip(e,'<div class="tip-name">Margaret E.B. Webb</div><div class="tip-stat">'+allEdgeIds.length+' collaborators across journal, conference &amp; book publications</div>');
      } else {
        showTip(e, tipHTML(hit.id));
      }
    } else { NC.style.cursor='default'; hideTip(); }
    moveTip(e);
    if(NDrag){NDrag.fx=mx;NDrag.fy=my;NDrag.x=mx;NDrag.y=my;}
  });
  NC.addEventListener('mousedown',function(e){
    var rect=NC.getBoundingClientRect(),hit=netHit(e.clientX-rect.left,e.clientY-rect.top);
    if(hit&&hit.id!=='Webb'){NDrag=hit;hit.fx=e.clientX-rect.left;hit.fy=e.clientY-rect.top;}
  });
  NC.addEventListener('mouseup',function(){if(NDrag){NDrag.fx=null;NDrag.fy=null;NDrag=null;}});
  NC.addEventListener('mouseleave',function(){hideTip();if(NDrag){NDrag.fx=null;NDrag.fy=null;NDrag=null;}});
  NC.addEventListener('click',function(e){
    if(NDrag) return;
    var rect=NC.getBoundingClientRect(),hit=netHit(e.clientX-rect.left,e.clientY-rect.top);
    if(hit&&hit.id!=='Webb'&&collabs[hit.id]&&collabs[hit.id].papers.length>0){
      var p=collabs[hit.id].papers[0];
      window.open(BASE+p.s,'_blank');
    }
  });

  /* --- bubbles --- */
  KC=document.getElementById('rvKwCanvas'); KX=KC.getContext('2d');
  kwInit();
  (function kl(){kwF();kwDraw();requestAnimationFrame(kl);})();

  KC.addEventListener('mousemove',function(e){
    var rect=KC.getBoundingClientRect(),mx=e.clientX-rect.left,my=e.clientY-rect.top,hit=kwHit(mx,my);
    if(hit){
      KC.style.cursor='pointer';
      showTip(e,'<div class="tip-name">'+hit.text+'</div><div class="tip-stat">'+hit.desc+'</div><div class="tip-pubs"><a href="'+PUB+'" target="_blank">↗ Browse all publications</a></div>');
    } else { KC.style.cursor='default'; hideTip(); }
    moveTip(e);
  });
  KC.addEventListener('mouseleave',function(){hideTip();});
  KC.addEventListener('click',function(e){
    var rect=KC.getBoundingClientRect(),hit=kwHit(e.clientX-rect.left,e.clientY-rect.top);
    if(hit) window.open(PUB,'_blank');
  });
});

})();
</script>

---

### Why is it hard for students and professors to work across different fields?

**The problem:** Universities are organized into separate departments (mechanical 
engineering, biology, etc.). When students try to work across these boundaries — 
which is exactly what solving complex problems requires — they face hidden obstacles.

**What I've found:** It's not enough to just create "interdisciplinary programs" 
and drop them into existing university structures. The whole system fights against 
it — from how professors get promoted, to how funding works, to how departments are 
managed. My [dissertation](https://webbmargaret.github.io/publication/2025-01-01-systems-to-transform-interdisciplinary-graduate-education-an-ecological-systems) 
mapped out 12 specific university "systems" (like funding, departments, and research 
labs) that either help or hurt students trying to become interdisciplinary researchers.

**Why it matters:** My award-winning research shows these systems need to change 
together, not one at a time. Work like 
[*Breaking Silos*](https://webbmargaret.github.io/publication/2024-01-01-breaking-silos-rethinking-university-structures-to-facilitate-interdisciplinary) 
and [*Navigating (Inter)disciplinary Systems*](https://webbmargaret.github.io/publication/2025-01-01-navigating-interdisciplinary-systems-ecological-systems-analysis-of-engineering) 
demonstrates how entrenched structures shape whether students can develop 
interdisciplinary identities — and what universities would need to change to actually 
support them. I'm now studying how postdoctoral researchers — who are supposed to 
drive innovation from their research — navigate similar tensions in complex educational 
systems (see [*Beyond Barriers and Supports*](https://webbmargaret.github.io/publication/2026-01-01-beyond-barriers-and-supports-a-systems-interaction-analysis-of-how-microsystems), in review).

This strand also extends to how marginalized students experience interdisciplinary 
spaces. Ongoing work with colleagues examines how graduate students from underrepresented 
groups develop resilience and self-authorship when navigating these systems — and what 
it would take to make those spaces genuinely equitable (see [*Rethinking Self-Authorship 
Through Critical Resilience Theory*](https://webbmargaret.github.io/publication/2027-01-01-rethinking-self-authorship-through-critical-resilience-theory), in progress).


---

### How can we study education better and at scale, without losing quality?

**The problem:** To understand big and complex educational problems, researchers 
often need to analyze massive amounts of data from many students over long periods 
and draw connections between them. Traditional qualitative research methods are 
thorough, but they can be slow and do not always lend themselves toward visualization 
and systems-level analysis.

**What I've found:**

- **Using GenAI thoughtfully for systems-level analysis:** I've helped develop methods where AI enables the 
  analysis of student reflections and other open responses at massive scale, but 
  humans stay in control to ensure quality. Critically, scaling up qualitative analysis this way opens doors that were previously impractical — enabling multi-institutional and cross-cultural comparisons, longitudinal studies across larger cohorts, and findings with broader generalizability than traditional qualitative work alone can achieve. Without this kind of scale, systems-level questions about how universities shape student development are nearly impossible to answer rigorously. See [*Advancing Qualitative Analysis in Professional Disaster and Risk Communication*](https://webbmargaret.github.io/publication/2025-01-01-advancing-qualitative-analysis-in-professional-disaster-and-risk-communication-a) and [*Toward Scalable Assessment of Undergraduate Reflective Practice*](https://webbmargaret.github.io/publication/2026-01-01-toward-scalable-assessment-of-undergraduate-reflective-practice) (forthcoming).

  But scaling up GenAI-enabled coding isn't straightforward. Our ongoing work shows 
  that the type of code being applied matters enormously — surface-level content codes 
  behave very differently from deeper interpretive codes when automated, and standard 
  interrater agreement metrics don't always tell the full story. See [*Scaling Reflection 
  Quality Assessment with GenAI: Code Type, Dataset Balancing, and the Limits of 
  Interrater Agreement in EER*](https://webbmargaret.github.io/publication/2027-01-01-scaling-reflection-quality-assessment-genai-code-type) 
  (in progress), which challenges the common assumption that latent codes are simply 
  "harder" for AI to handle.

- **Visualizing complex qualitative data:** Understanding how systems interact over 
  time requires more than written analysis — it requires making invisible patterns 
  visible. I've developed visualization techniques for longitudinal qualitative data 
  that show how students' identities and motivations shift across time and in response 
  to different institutional systems. This work, first developed in my 
  [dissertation](https://webbmargaret.github.io/publication/2025-01-01-systems-to-transform-interdisciplinary-graduate-education-an-ecological-systems) and extended in an upcoming article in the 
  [*Journal of Engineering Education*](https://webbmargaret.github.io/publication/2026-01-01-beyond-barriers-and-supports-a-systems-interaction-analysis-of-how-microsystems), is now being applied to postdoctoral professional development — where visualizing 
  how postdocs navigate critical tensions across complex academic relationships can 
  make those patterns legible in ways that can actually inform program design. An 
  upcoming article in [*Studies in Graduate and Postdoctoral Education*](https://webbmargaret.github.io/publication/2027-01-01-visualizing-interdisciplinary-scholar-development) extends this 
  visualization work to trace how students' interdisciplinary motivation trajectories 
  evolve across the full arc of graduate training (in progress).

- **Community-partnership research:** Instead of researchers designing technology 
  for communities, I work *with* communities — refugees, immigrants, hospital 
  educators — to co-create solutions through participatory action research. For 
  example, I've helped develop a citizenship study app based on what refugee 
  communities actually needed, not what researchers might assume they needed. See 
  [*Reimagining Information Architecture*](https://webbmargaret.github.io/publication/2025-01-01-towards-digital-justice-and-consolidated-resettlement-resources-for-new-american) 
  and [*Incorporating Community Knowledge in Design*](https://webbmargaret.github.io/publication/2025-01-01-incorporating-community-knowledge-in-design-a-reflective-account-of-designing-te).

  Here is our prototype [citizenship study app](https://apps.apple.com/us/app/100-uscis-civics-questions/id6478173322).

---

### How do we actually create change in engineering education?

**The problem:** Knowing what works in teaching isn't the same as getting professors 
to adopt it. Change is hard.

**What I study:**

- **How postdocs can drive change:** Postdocs are positioned to innovate in higher 
  education as new experts in their disciplines, but they face tensions — like unclear 
  expectations from the faculty they work with. I've been developing a framework to 
  help them navigate these challenges. See [*Building Capacity for Instructional 
  Change*](https://webbmargaret.github.io/publication/2026-01-01-building-capacity-for-instructional-change-dber-postdoctoral-professional-development) 
  (forthcoming).

- **Critical tensions and how postdocs build agency:** My team has found that 
  productive struggle is necessary for postdocs' growth. "Critical tensions" are 
  challenging situations — like when a postdoc's vision for innovative teaching 
  conflicts with their supervising professor's expectations — that feel uncomfortable 
  but are actually essential learning moments. Rather than trying to eliminate these 
  tensions, our research helps define what they are and how they can be navigated, 
  as well as how to design professional development that recognizes them as 
  opportunities for growth. See [*Building Capacity for Instructional 
  Change*](https://webbmargaret.github.io/publication/2026-01-01-building-capacity-for-instructional-change-dber-postdoctoral-professional-development) 
  (forthcoming).

  Importantly, how a postdoc responds to these tensions — and whether those responses 
  accumulate into genuine agency — is not just an individual matter. Our research 
  identifies five archetypical patterns of how postdocs build professional agency 
  over time, showing that the same person may follow different patterns depending on 
  their relational and institutional environment. See [*Cycles of Recognition: How 
  DBER Postdocs Build Professional Agency for Instructional Change with Five 
  Archetypical Patterns*](https://webbmargaret.github.io/publication/2027-01-01-cycles-of-recognition-dber-postdocs-professional-agency) 
  (in progress).

  This work also reveals that agency development is not just a property of the 
  individual postdoc — it emerges from the postdoc-faculty relationship itself. When 
  both parties learn from each other, productive outcomes follow; when that 
  bidirectional learning breaks down, labor happens but agency doesn't build. See 
  [*Beyond the Individual: Bidirectional Learning and Dyadic Agency Development in 
  DBER Postdoc–Faculty Collaborations for Instructional Change*](https://webbmargaret.github.io/publication/2027-01-01-beyond-the-individual-bidirectional-learning-dyadic-agency) 
  (in progress).

  We've also been developing a method for surfacing these tensions 
  using research fiction — fictionalized case studies that protect participants' 
  identities while enabling honest discussion of difficult relational dynamics. 
  GenAI plays a role here too, helping generate synthetic vignettes that can be 
  discussed, refined, and used in professional development settings. See 
  [*Generative Stories Generating Research Insight*](https://webbmargaret.github.io/publication/2026-01-01-generative-stories-generating-research-insight-genai-enabled-research-fiction).

- **Practical teaching innovations:** I've also been studying how to teach hands-on 
  engineering courses online without losing the hands-on part — especially important 
  for working professionals who can't be on campus. See [*Strategies for Hybrid, 
  Hands-on Courses in Robotics, Embedded Systems, and IoT*](https://webbmargaret.github.io/publication/2026-01-01-strategies-for-hybrid-hands-on-courses-in-robotics-embedded-systems-and-iot) 
  (forthcoming).

---