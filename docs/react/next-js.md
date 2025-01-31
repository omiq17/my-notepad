---
layout: note
title: Next.js Note
parent: React
---

- Pre-rendering: two froms:

  - Static Generation
    - Generates HTML on build time
    - Resused on each request
    - Uses `getStaticProps` function
  - Server-side Rendering
    - Generates HTML on request time
    - Uses `getServerSideProps`

- Clien-side rendering: use SWR react-hook.
