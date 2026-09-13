<h1 align="center">Mohammad Tahmim Tasin</h1>

<p align="center">
Co founder and CTO at FreeleeGo. I build and ship production web products with Next.js, Django and PostgreSQL.
</p>

<p align="center">
<a href="https://mttasin.vercel.app/"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio"></a>
<a href="mailto:m.t.tasin20@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
<a href="https://linkedin.com/in/mttasin"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
<a href="https://x.com/MTTasin1"><img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X"></a>
<a href="https://www.facebook.com/M.T.Tasin20"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" alt="Facebook"></a>
</p>

---

## About

- Co founder and CTO at **[FreeleeGo](https://www.freeleego.com/)**, a digital agency based in Chattogram, Bangladesh
- I take products end to end, from data model and API design through to deployment, scaling and the ads that bring traffic in
- Day to day stack is Next.js and TypeScript on the front, Django REST Framework and PostgreSQL behind it, Redis and Celery where the work needs a queue
- I also build AI and ML features into client products, from LLM powered sales agents to recommendation and scoring
- I ship for real constraints, low bandwidth Android users, shared cPanel hosts, local payment gateways, Bengali first interfaces
- Available for client work, both through FreeleeGo and directly

> Source for the projects below is private. Every one of them is live, so click the site rather than looking for a repo.

## Selected work

### [EducareQuiz](https://educarequiz.com)

Medical exam prep platform for Bangladeshi medical students. Question bank, timed mock exams, video and slide lessons, full admin panel. Built for a client, shown with their permission.

- Next.js 16, React 19, Django 6, PostgreSQL 18, Redis, Celery, Docker Compose on a single VPS
- Write behind answer cache so a student's answers survive a closed browser, Redis first then flushed to PostgreSQL
- Per country pricing with two gateways, SSLCommerz for BDT and Stripe for USD, with idempotent order fulfilment protected against double firing from concurrent IPN and browser redirect
- Private video delivery through short lived token signed URLs, pptx decks converted to slide images by a Celery worker
- Version key cache invalidation so one counter bump orphans every stale list key regardless of filter combination
- Holds roughly 300 to 500 concurrent active users on 2 vCPU and 8 GB RAM
- Push to main triggers a GitHub Actions deploy, build, migrate and collect static on the VPS

### [Zaujain Nikah Point](https://zaujain.xyz/)

My own ecommerce business selling premium customized Nikah Nama products across Bangladesh. I built the platform and I run the Meta ads behind it.

- Next.js 16, TypeScript, Django 6, deployed on shared cPanel with Passenger, no Docker and no background workers
- With no job queue available, fraud checks and LLM calls run synchronously with timeouts and fallbacks rather than pretending a worker exists
- AI sales agent answers customers in Bengali from live catalogue facts, so it quotes real prices instead of inventing them
- Product configurator prices from admin defined options, and prices are snapshotted into the order so later catalogue edits never mutate a placed order
- Built for slow 2G and 3G on low end Android, image first, huge tap targets, Bengali only storefront with an English admin panel
- Courier booking and the Meta conversion event fire only after a human confirms the order by phone, so a cancelled order never reports a sale

### [FreeleeGo Platform](https://www.freeleego.com/)

Our agency site plus the client and team portal behind it. Portfolio and case studies on the public side, projects, tasks, meetings, files and invoices behind auth.

- Next.js, Redux Toolkit, Django REST Framework, Djoser and SimpleJWT with refresh handling
- Client portal for project progress, separate team portal for profiles, tasks and admin work

### FreeleeGo CRM

Internal CRM we run the agency on. Leads, kanban tasks, content calendar and email campaigns in one place. Private, no public instance.

- React with Vite, Redux Toolkit, Django REST Framework, JWT auth
- Drip sender paces campaign email one at a time on a fixed interval so the sending domain does not get spam flagged
- Lead verification workbench for cross checking data and flagging inconsistencies, BANT scoring on every lead

## Tech

**Frontend**

![React](https://img.shields.io/badge/React-20232a?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![Redux](https://img.shields.io/badge/Redux%20Toolkit-593d88?style=for-the-badge&logo=redux&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

**Backend**

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![DRF](https://img.shields.io/badge/Django%20REST-ff1709?style=for-the-badge&logo=django&logoColor=white&labelColor=gray)
![Celery](https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=celery&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

**Data and infrastructure**

![Postgres](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

**AI and ML**

![Python](https://img.shields.io/badge/LLM%20Integration-412991?style=for-the-badge&logo=openai&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

**Design and tooling**

![Illustrator](https://img.shields.io/badge/Illustrator-FF9A00?style=for-the-badge&logo=adobeillustrator&logoColor=white)
![Photoshop](https://img.shields.io/badge/Photoshop-31A8FF?style=for-the-badge&logo=adobephotoshop&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)

## Hire me

I take on client projects, both through FreeleeGo and directly. Web apps, ecommerce, custom platforms, and the paid ads and SEO that bring people to them.

Email **[m.t.tasin20@gmail.com](mailto:m.t.tasin20@gmail.com)** or message me on [LinkedIn](https://linkedin.com/in/mttasin). More work on my [portfolio](https://mttasin.vercel.app/).
