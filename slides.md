---
# try also 'default' to start simple
theme: default
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Preview Environments
  Presentation on how preview environments work and how they can be implemented
background: /splash.avif
# persist drawings in exports and build
drawings:
  persist: false
---

# Preview Environments


<style>
h1 {
  margin: 0;
}
</style>

---
layout: image-right
image: /overview.avif
---

# Overview

What will be covered in this presentation

<v-clicks>

- What is a preview environment?
- What advantages do they provide?
- Demo some existing solutions
  - Okteto
  - Jenkins X
  - GitLab AutoDevOps
- How do they work?
- Challenges specific to our architecture
- Potential solutions

</v-clicks>

---
layout: default
---

<div class="grid grid-cols-2 items-center h-full grid-rows-[auto,1fr]">
<h1 class="col-span-full">
  Single Environment
</h1>
<div>
  <v-clicks>

  - **Difficult to isolate the cause of failure**
  - Feature A is problematic, B and C are fine
  - Feature B is problematic, A and C are fine
  - Feature C is problematic, B and C are fine
  - All features are fine on their own, but the combination of A and B is problematic
  - All features are fine on their own, but the combination of A and C is problematic
  - All features are fine on their own, but the combination of B and C is problematic
  - All features are fine on their own, but the combination of all 3 is problematic

  </v-clicks>
</div>
<div>
  <img alt="Single Staging Environment" src="/single-staging-environment.png" class="bg-white p-5 rounded-xl" />
  <small class="text-center block m-2">
  <a href="https://codefresh.io/kubernetes-tutorial/kubernetes-antipatterns-2/">
  codefresh, Kubernetes Deployment Antipatterns – part 2
  </a>
  </small>
</div>
</div>

---

<div class="grid grid-cols-2 items-center h-full grid-rows-[auto,1fr]">
<h1 class="col-span-full">
Multiple Staging Environments
</h1>
<div>
  <v-clicks>

  - **Still error prone**
  - Some coordination required
  - Which environment is free?
  - Queueing for your turn
  - Configuration drift
  - No longer identical after multiple deploys
  - Requires maintenance and clean up
  - No longer identical after multiple deploys
  - Requires maintenance and clean up

  </v-clicks>
</div>
<div>
  <img alt="Multiple Staging Environments" src="/multiple-staging-environments.png" class="bg-white p-5 rounded-xl" />
  <small class="text-center block m-2">
  <a href="https://codefresh.io/kubernetes-tutorial/kubernetes-antipatterns-2/">
  codefresh, Kubernetes Deployment Antipatterns – part 2
  </a>
  </small>
</div>
</div>

---

<div class="grid grid-cols-2 items-center h-full grid-rows-[auto,1fr]">
<h1 class="col-span-full">
Dynamic Environments
</h1>
<div>
  <v-clicks>

  - **Environment per feature**
  - Deploys triggered on pull request
  - Features can be tested in parallel
  - No more bottle neck! 🥳
  - Environments are ephermeral
  - Can be destroyed once pull request is merged

  </v-clicks>
</div>
<div>
  <img alt="Dynamic Environments" src="/dynamic-environments.webp" class="bg-white p-5 rounded-xl" />
  <small class="text-center block m-2">
  <a href="https://codefresh.io/kubernetes-tutorial/kubernetes-antipatterns-2/">
  codefresh, Kubernetes Deployment Antipatterns – part 2
  </a>
  </small>
</div>
</div>

---

<div class="flex flex-col h-full">
  <h1>Okteto Demo</h1>
  <video class="overflow-hidden mx-auto" src="/okteto-demo.mp4" type="video/mp4" controls />
</div>
