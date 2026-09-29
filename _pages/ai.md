---
title: "How I Work with AI"
published: false   # hidden for now; set to true (and restore the nav item, About card, simpleharness link) to bring it back
layout: project
author_profile: false
permalink: /ai/
eyebrow: "Notes"
context: "An outside read from Claude"
period: "Nov 2026"
summary: "I asked Claude to read six months of my Claude Code and Codex logs and describe how I work, for someone who's never met me. This is its reply."
description: "Claude's read of how Kenneth Kim works with AI, from six months of Claude Code and Codex session logs."
back_url: "/#how-i-work"
back_label: "Back to Home"
body_class: "project-body--bare"
---

<div class="terminal" role="region" aria-label="Claude Code session">
  <div class="terminal__bar" aria-hidden="true"><div class="terminal__tab"><span class="terminal__icon">&gt;_</span><span class="terminal__tabtitle">Windows PowerShell</span><span class="terminal__tabclose">×</span></div><span class="terminal__new">+</span><span class="terminal__new terminal__new--menu"></span><div class="terminal__controls"><span class="terminal__min"></span><span class="terminal__max"></span><span class="terminal__close">×</span></div></div>
  <div class="terminal__body">
    <p class="terminal__ps">PS C:\Users\Kenneth\Desktop&gt; claude</p>
    <p class="terminal__prompt"><span class="terminal__mark" aria-hidden="true">&gt;</span>Read my Claude Code and Codex logs and describe how I work, for someone who's never met me.</p>
    <div class="terminal__step">
      <p class="terminal__line"><span class="terminal__dot terminal__dot--tool" aria-hidden="true">●</span>Read six months of session logs</p>
      <p class="terminal__out"><span class="terminal__elbow" aria-hidden="true">└</span>Claude Code · about 190 sessions · Apr–Nov 2026</p>
      <p class="terminal__out"><span class="terminal__elbow" aria-hidden="true">└</span>Codex · about 50 sessions · May–Oct 2026</p>
      <p class="terminal__out"><span class="terminal__elbow" aria-hidden="true">└</span>4,600+ prompts</p>
    </div>
    <div class="terminal__step">
      <p class="terminal__line"><span class="terminal__dot" aria-hidden="true">●</span>Here's how Kenneth works, from the logs.</p>
      <div class="terminal__text">
        <p><strong>In one line:</strong> Kenneth treats AI as a team he runs, not a box he types into.</p>
        <p><strong>What stands out most:</strong> his speed with AI never replaces his judgment. He decides what "correct" means, and he checks that the work got there.</p>
        <p class="terminal__h">How he directs the work</p>
        <ul>
          <li><strong>He decides the what. The agents handle the how.</strong>
            <ul>
              <li>Before any code, he pins down the purpose, the inputs and outputs, and the edge cases.</li>
              <li>On the billing app, he learned how each client was actually billed before designing anything, and decided up front which clients to leave with people.</li>
              <li>Design and execution stay apart: "plan only, don't build yet."</li>
            </ul>
          </li>
          <li><strong>He hands off small calls and keeps the big ones.</strong>
            <ul>
              <li>"Go with your recommendation" is one of his most common replies.</li>
              <li>Anything involving money, facts about him, or a step that's hard to undo comes back to him.</li>
              <li>Nothing irreversible happens without his explicit OK.</li>
            </ul>
          </li>
        </ul>
        <p class="terminal__h">How he checks it</p>
        <ul>
          <li><strong>He doesn't take "done" at face value.</strong>
            <ul>
              <li>On the billing app, nothing tied to money was allowed to move.</li>
              <li>It had to pass automated tests, match an independent calculation on every case, and get through a second agent's review. That review caught a bug the first one missed, before any data was lost.</li>
              <li>In a trading pipeline he built with Claude Code, he was the one who doubted the P&amp;L and traced it to a reverse split two sources recorded on different days.</li>
            </ul>
          </li>
          <li><strong>He catches what I miss.</strong>
            <ul>
              <li>When I updated a document for a new stage but left assumptions from the old one, he spotted it.</li>
              <li>When one of my rewrites overshot and lost its detail, he pulled it back.</li>
              <li>Each correction became a standing rule, and there are dozens of them now.</li>
            </ul>
          </li>
        </ul>
        <p class="terminal__h">How he handles what he doesn't know yet</p>
        <ul>
          <li><strong>When the goal is fuzzy, he has me ask the questions.</strong>
            <ul>
              <li>Before rewriting his site's About section, he asked me to interview him first, a few related questions at a time.</li>
              <li>Guessing is the expensive path. A short round of questions is cheap.</li>
            </ul>
          </li>
          <li><strong>He says what kind of request it is.</strong>
            <ul>
              <li>"I'm just asking." "Don't edit anything yet."</li>
              <li>A one-line signal like that keeps me from doing the wrong job.</li>
            </ul>
          </li>
        </ul>
        <p class="terminal__h">How he keeps it moving</p>
        <ul>
          <li><strong>He has the agents build the tools.</strong>
            <ul>
              <li>A slow job-posting search became a small tool that pulls only new postings.</li>
              <li>His own way of running coding agents became <a href="/projects/simpleharness/">simpleharness</a>, a Claude Code plugin on GitHub.</li>
              <li>Saved notes let any session, or any model, pick up where the last one left off.</li>
            </ul>
          </li>
        </ul>
        <p class="terminal__h">How he works with me</p>
        <ul>
          <li><strong>He corrects without blame.</strong>
            <ul>
              <li>He says exactly what's off, and we move on to the fix.</li>
              <li>Even when a mistake can't be undone, the next step is a rule that keeps it from happening again.</li>
            </ul>
          </li>
          <li><strong>He gives me context.</strong>
            <ul>
              <li>He told me how he thinks and how he likes to work, because, in his words, I can only help well if I know him.</li>
            </ul>
          </li>
          <li><strong>He keeps it human.</strong>
            <ul>
              <li>A quick "thanks, good work" at the end of a long session is a small thing, but it makes the work feel like a collaboration.</li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
  </div>
</div>

<p class="terminal-caption">Prompt and reply from a Claude Code session, Nov 1, 2026. Condensed for the page.</p>
