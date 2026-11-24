# SiLelo - Online Auction

![Project Banner](screenshots/banner.webp)

![Project Type](https://img.shields.io/badge/Project_Type-Full--Stack-blue)
![Primary Language](https://img.shields.io/badge/Primary_Language-PHP-blue)
![Framework](https://img.shields.io/badge/Framework-CodeIgniter-orange)
![Runtime / Platform](https://img.shields.io/badge/Runtime_%2F_Platform-Apache_%2F_PHP-green)
![Package Manager](https://img.shields.io/badge/Package_Manager-Composer-red)
![Build Tool](https://img.shields.io/badge/Build_Tool-PHP_Router-purple)
![Database](https://img.shields.io/badge/Database-MariaDB_%2F_MySQL-informational)
![Project Status](https://img.shields.io/badge/Project_Status-Completed-success)
![Project Year](https://img.shields.io/badge/Project_Year-2023-blue)
![License](https://img.shields.io/badge/License-MIT-yellow)

## Project Overview

**SiLelo - Online Auction** is a full-stack web-based auction marketplace built with PHP and the CodeIgniter MVC framework, backed by a MariaDB/MySQL relational database. It connects verified auctioneers (`pelelang`), registered bidders, and platform administrators within a structured bidding ecosystem across curated categories such as electronics, watches and fashion, automotive accessories, antiques, and hobbies. To prevent fake bids and fragmented settlements, the platform enforces refundable security deposit verification before bidding, records transparent masked bid histories, automates winner invoice generation with unique payment verification codes, and provides dedicated portals for lot management, escrow payment validation, and category-click analytics.

## Key Features

- **Curated Auction Storefront & Category Browsing**: Displays featured high-value lots, live auction grids, category filters (`abe_kategori`), lot countdown dates, and personalized lot recommendations (`abe_rekomendasi`).
- **Transparent Bidding & Masked Bid History**: Allows authenticated bidders to submit competitive bids (`abe_lelang_bidder`) while displaying ranked bid histories with privacy-masked bidder emails and live leading-bid indicators.
- **Security Deposit Escrow Mechanism**: Requires bidders to top up and submit bank transfer proofs for security deposits (`abe_deposit`, minimum Rp 1,000,000 enforced in `Profile::deposit`) that can later be applied directly toward winning invoice settlements.
- **Automated Winner Invoicing & Payment Reconciliation**: Generates sequential invoices (`INV...` with 3-digit unique codes) upon winner selection, calculates 10% tax and deposit deductions, sends email notifications via SMTP, and tracks bank transfer confirmations (`abe_invoice`).
- **Dedicated Auctioneer Portal (`Portal Pelelang`)**: Provides verified sellers with an AdminLTE dashboard to stage new lots (`ready`), upload multi-image product galleries (`abe_foto_produk`), publish items to live auctions (`lelang`), inspect incoming bids, select winners, and review invoices.
- **Comprehensive Administrator Moderation Panel**: Equips administrators with system-wide oversight over staff accounts (`abe_admin`), auctioneer and bidder approvals/blocking, deposit and invoice validation, buyer satisfaction reviews (`abe_review`), and category click/bid analytics (`abe_kategori_klik`).
- **Dual Authentication & Google OAuth 2.0**: Supports standard email/password authentication alongside Google OAuth 2.0 sign-in for bidders, plus email-verified registration and password recovery workflows for auctioneers.

## Tech Stack

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| Backend Framework | CodeIgniter 3 (PHP) | MVC routing, controllers, models, session management, file upload, and SMTP email delivery |
| Database | MariaDB / MySQL (`mysqli`) | Relational persistence across 11 tables for users, auctioneers, lots, bids, deposits, invoices, and analytics |
| Frontend UI (Storefront) | Bootstrap, Owl Carousel, Bootstrap Select | Responsive auction marketplace layout, carousels, modals, and bidder account portal |
| Frontend UI (Back Office) | AdminLTE, Bootstrap 3, DataTables, Datepicker | Role-based auctioneer and administrator dashboards, searchable tables, and auction scheduling |
| Rich Text & Utilities | TinyMCE, jQuery, Font Awesome | Rich product description editing, AJAX photo/preference updates, and iconography |
| Authentication | Google OAuth 2.0 (`google-login-api`) | Third-party Google sign-in integration for bidder accounts alongside MD5 credential login |
| Server & Routing | Apache (`mod_rewrite`) / PHP Built-in Router | Clean URL rewriting via `.htaccess` and local development serving via `router.php` |
| Dependency Metadata | Composer | PHP project metadata and framework dependency configuration (`composer.json`) |

## Application Architecture

SiLelo implements a classic CodeIgniter 3 Model-View-Controller (MVC) full-stack architecture served through a single front controller (`index.php`) and routed via `.htaccess` or `router.php`. Public and bidder views render through `template_front`, while auctioneer and administrator operations run under `template_back` protected by session role checks. Controllers delegate relational queries and mutations to dedicated models (`M_produk`, `M_barang`, `M_dashboard`, `M_admin`, `User`) connected to MariaDB via the `mysqli` driver, while integrating external Google OAuth 2.0 and SMTP mail services.

```mermaid
flowchart LR
    subgraph Client["Browser Client (Storefront & Back-Office UI)"]
        PublicUI["Public & Bidder Views\n(Bootstrap / jQuery / Owl Carousel)"]
        BackUI["Auctioneer & Admin Portals\n(AdminLTE / DataTables / TinyMCE)"]
    end

    subgraph App["CodeIgniter 3 MVC Application (index.php / router.php)"]
        Controllers["Controllers\n(Home, Profile, Dashboard,\nback_end/Barang, Transaksi, Deposit, Users, Admin)"]
        Libraries["Libraries & Helpers\n(Template, Session, Upload, Email, Google, mylib_helper)"]
        Models["Models\n(M_produk, M_barang, M_dashboard, M_admin, User)"]
    end

    subgraph Data["Persistence & File Storage"]
        DB[("MariaDB / MySQL\nDatabase: lelang (11 Tables)")]
        Assets["Local Media Storage\n(assets/foto, foto_produk, foto_transfer)"]
    end

    subgraph External["External Services"]
        GoogleOAuth["Google OAuth 2.0 API"]
        SMTP["SMTP Mail Server"]
    end

    PublicUI -->|"HTTP / AJAX"| Controllers
    BackUI -->|"HTTP / AJAX"| Controllers
    Controllers --> Libraries
    Controllers --> Models
    Models -->|"mysqli Queries"| DB
    Libraries -->|"File Uploads"| Assets
    Libraries -->|"OAuth Flow"| GoogleOAuth
    Libraries -->|"Verification & Invoice Emails"| SMTP
```

## Screenshots / Preview

### 1. Landing Page & Hero Section
![Landing Page and Hero Section](screenshots/image1.webp)
The primary marketplace landing page featuring top-level navigation (`Eksplor Lelang`, `Kategori`, `Cara Lelang`, `Bantuan`, `Buka Lelang`), a featured high-value lot spotlight card, and a live platform telemetry ribbon highlighting curated lots, completed auctions, total transaction value, and escrow protection.

### 2. Live Auctions Catalog Grid
![Live Auctions Catalog Grid](screenshots/image2.webp)
The active auction catalog ("Lelang Terpopuler Hari Ini") rendering a responsive four-column product grid with pulsing `LIVE` badges, category chips, current bid values, bid counts, closing dates, and direct bidding action buttons.

### 3. Auction Lot Detail & Bidding Console
![Auction Lot Detail and Bidding Console](screenshots/image3.webp)
The curated lot detail view displaying the product gallery, verified auctioneer badge, live auction status, highest bid telemetry, bidder participation count, closing date, and the SiLelo Buyer Protection escrow checklist.

### 4. How It Works & Auction Guide
![How It Works and Auction Guide](screenshots/image4.webp)
The official bidder guide outlining the four-stage auction lifecycle: account registration, refundable security deposit submission, real-time competitive bidding, and post-win invoice settlement with insured shipping.

### 5. Bidder Authentication & Login Screen
![Bidder Authentication and Login Screen](screenshots/image5.webp)
The bidder sign-in interface supporting both one-click Google OAuth 2.0 authentication and standard email/password credentials to unlock bidding and account management features.

### 6. Bidder Account & Profile Management
![Bidder Account and Profile Management](screenshots/image6.webp)
The bidder profile workspace (`ID BIDDER: #0001`) enabling users to maintain shipping details, update passwords, inspect their active security deposit balance (`Rp 5.000.000`), and trigger deposit top-ups.

### 7. Bidder Category Interest Preferences
![Bidder Category Interest Preferences](screenshots/image7.webp)
The interest-tuning panel where bidders toggle preferred auction categories (`Elektronik & Gadget`, `Jam Tangan & Fashion`, `Hobi & Olahraga`, etc.) with automatic AJAX persistence to tailor personalized recommendations.

### 8. Bidder Bidding History
![Bidder Bidding History](screenshots/image8.webp)
The bid tracking table ("Riwayat Tawaran Saya") listing every lot the bidder has participated in alongside timestamps, submitted bid amounts, `DITAWAR` status indicators, and quick links back to each lot page.

### 9. Bidder Auction Invoices & Billing
![Bidder Auction Invoices and Billing](screenshots/image9.webp)
The bidder billing center ("Tagihan & Invoice Lelang") displaying winner settlement invoices, issuance dates, total amounts due, and clear empty-state feedback when no pending invoices exist.

### 10. Auctioneer Portal Login & Registration
![Auctioneer Portal Login and Registration](screenshots/image10.webp)
Side-by-side authentication interfaces for the Auctioneer Portal (`Portal Mitra Pelelang`), providing email/password sign-in with demo account guidance alongside new auctioneer partner registration.

### 11. Auctioneer Dashboard Overview
![Auctioneer Dashboard Overview](screenshots/image11.webp)
The AdminLTE-based Auctioneer Dashboard displaying KPI summary widgets (total lots, live lots, sold lots, incoming bids) and a real-time lot status table categorized by `READY`, `LELANG`, and `SOLD OUT` states.

### 12. Auctioneer Lot Inventory Management
![Auctioneer Lot Inventory Management](screenshots/image12.webp)
The seller inventory DataTable ("Data Produk Lelang") listing staged items with category labels, opening prices, and quick actions to launch an item into live bidding, edit lot metadata, or delete entries.

### 13. Create Auction Lot Form
![Create Auction Lot Form](screenshots/image13.webp)
The lot creation workspace supporting AJAX multi-image product uploads, category assignment, opening price input, quantity configuration, and formatted product descriptions.

### 14. Auctioneer Live Bidding Transactions
![Auctioneer Live Bidding Transactions](screenshots/image14.webp)
The auctioneer transaction monitor tracking active auction lots, incoming bidder counts, modal bid-history inspection (`Detail`) for selecting the winning bidder, and auction expiration controls.

### 15. Auctioneer Store Profile Settings
![Auctioneer Store Profile Settings](screenshots/image15.webp)
The store profile management screen allowing verified auctioneers to update KTP identity numbers, business names, contact details, addresses, and profile photos while reviewing their listed inventory.

### 16. Administrator Portal Login Screen
![Administrator Portal Login Screen](screenshots/image16.webp)
The dedicated administrator authentication gate designed for internal platform staff and super administrators to access moderation and financial verification workflows.

### 17. Administrator Control Center Dashboard
![Administrator Control Center Dashboard](screenshots/image17.webp)
The platform-wide Administrator Dashboard summarizing total registered bidders, active auctioneers, active live auction lots, and pending invoice validations with one-click moderation navigation.

### 18. System Administrator Management
![System Administrator Management](screenshots/image18.webp)
The staff directory ("Data Admin") enabling super administrators to create, edit, activate, deactivate, or permanently remove administrative accounts with role level assignment.

### 19. Active Auctioneers Directory
![Active Auctioneers Directory](screenshots/image19.webp)
The auctioneer moderation view listing all verified sellers alongside profile inspection (`Detail`) and account suspension (`blokir`) controls.

### 20. Administrator Active Auction Lots Monitor
![Administrator Active Auction Lots Monitor](screenshots/image20.webp)
The global active-lot audit table ("Data Produk Lelang Aktif") providing administrators visibility across all ongoing auction listings, categories, and opening prices.

### 21. Incoming Winner Invoices Verification
![Incoming Winner Invoices Verification](screenshots/image21.webp)
The escrow settlement reconciliation table ("Data Invoice Masuk") presenting invoice numbers, uploaded transfer receipts, bidder emails, destination bank accounts, transfer totals, and `Lunas` confirmation status.

### 22. Bidder Reviews & Reputation Audit
![Bidder Reviews and Reputation Audit](screenshots/image22.webp)
The post-auction feedback monitor ("Data Review Bidder") capturing buyer satisfaction levels (`Sangat Puas`) and detailed reviews linked to completed auction lots and sellers.

### 23. Active Bidders Directory
![Active Bidders Directory](screenshots/image23.webp)
The bidder account directory ("Data Bidder Aktif") listing verified platform buyers with account status indicators and administrative blocking actions.

### 24. Bidder Category Click Analytics
![Bidder Category Click Analytics](screenshots/image24.webp)
The behavioral analytics view ("Data Minat Bidder Kategori Klik") aggregating per-bidder category click counts across all five marketplace categories to support demand visibility.

### 25. Administrator Account Profile Settings
![Administrator Account Profile Settings](screenshots/image25.webp)
The administrator profile configuration screen displaying access role, account status, registration date, avatar upload, and password update controls.

## Prerequisites

- **PHP** (`>= 5.3.7`, compatible with PHP 7.x / 8.x with `mysqli` extension enabled)
- **MariaDB** or **MySQL** server (tested with MariaDB 13.0 in `lelang.sql`)
- **Web Server**: PHP Built-in Development Server (via `router.php`) or Apache HTTP Server with `mod_rewrite` enabled
- **Composer** (optional, for managing `composer.json` dev dependencies)
- **Web Browser**: Modern desktop or mobile browser with JavaScript enabled

## Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/weztcy/SiLelo-Online-Auction.git
   cd "SiLelo - Online Auction"
   ```

2. **Start MariaDB / MySQL and import the database schema**
   - On Windows with a local MariaDB setup matching `start_db.bat`, you can start the database service and import `lelang.sql`:
   ```bash
   mysql -u root -p -e "CREATE DATABASE IF NOT EXISTS lelang;"
   mysql -u root -p lelang < lelang.sql
   ```

3. **Verify database configuration**
   - Open `application/config/database.php` and ensure `hostname`, `username`, `password`, and `database` (`lelang`) match your local database server.

4. **Configure Google OAuth & SMTP (Optional for external auth/email)**
   - Update `application/config/google.php` with your Google OAuth 2.0 `client_id`, `client_secret`, and `redirect_uri` if enabling Google Sign-In.
   - Update SMTP credentials inside `application/controllers/Dashboard.php` and `application/controllers/back_end/Transaksi.php` before sending live verification or winner invoice emails.

5. **Ensure upload directories are writable**
   - Verify write permissions on `assets/foto/`, `assets/foto_produk/`, and `assets/foto_transfer/`.

## Usage

You can run the application locally using the included `router.php` script with PHP's built-in web server, or host it behind Apache using the root `.htaccess` file.

1. **Start the database server** (if using the bundled Windows batch script):
   ```powershell
   .\start_db.bat
   ```

2. **Start the PHP development server**:
   ```bash
   php -S localhost:8080 router.php
   ```

3. **Access the portals in your browser**:
   - **Public Storefront & Bidder Portal**: `http://localhost:8080/`
   - **Auctioneer Portal (`Portal Pelelang`)**: `http://localhost:8080/pelelang` (or `/dashboard`)
   - **Administrator Portal**: `http://localhost:8080/admin` (or `/dashboard/admin`)

4. **Stop the local MariaDB server** when finished (if started via batch script):
   ```powershell
   .\stop_db.bat
   ```

## API Integration

SiLelo integrates with external authentication and mail delivery services through CodeIgniter libraries to support bidder onboarding and auction lifecycle notifications.

| API / Service | Purpose | Usage |
| :--- | :--- | :--- |
| Google OAuth 2.0 (`google-login-api`) | Third-party bidder sign-in and account provisioning | Configured in `application/config/google.php` and wrapped by `application/libraries/Google.php`; invoked in `Home::register` and `User_authentication::index`. |
| SMTP Mail Service | Auctioneer verification, password reset, and winner invoice emails | Configured via CodeIgniter's `email` library inside `Dashboard::proses_daftar`, `Dashboard::proses_forgot`, and `back_end/Transaksi::pilih_pemenang`. |

## Database Configuration

The application uses a single relational database named `lelang` (`mysqli` driver configured in `application/config/database.php`) defined in `lelang.sql`. The schema contains 11 InnoDB tables covering multi-role users, auction inventory, bidding logs, escrow deposits, invoicing, reviews, and category analytics.

1. **Create the target database**:
   ```sql
   CREATE DATABASE IF NOT EXISTS `lelang` DEFAULT CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci;
   ```

2. **Import the schema and seed data**:
   ```bash
   mysql -u root lelang < lelang.sql
   ```

3. **Verify connection settings in `application/config/database.php`**:
   ```php
   $db['default'] = array(
       'hostname' => 'localhost',
       'username' => 'root',
       'password' => '',
       'database' => 'lelang',
       'dbdriver' => 'mysqli',
   );
   ```

## Authentication & Authorization

SiLelo implements role-segregated authentication and session-based authorization across three distinct user actors stored in separate tables (`users`, `abe_pelelang`, and `abe_admin`).

- **Bidder Authentication (`users`)**: Supports email/MD5 password login (`Home::login`) and Google OAuth 2.0 (`Home::register`), storing `loggedIn` and user profile attributes in CodeIgniter sessions.
- **Auctioneer Authentication (`abe_pelelang`)**: Requires email verification (`Dashboard::verification`) to transition account status from `daftar` to `aktif` before dashboard access is granted, with MD5 password reset support (`Dashboard::proses_reset`).
- **Administrator Authentication (`abe_admin`)**: Authenticates staff accounts (`administrator` and `admin` roles) via `Dashboard::proses_login_admin` and validates `status = 'aktif'`.
- **Back-Office Route Protection**: All `back_end/*` controllers (`Admin`, `Barang`, `Deposit`, `Transaksi`, `Users`) enforce constructor guards redirecting unauthenticated sessions or `bidder` roles back to `dashboard`, supplemented by role-to-menu rules in `tabel_menu` and `abe_user_rule`.

## Contributing

Contributions are welcome to improve features, security hardening, or UI refinements. Follow this standard workflow when submitting changes:

1. Fork the repository.
2. Create a feature or fix branch (`git checkout -b feature/your-feature`).
3. Make and test your changes locally against the `lelang` database.
4. Commit and push your branch (`git commit -m "feat: describe change"` and `git push origin feature/your-feature`).
5. Open a pull request with a clear explanation of the changes.

## License

This project is licensed under the MIT License.
See the [LICENSE](LICENSE) file for details.

## Author & Contact

**Yohanes Dimas Pratama**

- GitHub: [github.com/weztcy](https://github.com/weztcy)
- Portfolio: [yohanesdimas.com](https://yohanesdimas.com)
- LinkedIn: [linkedin.com/in/yohanes-dimas](https://www.linkedin.com/in/yohanes-dimas)
