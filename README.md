<h1 align="center">Mohammad Tahmim Tasin</h1>

<p align="center">
Full-stack developer for web apps, mobile apps and machine learning. Co-founder and CTO at FreeLeeGo.<br>
I design, build and ship complete products with Next.js, React, Django and Python, from the database to the deploy.
</p>

<p align="center">
<a href="https://mttasin.com/"><img src="https://img.shields.io/badge/Portfolio-mttasin.com-F59E0B?style=for-the-badge&labelColor=111111" alt="Portfolio: mttasin.com"></a>
<a href="mailto:m.t.tasin20@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
<a href="https://www.linkedin.com/in/mttasin/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge" alt="LinkedIn"></a>
<a href="https://x.com/MTTasin"><img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X"></a>
<a href="https://www.facebook.com/M.T.Tasin20"><img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" alt="Facebook"></a>
</p>

---

## About

- Building production software since 2023. I take products from an idea to a live system: data model, API, interface, payments, background jobs, deployment, and the boring parts that keep it running, like backups and rate limits
- Next.js and React on the front end, Django and Python on the back end, PostgreSQL, Redis and Celery underneath
- Offline-first apps for places where the internet can't be trusted, and machine learning models with TensorFlow and scikit-learn when a problem calls for one
- Co-founder and CTO at **[FreeLeeGo](https://freeleego.com/)**, a full-stack digital agency, for projects that need design, marketing or SEO alongside the build
- Working remotely with clients in the US, Canada, the UK and Europe from GMT+6, which overlaps with European mornings and US East Coast evenings
- Open to **freelance projects, contract work and full-time remote roles**

Portfolio and full case studies: **[mttasin.com](https://mttasin.com/)**

## Selected work

Most client code is private, so each project links to its live site or its case study. Public repos are linked where they exist.

### [EducareQuiz](https://educarequiz.com) · Lead full-stack developer · [Case study](https://mttasin.com/projects/educarequiz/)

Medical exam prep SaaS for MRCP, FCPS, MRCOG and USMLE: course player, question bank, timed mock exams, billing and a full admin panel. Built for a client, shown with their permission.

- Next.js 16, React 19, Django 6, DRF, PostgreSQL 18, Redis, Celery, Stripe, Bunny Stream, Docker Compose on a VPS behind Cloudflare
- Exam answers go to Redis first and are saved to PostgreSQL at the end of a session, so a closed browser never loses work
- The visitor's country picks the payment gateway, and order fulfilment is idempotent and Redis-locked, because a payment redirect and its webhook can arrive at the same moment
- Private video over HLS with token-signed links, AVIF copies of every uploaded image
- Admin with bulk CSV/XLSX question import, a blog with scheduled publishing, role-based permissions, and GA4 and Google Ads data pulled in hourly
- AI assistant on the public site with a daily message cap to keep costs predictable
- Origin only accepts traffic from Cloudflare, per-visitor rate limits, GitHub Actions deploys plus a separate staging copy. 200+ commits since February 2026

### [Zaujain](https://zaujain.xyz/) · Sole developer · [Case study](https://mttasin.com/projects/zaujain-ecommerce/) · [Code](https://github.com/MTTasin/Zaujian)

Custom e-commerce store for personalised wedding keepsakes, with a live-priced product configurator, combos and an AI sales assistant. I built the platform and run the Meta ads behind it.

- Next.js 16, TypeScript, Django 6, DRF, PostgreSQL, Redis, Vitest, on shared cPanel hosting
- Pricing engine with base prices, option modifiers and lookup pricing. Prices are snapshotted into the cart and order so later edits never change a placed order, and money is always a decimal
- No background workers on shared hosting, so AI and fraud checks run synchronously with timeouts and fallbacks
- Pre-sized, lazy-loaded images so pages stay light on 3G and low-end Android phones

### Meta Conversions API pipeline · Sole developer · [Case study](https://mttasin.com/projects/meta-conversions-api-tracking/)

Server-side tracking for Zaujain's click-to-Messenger ads, so Meta learns from real buyers instead of people who tapped a button and left.

- Django, Celery, Redis, PostgreSQL, Messenger Platform webhooks
- Lead fires only when the person replies in Messenger, Purchase (with the sale value) only when the order is marked complete
- HMAC-SHA256 webhook signatures, constant-time token check, event_id deduplication, retries with backoff and a delivery log. Runs with a Celery worker or in a cron-only mode

### The Professor POS · Sole developer · [Case study](https://mttasin.com/projects/theprofessor-pos/)

Offline point of sale for a clothing store. One Windows PC runs it as a service, and staff sell from their phones over shop Wi-Fi at `http://pos.local`. No internet, no cloud, no monthly fees.

- Django 6, DRF, SQLite (WAL), React 19, TypeScript, TanStack Query, WinSW, mDNS
- Landed cost spreads van fare and labour across every garment in a delivery, so profit is real profit
- Edits write correcting entries and never rewrite history, which keeps the books auditable. Updates back up the database before migrating

### Self POS · Sole developer · [Case study](https://mttasin.com/projects/self-pos/)

Offline-first Android and web POS that replaced a wholesaler's paper ledgers, built for older users with large text and a picture on every button.

- Flutter, Dart, Drift (SQLite), Node.js, PostgreSQL, Bluetooth thermal printing
- Every phone keeps its own database and syncs on its own: on opening, a few seconds after each entry and every five minutes. A sale never waits for the network
- Append-only history, money stored in whole minor units, mixed-unit sales (ream, quire, piece, yard), receipts on WhatsApp or a 58 mm printer

### [FreeLeeGo](https://freeleego.com/) website and CRM · Co-founder & CTO · [Platform](https://mttasin.com/projects/freeleego-agency-platform/) · [CRM](https://mttasin.com/projects/freeleego-crm/)

The agency's site and staff portal, plus the internal CRM we run the agency on.

- Site: Next.js 16 on a Django REST API, fully editable from the admin, containerised behind Caddy with automated backups. Staff portal for projects, tasks, files, meetings and invoices
- CRM: React, Redux Toolkit, Django REST Framework, MySQL. Leads with BANT scoring and a verification workbench, Kanban board, content calendar, segmented newsletters
- The email drip worker sends one message at a time at a safe interval, as a cron-friendly management command that needs no queue

### More projects

| Project | What it is | Links |
|---|---|---|
| Email Verification System | Bulk email verification app and API: syntax, MX, SMTP and disposable checks in Celery workers | [Case study](https://mttasin.com/projects/email-verification-system/) · [Code](https://github.com/MTTasin/Email-Verification-System) |
| Sharanga Kinera | Single-product store with an order-first landing page and an admin for orders, inventory and variants | [Live](https://www.sharagakinera.com) · [Case study](https://mttasin.com/projects/sharanga-kinera/) |
| Water Foundation LMS | Learning management system for a nonprofit: roles, modules, enrolments, a graded practice center | [Case study](https://mttasin.com/projects/water-foundation-lms/) |
| The Professor e-commerce | Django REST Framework and React store with JWT accounts and a django-unfold admin | [Case study](https://mttasin.com/projects/the-professor-ecommerce/) · [Code](https://github.com/MTTasin/Amar_dokan) |
| Shikkhashala | Coaching center management: students, teachers, payments, attendance. My first client project | [Case study](https://mttasin.com/projects/shikkhashala-coaching-management/) · [Code](https://github.com/MTTasin/Coaching-management-system) |
| Heaven Furniture Mart | Conversion-focused landing page in Next.js 16, RACDOX Hackathon entry | [Case study](https://mttasin.com/projects/heaven-furniture-landing-page/) |
| Melanoma detection (assignment) | TensorFlow and Keras CNN that classifies skin lesion photos | [Case study](https://mttasin.com/projects/melanoma-detection-cnn/) |
| Heart disease risk (assignment) | scikit-learn model served in a Django app with single and bulk predictions | [Case study](https://mttasin.com/projects/heart-disease-risk-predictor/) |

## What I build

- [Full-Stack Web Development](https://mttasin.com/services/full-stack-development/)
- [SaaS & Web Application Development](https://mttasin.com/services/saas-development/)
- [Next.js & React Development](https://mttasin.com/services/nextjs-react-development/)
- [Django & Python Backend Development](https://mttasin.com/services/django-development/)
- [Custom E-commerce Development](https://mttasin.com/services/ecommerce-development/)
- [Offline-First App Development](https://mttasin.com/services/offline-first-apps/)
- [Machine Learning & AI Integration](https://mttasin.com/services/machine-learning-ai/)

## Tech

**Frontend**

![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232a?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Redux Toolkit](https://img.shields.io/badge/Redux_Toolkit-593D88?style=for-the-badge&logo=redux&logoColor=white)
![TanStack Query](https://img.shields.io/badge/TanStack_Query-FF4154?style=for-the-badge&logo=reactquery&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-0055FF?style=for-the-badge&logo=framer&logoColor=white)

**Backend**

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=FFDD54)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![Django REST Framework](https://img.shields.io/badge/Django_REST-A30000?style=for-the-badge&logo=django&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=celery&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

**Data and machine learning**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

**Mobile and offline**

![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![Drift](https://img.shields.io/badge/Drift_(SQLite)-003B57?style=for-the-badge&logo=sqlite&logoColor=white)

**Payments and integrations**

![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=for-the-badge&logo=stripe&logoColor=white)
![Meta Conversions API](https://img.shields.io/badge/Meta_Conversions_API-0467DF?style=for-the-badge&logo=meta&logoColor=white)
![GA4](https://img.shields.io/badge/GA4-E37400?style=for-the-badge&logo=googleanalytics&logoColor=white)
![LLM APIs](https://img.shields.io/badge/LLM_APIs-412991?style=for-the-badge)

**DevOps and tools**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=for-the-badge&logo=caddy&logoColor=white)
![Linux](https://img.shields.io/badge/Linux_VPS-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

## Hire me

Freelance projects, contracts and full-time remote roles, directly or through FreeLeeGo when the project needs a full team. Clear plans before code, short progress updates, and documentation you can hand to the next developer.

Email **[m.t.tasin20@gmail.com](mailto:m.t.tasin20@gmail.com)** or message me on [LinkedIn](https://www.linkedin.com/in/mttasin/). More at **[mttasin.com](https://mttasin.com/)**.
