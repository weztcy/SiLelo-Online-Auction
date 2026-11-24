# Portfolio Project Data — SiLelo - Online Auction

- **Category:** `web-development` (`Web Development`)
- **Accent Color:** `cyan`
- **Target Assets Folder:** `public/images/projects/silelo_online_auction/`
- **Required Local Images:** `banner.webp`, `image01.webp` .. `image25.webp`

## TypeScript Data (`ProjectCaseStudy`)

```typescript
{
  "id": "silelo-online-auction",
  "code": "PRO-12 // WEB-02",
  "title": "SiLelo - Online Auction",
  "category": "web-development",
  "categoryLabel": "Website",
  "year": "2023",
  "status": "Completed",
  "accentColor": "cyan",
  "repoUrl": "https://github.com/weztcy/SiLelo-Online-Auction",
  "license": "MIT License",
  "banner": "/images/projects/silelo_online_auction/banner.webp",
  "summary": "Full-stack online auction platform in CodeIgniter and MariaDB with competitive bidding, escrow deposit verification, and multi-role portals.",
  "projectDescription": "SiLelo is a curated full-stack online auction platform built with PHP CodeIgniter and MariaDB. It connects verified auctioneers and bidders through transparent live bidding, security deposit validation, automated invoice generation, escrow payment confirmation, and category-driven recommendations.",
  "architectureSummary": "Three-tier CodeIgniter MVC web application connecting Bootstrap/AdminLTE role portals to a 11-table MariaDB relational database with Google OAuth and SMTP integration.",
  "techStack": [
    "PHP",
    "CodeIgniter",
    "MariaDB",
    "MySQL",
    "Bootstrap",
    "AdminLTE",
    "jQuery",
    "DataTables",
    "TinyMCE",
    "Owl Carousel",
    "Google OAuth",
    "Composer"
  ],
  "telemetryMatrix": {
    "projectType": "Full-Stack Online Auction Marketplace",
    "targetPlatform": "Web Browser (Desktop & Mobile)",
    "primaryDomain": "E-Commerce & Digital Auctions",
    "architecturePipeline": "CodeIgniter MVC + MariaDB + OAuth/SMTP",
    "testingAndAudit": "Passed",
    "projectStatus": "Completed",
    "projectYear": "2023"
  },
  "projectInfo": {
    "projectType": "Full-Stack Online Auction Platform",
    "developmentStatus": "Completed",
    "developmentYear": "2023",
    "platform": "Web (Responsive Desktop & Mobile)",
    "projectCategory": "Web Development"
  },
  "projectBackground": "Traditional online auctions often suffer from unverified participants, fake bids, and fragmented payment settlement. SiLelo addresses these challenges by enforcing refundable security deposits prior to bidding, masking bidder identities publicly, and centralizing escrow invoice verification and moderation within a unified web ecosystem.",
  "problemStatements": [
    {
      "title": "Unverified & Speculative Bidding",
      "description": "Open online auctions frequently experience non-serious or bot bids when participants have no financial commitment prior to placing offers.",
      "issueCode": "ISSUE_01"
    },
    {
      "title": "Opaque Winner Settlement & Deposit Reconciliation",
      "description": "Manually calculating tax, applying prior security deposits, and verifying bank transfer proofs across winning auction lots slows down post-auction fulfillment.",
      "issueCode": "ISSUE_02"
    },
    {
      "title": "Fragmented Multi-Role Auction Operations",
      "description": "Bidders, independent auctioneers, and platform moderators require distinct operational workflows that become error-prone without role-isolated portals.",
      "issueCode": "ISSUE_03"
    }
  ],
  "projectObjectives": [
    {
      "title": "Enforce Escrow-Backed Bidding Eligibility",
      "description": "Require bidders to submit and verify refundable security deposits before unlocking full auction participation and balance-offset invoice settlements.",
      "targetTag": "TARGET_01"
    },
    {
      "title": "Automate Winner Selection & Invoicing",
      "description": "Transition winning lots to sold-out status, mark competing offers as outbid, generate unique-code invoices, and notify winners via SMTP automatically.",
      "targetTag": "TARGET_02"
    },
    {
      "title": "Deliver Role-Isolated Dashboards & Analytics",
      "description": "Provide dedicated portals for bidders, auctioneers, and administrators alongside category click and bid engagement tracking.",
      "targetTag": "TARGET_03"
    }
  ],
  "coreFeatures": [
    {
      "title": "Curated Storefront & Personalized Recommendations",
      "description": "Showcases featured high-value auction lots, category catalogs, and interest-based recommendations tailored from each bidder's saved category preferences.",
      "badge": "Storefront"
    },
    {
      "title": "Competitive Bidding & Privacy-Masked History",
      "description": "Records timestamped bidder offers against active lots while displaying ranked bid leaderboards with masked participant emails and real-time leading-bid status.",
      "badge": "Bidding Engine"
    },
    {
      "title": "Security Deposit & Escrow Invoice Settlement",
      "description": "Validates minimum Rp 1,000,000 security deposits, deducts active balances against winning invoice totals (including 10% tax and unique transfer codes), and reconciles excess balances.",
      "badge": "Escrow & Billing"
    },
    {
      "title": "Auctioneer Lot Lifecycle & Winner Selection",
      "description": "Enables verified auctioneers to upload multi-photo product galleries via AJAX, publish lots with closing dates, inspect incoming bids, and confirm auction winners.",
      "badge": "Seller Portal"
    },
    {
      "title": "Admin Moderation & Engagement Analytics",
      "description": "Equips administrators to approve or block auctioneers and bidders, validate deposit and invoice receipts, audit buyer reviews, and monitor category click metrics.",
      "badge": "Administration"
    }
  ],
  "interfaceShowcase": [
    {
      "imageUrl": "/images/projects/silelo_online_auction/image01.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image02.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image03.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image04.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image05.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image06.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image07.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image08.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image09.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image10.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image11.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image12.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image13.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image14.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image15.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image16.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image17.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image18.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image19.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image20.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image21.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image22.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image23.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image24.webp"
    },
    {
      "imageUrl": "/images/projects/silelo_online_auction/image25.webp"
    }
  ],
  "userFlow": {
    "summary": "Bidders browse curated lots by category or personalized interests, authenticate via email or Google OAuth, and fund a refundable security deposit before placing competitive bids. Once an auctioneer selects a winning bid, the platform generates an itemized invoice settled through escrow transfer confirmation.",
    "steps": [
      {
        "step": "01",
        "title": "Storefront Discovery & Category Tracking",
        "description": "Visitors explore live lots on the storefront; authenticated bidder visits increment category interest counters for personalized feeds.",
        "actorOrNode": "Bidder / Home Controller"
      },
      {
        "step": "02",
        "title": "Authentication & Deposit Verification",
        "description": "Bidders sign in via email or Google OAuth and upload security deposit transfer receipts validated by platform administrators.",
        "actorOrNode": "Bidder / Profile & Deposit Controllers"
      },
      {
        "step": "03",
        "title": "Lot Listing & Competitive Bidding",
        "description": "Verified auctioneers publish curated lots with opening prices and closing dates while bidders submit ranked offers on product detail pages.",
        "actorOrNode": "Auctioneer / Bidder / Barang & Home"
      },
      {
        "step": "04",
        "title": "Winner Selection & Invoice Issuance",
        "description": "Auctioneers select the winning bid from the transaction modal, marking the lot sold out and dispatching an invoice via SMTP.",
        "actorOrNode": "Auctioneer / Transaksi Controller"
      },
      {
        "step": "05",
        "title": "Escrow Settlement & Post-Auction Review",
        "description": "Winners apply deposit balances or upload transfer proofs to settle invoices, administrators confirm receipt, and buyers submit seller reviews.",
        "actorOrNode": "Bidder / Admin / Deposit & Profile"
      }
    ]
  },
  "systemArchitecture": {
    "summary": "SiLelo follows a three-tier CodeIgniter MVC architecture separating public storefronts, role-protected auctioneer and administrator portals, and MariaDB persistence. Controllers coordinate session auth, Google OAuth, SMTP notifications, image uploads, and relational queries via dedicated models and helper libraries.",
    "layers": [
      {
        "name": "Presentation Layer",
        "role": "Renders responsive storefront and back-office views via template_front and template_back layouts.",
        "components": ["Bootstrap Storefront Views", "AdminLTE Back-Office Views", "DataTables & TinyMCE", "Owl Carousel"]
      },
      {
        "name": "Application & Routing Layer",
        "role": "Routes clean URIs and enforces session-based role guards across public, bidder, auctioneer, and admin controllers.",
        "components": ["Home & Profile Controllers", "Dashboard Controller", "back_end/Barang & Transaksi", "back_end/Deposit, Users & Admin"]
      },
      {
        "name": "Integration & Helper Layer",
        "role": "Handles template composition, file uploads, Google OAuth 2.0 authentication, SMTP dispatch, and currency/access helpers.",
        "components": ["Template Library", "Google OAuth Library", "CodeIgniter Upload & Email", "mylib_helper"]
      },
      {
        "name": "Data & Media Persistence Layer",
        "role": "Persists relational auction state in MariaDB and stores uploaded avatars, product photos, and transfer proofs.",
        "components": ["MariaDB Database (lelang)", "M_produk, M_barang, M_dashboard, M_admin, User", "assets/foto_produk & foto_transfer"]
      }
    ]
  },
  "databaseDataFlow": {
    "type": "Database Schema / ERD",
    "summary": "The MariaDB schema (lelang) comprises 11 normalized InnoDB tables linking multi-role accounts, categorized auction products, multi-photo galleries, bid histories, security deposits, winner invoices, customer reviews, and category analytics.",
    "entitiesOrPipelines": [
      {
        "name": "users",
        "type": "Table",
        "fields": ["id", "oauth_provider", "oauth_uid", "nama_lengkap", "email", "password", "status", "alamat", "telephone"]
      },
      {
        "name": "abe_pelelang",
        "type": "Table",
        "fields": ["id_user", "nama_lengkap", "email", "nik_ktp", "telpon", "alamat", "hak_akses", "status", "tgl_aktif"]
      },
      {
        "name": "abe_admin",
        "type": "Table",
        "fields": ["id_user", "nama_lengkap", "email", "password", "hak_akses", "status", "tgl_daftar"]
      },
      {
        "name": "abe_produk",
        "type": "Table",
        "fields": ["id_produk", "nama_produk", "harga_produk", "jumlah_produk", "id_kategori", "id_pelelang", "status", "tgl_buka", "tgl_tutup", "harga_jual"]
      },
      {
        "name": "abe_foto_produk",
        "type": "Table",
        "fields": ["id_foto_produk", "id_produk", "id_user", "file_foto", "status"]
      },
      {
        "name": "abe_lelang_bidder",
        "type": "Table",
        "fields": ["id_lelang_bidder", "id_barang", "id_bidder", "id_kategori", "harga_lelang", "tanggal", "status"]
      },
      {
        "name": "abe_deposit",
        "type": "Table",
        "fields": ["id_deposit", "id_user", "status", "jumlah", "bank_pengirim", "bank_penerima", "file_foto", "id_invoice", "id_produk"]
      },
      {
        "name": "abe_invoice",
        "type": "Table",
        "fields": ["id_invoice", "no_invoice", "kode_unik", "id_produk", "id_user", "harga_produk", "deposit", "jumlah_transfer", "ppn", "status"]
      },
      {
        "name": "abe_kategori & abe_kategori_klik & abe_rekomendasi",
        "type": "Table",
        "fields": ["id_kategori", "nama_kategori", "url_kategori", "id_bidder", "jumlah_klik", "bidder"]
      },
      {
        "name": "abe_review & tabel_menu & abe_user_rule",
        "type": "Table",
        "fields": ["id_review", "kepuasan", "review", "produk", "pelelang", "id_level_user", "id_menu", "link"]
      }
    ]
  },
  "technicalImplementation": [
    {
      "category": "Escrow & Billing Logic",
      "title": "Automated Deposit Deduction & Excess Balance Rollover",
      "description": "In Profile::bayar_invoice_deposit, applying a verified deposit exceeding the invoice total marks the existing deposit as consumed, automatically creates a new active deposit record with the remaining balance, and transitions the invoice to transfer verification.",
      "badge": "Deposit Offset"
    },
    {
      "category": "Auction Lifecycle",
      "title": "Atomic Winner Selection & Invoice Generation",
      "description": "Transaksi::pilih_pemenang generates a sequential monthly invoice code with a 3-digit random reconciliation code, dispatches an HTML email notice to the winning bidder, updates all competing bids to kalah, marks the winning bid pemenang, and closes the lot as sold out.",
      "badge": "Winner Workflow"
    },
    {
      "category": "Access Control",
      "title": "Role-Segregated Session Guards & Dynamic Menu Rules",
      "description": "Back-office controllers reject unauthenticated requests and bidder-level sessions in their constructors, while sidebar navigation queries tabel_menu joined with abe_user_rule to render role-specific modules for administrators and auctioneers.",
      "badge": "Role Guards"
    },
    {
      "category": "Media & Engagement",
      "title": "AJAX Gallery Staging & Category Interest Tracking",
      "description": "Barang::add_foto stages uploaded lot images with status baru before linking them to newly saved products, while Home::produk logs per-bidder category clicks in abe_kategori_klik and Profile::addrekomendasi toggles personalized interests.",
      "badge": "AJAX & Analytics"
    }
  ],
  "primaryTechSpecs": {
    "programmingLanguage": "PHP",
    "framework": "CodeIgniter",
    "database": "MariaDB"
  },
  "architectureQuality": {
    "badges": [
      "Role Segregated",
      "Escrow Verified",
      "MVC Architecture",
      "Responsive UI"
    ]
  }
}
```
