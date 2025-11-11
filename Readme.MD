# VillageCryer

## Product Overview

**VillageCryer** is a hyperlocal social networking platform designed specifically for Nigerian homeowners associations (HOAs) and residential communities. It replaces fragmented WhatsApp and Facebook groups with a unified, secure, and feature-rich community platform.

### The Problem We're Solving

Nigerian residential communities currently rely on scattered communication channels:
- Multiple WhatsApp groups that become unwieldy as neighborhoods grow
- Facebook groups with poor privacy controls and content organization
- No centralized system for local businesses, events, or classifieds
- Difficulty verifying that members actually live in the neighborhood
- Lack of hyperlocal advertising opportunities for nearby businesses

### The Solution

VillageCryer provides a verified, neighborhood-based social network where:
- **Residents** connect with verified neighbors, share local news, organize events, and access hyperlocal classifieds
- **Businesses** reach specific neighborhoods with targeted advertising and maintain business pages
- **Community Leaders** manage verified members, moderate content, and maintain trust and safety
- **HOA Administrators** have centralized control with manual verification fallbacks

---

## Key Features

### MVP (Phase 1) Features

#### Epic 1: Onboarding & Identity Verification
- Multi-method address verification (SMS OTP, geolocation, physical postcard)
- Automatic neighborhood assignment based on verified address
- "Pending" to "Verified" user status workflow
- Admin manual verification fallback
- Phone number verification via Twilio (Nigerian numbers supported)

#### Epic 2: Neighborhood Discovery & Content Consumption
- Automatic assignment to specific neighborhood groups
- Hyperlocal activity feed showing content from your neighborhood
- "Nearby Neighborhoods" feature to view adjacent areas
- Clear neighborhood labeling on all posts

#### Epic 3: Engagement & Contribution
- Text posts within your neighborhood
- Comments and reactions on posts
- Event creation and management (basic functionality, extensible)
- Classifieds/marketplace powered by GeoDirectory

#### Epic 4: Trust & Safety
- Content restricted to verified neighborhood members only
- Address privacy (displays street name, hides house number)
- Manual admin verification for edge cases
- Admin capability to manually create user accounts

#### Epic 5: Private Communication
- Direct messaging between verified users
- Message notifications
- User blocking functionality

#### Epic 6: Hyperlocal Advertising Platform
**Note:** Advertising features are integrated via GeoDirectory plugins rather than separate ad platform
- Business listings in local directory
- Neighborhood-targeted business pages
- Basic ad display capabilities through GeoDirectory add-ons

#### Epic 7: Gift Cards & Community Support
- Digital gift card marketplace powered by WooCommerce
- Gift card purchase and redemption flow
- Nigerian payment methods (Paystack, Flutterwave)
- Community support use case: Send gift cards to neighbors in need

### Phase 2 Features (Fast Follow)

- **QR Code Generation & Redemption**: Enhanced gift card redemption via QR scanning
- **Advanced Event Features**: Recurring events, paid events, ticket booking
- **Enhanced GeoDirectory Features**: Business claims, reviews, featured listings, advanced directory add-ons
- **Social Login Integration**: OAuth login with post-registration verification (requires flow adjustment)

---

## Technology Stack

### Core Platform
- **CMS**: WordPress
- **Community Framework**: BuddyPress
- **Theme**: Rain Theme (BuddyPress-compatible with integrated event/GeoDirectory support)
- **Hosting**: VPS (Cloudways or RapidCloud recommended, minimum 2-4GB RAM)

### Key Plugins

#### Location & Directory
- **GeoDirectory** - Core directory functionality
- **GeoDirectory Add-ons** (as needed for MVP):
  - Classifieds functionality
  - Business listings
  - Basic advertising features
  - Location-based filtering

#### Communication & Social
- **BuddyPress** - Social networking core
- **BuddyPress Messaging** - Private messaging
- **WP SMS** - Phone verification and OTP delivery

#### E-Commerce & Payments
- **WooCommerce** - E-commerce platform
- **WooCommerce Memberships** - Access control and membership management
- **WooCommerce Gift Cards** - Gift card functionality (YITH or PW Gift Cards)
- **Paystack for WooCommerce** - Nigerian payment gateway
- **Flutterwave for WooCommerce** - Alternative Nigerian payment gateway

#### Development Tools
- **Advanced Custom Fields (ACF) Pro** - Custom field management
- **Twilio Integration** - SMS/OTP delivery

### Technical Decisions

Based on project requirements and meeting discussions:

1. **Payment Gateway**: Using Paystack and Flutterwave (Nigeria-specific) instead of international gateways
2. **Membership System**: WooCommerce Memberships replaces PM Pro to avoid dual dashboard confusion
3. **Advertising**: GeoDirectory handles business listings and ads; Advanced Ads Pro not required
4. **Social Login**: Removed from MVP due to conflicts with multi-step verification workflow
5. **Events**: Using event calendar with BuddyPress integration (specific plugin TBD based on requirements)

---

## Project Setup Requirements

### Infrastructure
- **VPS Hosting Account** (Cloudways/RapidCloud or equivalent)
  - Minimum 2-4GB RAM
  - Vertical scaling capability
  - Full server access for development team
- **Development Environment**: One development VPS (production environment created later)
- **Database**: MySQL on same VM (can be separated post-MVP)

### Plugin Licenses
Client responsibility to purchase:
- GeoDirectory Pro + required add-ons
- Rain Theme license
- ACF Pro license
- WooCommerce extension licenses (gift cards, memberships)
- Event calendar plugin license (TBD)

### Project Management
- **Platform**: Basecamp
  - Real-time chat with development team
  - Task tracking and to-do lists
  - Message boards for important updates
  - Timeline view of all activities
- **Code Repository**: GitHub (private repo)
- **Communication**: Weekly sync meetings + ad-hoc calls as needed

### Payment Gateway Setup
- **Paystack Account** - Nigerian payment processing
- **Flutterwave Account** - Backup payment option
- **API Keys** - Provided to development team for integration

---

## Scope Changes & Revised Estimates

### Original Scope (Initial Proposal - 75 Hours)

The initial development proposal covered:
- BuddyPress community setup ✓
- GeoDirectory configuration ✓
- Phone verification system via Twilio ✓
- Region-to-group mapping automation ✓
- Address-based neighborhood assignment ✓
- Manual verification workflow ✓
- Basic access control ✓
- Activity streams and community features ✓

### What's Actually NEW (Not in Original Scope)

Based on the story map document and meeting discussions, these features are genuinely new additions:

#### Truly New Features Added to MVP:

**Epic 3 - Event Calendar (+6-8 hours):**
- Event calendar integration with BuddyPress (6-8 hours)
  - Event plugin selection and installation
  - BuddyPress integration setup
  - Basic event creation interface
  - RSVP/registration system
  - Calendar view implementation
- **Note:** Basic event functionality; advanced features (recurring, paid, booking) would add 6-12 more hours if needed

**Epic 6 - Advertising Features (+2-3 hours):**
- GeoDirectory advertising add-ons configuration (2-3 hours)
  - Ad campaign dashboard setup
  - Neighborhood targeting configuration
  - Basic analytics integration
- **Note:** Core GeoDirectory was already in scope; this is just additional add-ons

**Epic 7 - WooCommerce & Gift Cards (+15-18 hours):**
- WooCommerce installation and configuration (3 hours)
- WooCommerce Memberships setup (replacing PM Pro decision) (3 hours)
- Gift card plugin integration (YITH or PW Gift Cards) (4 hours)
- Paystack payment gateway integration (3 hours)
- Flutterwave payment gateway integration (2-3 hours)

**Enhanced Wireframe Implementation (+4-5 hours):**
- Landing page customization per client wireframes (2 hours)
- Multi-step registration UI refinement (2-3 hours)
- **Note:** Basic registration flow was already planned; this is client-specific UI polish

**Comprehensive Documentation (+3 hours):**
- Detailed user flow documentation (2 hours)
- Expanded admin training materials (1 hour)

### Revised Total Estimate

| Category | Original Hours | Added Hours | Total Hours |
|----------|---------------|-------------|-------------|
| **Core Development (Original)** | 75 | - | 75 |
| **Event Calendar** | - | 6-8 | 6-8 |
| **GeoDirectory Advertising Add-ons** | - | 2-3 | 2-3 |
| **WooCommerce & Gift Cards** | - | 15-18 | 15-18 |
| **Wireframe Polish** | - | 4-5 | 4-5 |
| **Enhanced Documentation** | - | 3 | 3 |
| **REVISED TOTAL** | **75** | **30-37** | **105-112 hours** |

### What Was ALREADY Covered (No Extra Hours):

- ✓ BuddyPress setup and configuration
- ✓ GeoDirectory core installation and basic configuration
- ✓ Phone/SMS verification system
- ✓ Region-to-group mapping automation
- ✓ Activity feed and posting
- ✓ Direct messaging (BuddyPress native)
- ✓ User blocking (BuddyPress native)
- ✓ Comments and reactions (BuddyPress native)
- ✓ Access control and verification badges
- ✓ Manual admin verification workflow
- ✓ Address privacy settings
- ✓ Basic classifieds (GeoDirectory core feature)
- ✓ Business listings (GeoDirectory core feature)

### Items Requiring Client Clarification (May Add Hours)

These items need specification before final hours can be confirmed:

1. **Event Calendar Requirements (Task #13)**
   - Basic events only? (already included in 6-8 hours)
   - Recurring events support? (adds 3-4 hours)
   - Paid events with ticketing? (adds 4-5 hours)
   - Advanced booking/seat limits? (adds 3-4 hours)
   - **Potential additional hours:** 0-13 hours depending on selections

2. **GeoDirectory Add-ons (Task #16)**
   - Basic directory already included in original scope
   - Select additional add-ons from 28+ options if needed:
     - Reviews & Ratings (2-3 hours)
     - Claims/Verification (2-3 hours)
     - Featured Listings (1-2 hours)
     - Advanced Search (2-3 hours)
   - **Potential additional hours:** 0-10 hours for advanced add-ons

3. **Custom Wireframe Adjustments**
   - Basic wireframe implementation included (4-5 hours)
   - Significant custom UI beyond Rain theme would add hours
   - **Potential additional hours:** 0-8 hours for major customizations

**Important Note:** The revised estimate of **105-112 hours** represents the realistic scope based on genuinely new features. Final hours may increase by 0-30 hours depending on client selections for advanced event features and GeoDirectory add-ons.

---

## Development Roadmap

### Timeline Overview
- **MVP Duration**: 6-7 weeks (105-112 hours revised estimate, up from 75 hours baseline)
- **Team Size**: 3 developers (Senior WordPress Developer, BuddyPress Specialist, Frontend Developer)
- **Scope Change Impact**: +30-37 hours for events, WooCommerce/gift cards, and payment gateways

### Phased Approach (Revised)

**Week 1-2**: Foundation, verification systems, user onboarding (20 hours)
- Server setup, WordPress installation
- BuddyPress and GeoDirectory configuration
- Phone verification system
- Custom registration workflow

**Week 3-4**: Location management, neighborhood assignment (20 hours)
- Region-to-group mapping automation
- KML boundary import
- Address geocoding and assignment
- Manual verification dashboard

**Week 5**: Community features and access control (15 hours)
- Activity stream customization
- Content restrictions
- Privacy settings
- Neighborhood-based filtering

**Week 6**: NEW - Events, WooCommerce, Gift Cards (25 hours)
- Event calendar integration (6-8 hours)
- WooCommerce installation and configuration (3 hours)
- Gift card plugin setup (4 hours)
- Paystack + Flutterwave payment gateways (5-6 hours)
- GeoDirectory advertising add-ons (2-3 hours)
- Wireframe polish (4-5 hours)

**Week 7**: Testing, optimization, training, documentation (20-22 hours)
- Integration testing
- Performance optimization
- Admin training and documentation
- User flow documentation
- Launch preparation

**Post-MVP**: Phase 2 features (QR codes, advanced events, enhanced directory features)

---

## Development Phases (Technical Implementation)

### Phase 1: Foundation & Setup (16 hours)

| Task | Hours | Details |
|------|-------|---------|
| **Server & WordPress Setup** | 3 | Server configuration, WordPress installation, Performance optimization |
| **Plugin Installation & Configuration** | 6 | BuddyPress setup, GeoDirectory configuration, ACF Pro setup, WP SMS installation, Reign theme configuration |
| **Initial Theme Customization** | 3 | Reign theme branding, Basic layout adjustments, Mobile responsiveness check |

**Note**: Social login removed from MVP scope

### Phase 2: Custom Development - User Verification (23 hours)

| Task | Hours | Details |
|------|-------|---------|
| **Custom Registration Form** | 5 | Multi-step form development, ACF field integration, Address collection UI |
| **Phone Verification System** | 9 | OTP generation logic, Twilio API integration, SMS sending functionality, Code validation system, Error handling |
| **Manual Verification Workflow** | 5 | Admin notification system, Document upload feature, Approval interface, Status tracking system |
| **User Profile Enhancements** | 4 | Street name extraction algorithm, Privacy display settings, Verification badge display, Custom profile fields |

### Phase 3: Custom Development - Location Management (21 hours)

| Task | Hours | Details |
|------|-------|---------|
| **Region-to-Group Mapping System** | 9 | Automatic group creation, Synchronization logic, Permission inheritance, Member auto-assignment |
| **KML Import & Boundary Setup** | 4 | Import interface setup, 5 pilot neighborhood boundaries, Validation system |
| **Address-to-Region Assignment** | 6 | Geocoding integration, Coordinate matching algorithm, Boundary detection logic, Edge case handling |
| **Location Display Integration** | 2 | Map visualization, User location indicators, Privacy controls |

### Phase 4: Custom Development - Community Features (10 hours)

| Task | Hours | Details |
|------|-------|---------|
| **Access Control System** | 4 | Verified-only content restrictions, Neighborhood-based filtering, Guest access limitations |
| **Group Configuration** | 3 | Auto-join functionality, Privacy settings, Admin tool customization |
| **Activity Stream Customization** | 3 | Neighborhood-specific feeds, Content filtering rules, Visibility controls |

### Phase 5: Testing & Launch (5 hours)

| Task | Hours | Details |
|------|-------|---------|
| **Integration Testing** | 2 | Full workflow testing, Cross-browser checks |
| **Performance Optimization** | 1 | Caching setup, Database optimization |
| **Admin Training & Documentation** | 2 | Video walkthrough, Admin guide creation, Launch preparation |

---

## Custom Development Summary

### Core Custom Features (Total: 49 hours)

1. **Phone Verification System (9 hours)**
   - Custom OTP generation and validation
   - Twilio API integration
   - Verification status management
   - SMS retry logic
   - Nigerian phone number validation

2. **Region-to-Group Mapping (9 hours)**
   - Automatic BuddyPress group creation from GeoDirectory regions
   - Bidirectional synchronization
   - Permission inheritance system
   - Bulk operations support
   - Group metadata management

3. **Address-to-Region Assignment (6 hours)**
   - Smart geocoding algorithm
   - Polygon boundary detection
   - Fallback mechanisms for edge cases
   - Manual override options

4. **Manual Verification Workflow (5 hours)**
   - Custom admin interface
   - Document management system
   - Approval queue management
   - Email notifications

5. **Custom Registration System (5 hours)**
   - Multi-step form with validation
   - Progressive data collection
   - Error recovery
   - Status tracking

6. **User Profile Enhancements (4 hours)**
   - Street name parser
   - Privacy level controls
   - Verification status display
   - Custom field handlers

7. **Access Control System (4 hours)**
   - Content restriction engine
   - Neighborhood-based permissions
   - Role-based access control
   - Guest limitation logic

8. **Activity Stream Filters (3 hours)**
   - Location-based filtering
   - Privacy-aware queries
   - Performance optimization

9. **Other Custom Work (4 hours)**
   - Admin dashboard widgets
   - Custom notifications
   - API endpoints
   - Helper utilities

---

## Technical Architecture

### Custom Development Highlights

**Phone Verification Flow:**
```
User Registration → Generate OTP → Send SMS via Twilio →
Validate Code → Update Status → Grant Access
```

**Region-Group Mapping:**
```
Create Region in GeoDirectory → Trigger Custom Hook →
Auto-create BuddyPress Group → Sync Permissions →
Enable Auto-join
```

**Address Assignment:**
```
User Submits Address → Geocode to Coordinates →
Check Against KML Boundaries → Assign to Region →
Add to Corresponding Group
```

**Payment Flow (Gift Cards):**
```
Browse Gift Cards → Add to Cart → Checkout via WooCommerce →
Pay with Paystack/Flutterwave → Receive Digital Gift Card →
Send to Recipient or Redeem
```

---

## Development Environment Strategy

Since we're working directly on the live site as development:

### Security Measures
- Password-protected site during development
- Maintenance mode plugin active
- Regular backups before major changes
- IP whitelist for development team

### Advantages
- No staging-to-production migration needed
- Real-time client visibility
- Immediate testing with actual data
- Faster development cycle
- 2 hours saved for other custom features

---

## Deliverables

Upon MVP completion, you will receive:
- Fully functional VillageCryer MVP
- Custom phone verification system with Nigerian number support
- Automated region-to-group mapping
- Address-based neighborhood assignment
- GeoDirectory integration for classifieds and business listings
- WooCommerce gift card system with Nigerian payment gateways
- Admin training and documentation
- 30-day post-launch support

---

## User Flows & Wireframes

This section documents all key user journeys through the VillageCryer platform to ensure consistent implementation.

### 1. Landing Page Flow

**Purpose**: First-time visitor introduction to VillageCryer

**Flow:**
```
Visitor arrives at landing page
    ↓
View hero section: "What is VillageCryer?"
    ↓
Scroll to see sections:
    - Why Join? (Benefits)
    - How It Works (Process overview)
    - Testimonials/Social Proof
    ↓
Call-to-Action: "Sign Up" or "Login"
```

**Key Elements:**
- Mobile-first design (primary Nigerian user device)
- Clear value proposition visible above the fold
- Trust indicators (security, privacy, verification)
- Localized content for Nigerian audience

---

### 2. User Registration & Onboarding Flow

**Purpose**: New user sign-up with multi-step verification

**Flow:**
```
Click "Sign Up" from landing page
    ↓
STEP 1: Basic Information
    - First Name
    - Last Name
    - Email Address
    - Phone Number (Nigerian format)
    - Password
    → Click "Continue"
    ↓
STEP 2: Address Collection
    - Full Street Address
    - City
    - State
    - Postal Code (if applicable)
    → System performs initial geocoding
    → Click "Continue"
    ↓
STEP 3: Verification Method Selection
    User selects ONE method:
    ☐ SMS OTP (instant)
    ☐ Location Check (geolocation-based)
    ☐ Physical Postcard (3-5 days)
    → Click "Verify Address"
    ↓
STEP 4A: SMS OTP Verification
    - System sends 6-digit code to phone
    - User enters code
    - System validates within 10 minutes
    → Success: User status = "Verified"

STEP 4B: Geolocation Verification
    - User grants location permission
    - System checks GPS coordinates against KML boundaries
    - System matches to neighborhood
    → Success: User status = "Verified"

STEP 4C: Postcard Verification
    - System calls Lob.com API
    - Physical postcard sent with code
    - User receives postcard (3-5 days)
    - User enters code from postcard
    → Success: User status = "Verified"
    ↓
STEP 5: Automatic Neighborhood Assignment
    - System assigns user to BuddyPress group based on address
    - User auto-joins neighborhood group
    - Welcome message displayed
    ↓
Redirect to Main Activity Feed
```

**Fallback Flow - Manual Verification:**
```
If automated verification fails:
    ↓
User status = "Pending"
    ↓
Admin receives notification in dashboard
    ↓
User can upload documents (utility bill, ID)
    ↓
Admin reviews and manually approves/rejects
    ↓
User receives email notification of decision
    ↓
If approved: Status = "Verified" + neighborhood assignment
```

**Important Notes:**
- Social login removed from MVP (conflicts with verification steps)
- All verification methods require address input first
- User cannot access community features until verified

---

### 3. Main Activity Feed Flow

**Purpose**: Verified user's primary interaction space

**Flow:**
```
User logs in (email + password)
    ↓
Lands on Activity Feed (Homepage)
    ↓
Feed displays:
    ├─ Posts from MY neighborhood (primary)
    ├─ Neighborhood label on each post
    ├─ "Nearby Neighborhoods" tab (optional viewing)
    └─ Verification badges on user avatars
    ↓
User Actions Available:
    ├─ Create new text post
    ├─ Add photos/media to post
    ├─ Comment on posts
    ├─ React to posts (like, love, etc.)
    ├─ Share posts within neighborhood
    └─ Direct message verified users
    ↓
Filtering Options:
    ├─ My Neighborhood (default)
    ├─ Nearby Neighborhoods
    ├─ Following (specific users)
    └─ Post type (events, classifieds, general)
```

**Key Features:**
- Mobile-responsive layout (mobile-first)
- Infinite scroll for feed
- Real-time notifications
- Dark mode / Light mode toggle
- Verification badge always visible

---

### 4. Event Creation & Management Flow

**Purpose**: Community members create and manage local events

**Flow:**
```
User clicks "Create Event" from activity feed
    ↓
Event Creation Form:
    ├─ Event Title
    ├─ Event Description
    ├─ Event Date & Time
    ├─ Event Location (within neighborhood)
    ├─ Event Type: [TBD - requires client clarification]
    │   - Free Event
    │   - Paid Event (if applicable)
    │   - Recurring Event (if applicable)
    │   - Booking/RSVP Required
    └─ Event Image (optional)
    ↓
Visibility Settings:
    ├─ My Neighborhood Only (default)
    └─ Nearby Neighborhoods (optional)
    ↓
Click "Publish Event"
    ↓
Event appears in:
    ├─ Activity Feed (post format)
    ├─ Neighborhood Calendar View
    └─ Event Listings Page
    ↓
Attendees can:
    ├─ RSVP / Register
    ├─ Comment on event
    ├─ Share event
    └─ Add to personal calendar
```

**Note**: Event plugin selection pending client requirements clarification (Task #13)

---

### 5. Classifieds & Marketplace Flow

**Purpose**: Neighborhood members buy/sell/trade locally

**Flow:**
```
User clicks "Post Classified" or "Browse Marketplace"
    ↓
CREATE CLASSIFIED:
    ├─ Category Selection (GeoDirectory categories)
    │   - For Sale
    │   - Services
    │   - Housing
    │   - Jobs
    │   - Free Items
    ├─ Title
    ├─ Description
    ├─ Price (if applicable)
    ├─ Photos (up to X images)
    ├─ Contact Method (phone, email, DM)
    └─ Listing Duration (30/60/90 days)
    ↓
Visibility:
    ├─ My Neighborhood Only (default)
    └─ Extended Range (X km radius)
    ↓
Click "Publish Listing"
    ↓
BROWSE CLASSIFIEDS:
    ├─ Filter by Category
    ├─ Filter by Distance
    ├─ Filter by Price Range
    ├─ Search by Keywords
    └─ Sort by Date/Price/Distance
    ↓
User Actions:
    ├─ View listing details
    ├─ Contact seller (verified users only)
    ├─ Flag inappropriate listings
    └─ Share listing
```

**Note**: Powered by GeoDirectory. Specific add-ons pending client confirmation (Task #16)

---

### 6. Business Listings & Advertising Flow

**Purpose**: Local businesses reach neighborhood residents

**Flow:**
```
BUSINESS OWNER PERSPECTIVE:
    ↓
Create Business Page (via GeoDirectory)
    ├─ Business Name
    ├─ Business Category
    ├─ Business Address (must be local)
    ├─ Business Description
    ├─ Hours of Operation
    ├─ Contact Information
    ├─ Photos/Logo
    └─ Social Media Links
    ↓
Business Page Options:
    ├─ Free Basic Listing
    └─ Featured/Premium Listing (paid)
    ↓
CREATE AD CAMPAIGN:
    ├─ Ad Creative (image + text)
    ├─ Target Neighborhoods (select from list)
    ├─ Target Radius (X km from business)
    ├─ Campaign Duration
    ├─ Budget/Pricing Model:
    │   - CPM (cost per thousand impressions)
    │   - CPC (cost per click)
    │   - Flat Fee (monthly)
    └─ Ad Placement (feed, sidebar, featured)
    ↓
Submit for Approval (admin review)
    ↓
Ad Goes Live
    ↓
ADVERTISER DASHBOARD:
    ├─ View impressions
    ├─ View clicks
    ├─ View engagement metrics
    ├─ Pause/Resume campaign
    └─ Edit campaign
    ↓
RESIDENT PERSPECTIVE:
    ├─ See ads in activity feed (labeled as "Sponsored")
    ├─ See featured businesses in directory
    ├─ Click to visit business page
    ├─ Follow businesses organically
    └─ Can hide/report inappropriate ads
```

**Note**: Advertising handled via GeoDirectory add-ons (replaces Advanced Ads Pro)

---

### 7. Gift Card Purchase & Redemption Flow

**Purpose**: Community support and business gifting

**Flow:**
```
PURCHASER PERSPECTIVE:
    ↓
Browse Gift Card Marketplace
    ├─ Local Business Gift Cards
    ├─ General Store Credit
    └─ Community Support Fund Cards
    ↓
Select Gift Card:
    ├─ Choose business
    ├─ Select amount
    ├─ Add personal message (optional)
    └─ Add to cart
    ↓
Checkout via WooCommerce:
    ├─ Review cart
    ├─ Enter recipient details:
    │   - Recipient name
    │   - Recipient email or username
    │   - Delivery date (now or scheduled)
    └─ Select payment method
    ↓
PAYMENT:
    ├─ Paystack (primary - Nigerian)
    ├─ Flutterwave (backup - Nigerian)
    └─ Process payment
    ↓
Gift Card Issued:
    ├─ Digital gift card generated
    ├─ Unique code created
    ├─ Sent to recipient via email/DM
    └─ Purchaser receives confirmation
    ↓
RECIPIENT PERSPECTIVE:
    ↓
Receives gift card notification
    ├─ Email with gift card details
    └─ In-app notification
    ↓
View Gift Card:
    ├─ Gift card code visible
    ├─ Balance displayed
    ├─ Business details
    └─ Redemption instructions
    ↓
REDEEM GIFT CARD:
Method 1 - Online:
    ├─ Visit business page
    ├─ Add items to cart
    ├─ Enter gift card code at checkout
    └─ Balance applied

Method 2 - In Person:
    ├─ Show gift card code to business
    ├─ Business enters code in system
    └─ Balance deducted

Method 3 - QR Code (Phase 2):
    ├─ Scan QR code at business
    └─ Automatic redemption
    ↓
COMMUNITY SUPPORT USE CASE:
    ├─ Neighbor in need identified
    ├─ Community members contribute to fund
    ├─ Gift card(s) purchased collectively
    └─ Sent to neighbor anonymously (optional)
```

**Special Features:**
- Nigerian payment methods (Paystack, Flutterwave)
- User-to-user gifting within verified community
- Community fund pooling for support
- QR redemption in Phase 2

---

### 8. Direct Messaging Flow

**Purpose**: Private communication between verified neighbors

**Flow:**
```
User clicks "Message" on another verified user's profile
    ↓
Message Compose Screen:
    ├─ Recipient name (verified badge shown)
    ├─ Message text box
    ├─ Attach media (optional)
    └─ Send button
    ↓
Message Sent
    ↓
Recipient Receives:
    ├─ In-app notification
    ├─ Email notification (if enabled)
    └─ Push notification (if enabled)
    ↓
Recipient Can:
    ├─ Reply to message
    ├─ Block sender (if unwanted)
    └─ Report abuse (if inappropriate)
    ↓
Conversation Thread:
    ├─ Real-time messaging
    ├─ Message history preserved
    └─ Read receipts (optional)
```

**Privacy & Safety:**
- Only verified users can DM each other
- Users can block at any time
- Report feature for inappropriate messages
- Admin can review reported conversations

---

### 9. Admin Manual Verification Flow

**Purpose**: Admin fallback for edge cases where automated verification fails

**Flow:**
```
ADMIN DASHBOARD:
    ↓
View "Pending Verifications" Queue
    ├─ List of users awaiting manual review
    ├─ Sort by submission date
    └─ Filter by verification attempt type
    ↓
Select User to Review:
    ↓
View User Details:
    ├─ Submitted address
    ├─ Phone number
    ├─ Uploaded documents (utility bill, ID, etc.)
    ├─ Verification attempt history
    ├─ Geocoded location (if available)
    └─ Notes from user
    ↓
Admin Actions:
    ├─ Approve Verification
    │   → Select neighborhood manually
    │   → User status = "Verified"
    │   → Add to neighborhood group
    │   → Send approval email
    │
    ├─ Reject Verification
    │   → Add rejection reason
    │   → Send rejection email
    │   → User can re-submit
    │
    ├─ Request More Information
    │   → Send message to user
    │   → Keep status as "Pending"
    │
    └─ Manually Create Account (special cases)
        → Enter all user details
        → Skip automated verification
        → Directly assign to neighborhood
        → Set as "Verified"
```

**Admin Tools:**
- Bulk approve/reject options
- Search/filter pending users
- Verification history log
- Communication templates
- Neighborhood assignment override

---

### 10. Region-to-Group Mapping (Background Process)

**Purpose**: Automated synchronization between GeoDirectory regions and BuddyPress groups

**Technical Flow:**
```
Admin creates Region in GeoDirectory
    ↓
Custom Hook Triggered: "geodir_region_created"
    ↓
System Actions:
    ├─ Check if BuddyPress group exists for this region
    ├─ If NOT exists:
    │   → Create new BuddyPress group
    │   → Name: [Region Name]
    │   → Description: Auto-generated
    │   → Privacy: Private (verified members only)
    │   → Auto-join: Enabled for verified residents
    │   → Sync metadata (region ID, boundaries, etc.)
    │
    └─ If exists:
        → Update group metadata
        → Sync any changes (name, description)
    ↓
User Verification Completes:
    ↓
System geocodes user address
    ↓
System matches coordinates to KML boundaries
    ↓
Finds matching region
    ↓
Auto-adds user to corresponding BuddyPress group
    ↓
User sees neighborhood in "My Groups"
    ↓
User receives welcome notification
```

**Bidirectional Sync:**
- Region changes in GeoDirectory → Update BuddyPress group
- Group settings in BuddyPress → Update GeoDirectory metadata
- Member additions/removals stay in sync

---

## Wireframe Locations

**Note**: Client has provided wireframes for key flows. Reference wireframes for:
- Landing page (desktop & mobile)
- Sign-up flow (multi-step)
- Verification method selection
- Main activity feed (logged-in state)
- Event creation modal
- Classifieds posting form
- Gift card purchase flow

These wireframes should be stored in the project repository under `/docs/wireframes/` for developer reference.

---

## User Experience Design Principles

The platform follows BuddyPress/Rain theme UX patterns:
- Mobile-first design (most Nigerian users access via mobile)
- Activity feed similar to familiar social networks
- Dark mode and light mode support
- Familiar interaction patterns (like, comment, share)
- Intuitive member profiles with verification badges
- Seamless neighborhood-based content filtering

For UI reference, see Rain Theme demo: https://wbcomdesigns.com/downloads/reign-buddypress-theme/

---

## Pending Client Decisions

The following items require client input before development can proceed at full speed:

### High Priority Decisions Needed:

**1. Event Calendar Specifications (Task #13)**
- Which event features are required for MVP?
  - [ ] Basic events (date, time, location, RSVP)
  - [ ] Recurring events (weekly, monthly)
  - [ ] Paid events with ticketing
  - [ ] Booking/seat limit functionality
  - [ ] External calendar sync (Google Calendar, etc.)
- Preferred plugin based on requirements
- **Impact on timeline:** 3-12 additional hours depending on selections

**2. GeoDirectory Add-on Selection (Task #16)**
- Client must review 28+ available GeoDirectory add-ons
- Select which add-ons are needed for MVP:
  - [ ] Claims (business verification)
  - [ ] Reviews & Ratings
  - [ ] Featured Listings
  - [ ] Advanced Search
  - [ ] Payment integration
  - [ ] Custom fields
  - [ ] Others (to be specified)
- **Impact on timeline:** 3-15 additional hours depending on selections

**3. Payment Gateway Testing Credentials**
- Paystack sandbox/test account details
- Flutterwave sandbox/test account details
- **Required for:** Testing payment flows before launch

**4. Hosting Setup**
- VPS hosting provider selection (Cloudways/RapidCloud recommended)
- Server access credentials
- **Required to begin:** Foundation & Setup phase (Week 1)

**5. Plugin License Procurement**
- GeoDirectory Pro + selected add-ons
- Rain Theme license
- ACF Pro license
- WooCommerce extensions (Gift Cards, Memberships)
- Event calendar plugin (TBD after requirements)
- **Required for:** Plugin configuration phase

### Medium Priority Decisions:

**6. Wireframe Finalization**
- Review and approve current wireframes
- Identify any custom UI requirements beyond Rain theme
- **Impact on timeline:** 5-10 hours for significant customizations

**7. Content & Branding**
- Site logo and branding assets
- Landing page copy
- Welcome email templates
- **Can be added during development**

**8. KML Boundaries**
- Provide KML files for 5 pilot neighborhoods
- Verify boundary accuracy
- **Required for:** Address verification testing

---

## Why This Distribution Works

### Revised Approach (105-112 Hours):

1. **Realistic Scope Assessment:** 75 hours for core features + 30-37 hours for genuinely new requirements
2. **Most Features Already Covered:** BuddyPress, GeoDirectory, verification system were in original scope
3. **Focus on True Additions:** Events calendar, WooCommerce/gift cards, Nigerian payment gateways are the real additions
4. **E-Commerce Foundation:** WooCommerce provides scalability for future monetization
5. **Nigerian Market Focus:** Paystack/Flutterwave payment gateways tailored for Nigeria
6. **Efficient Delivery:** 6-7 week timeline leverages existing plugin capabilities
7. **Scalable Architecture:** GeoDirectory and WooCommerce provide extensibility for Phase 2 features

### Hour Distribution Breakdown:

| Phase | Original | Added | Total | Percentage |
|-------|----------|-------|-------|------------|
| **Setup & Foundation** | 16 | 0 | 16 | 15% |
| **User Verification** | 23 | 0 | 23 | 21% |
| **Location Management** | 21 | 0 | 21 | 19% |
| **Community Features** | 10 | 2-3 | 12-13 | 11% |
| **Events Calendar (NEW)** | 0 | 6-8 | 6-8 | 6% |
| **WooCommerce & Gift Cards (NEW)** | 0 | 15-18 | 15-18 | 15% |
| **Wireframe Polish (NEW)** | 0 | 4-5 | 4-5 | 4% |
| **Testing & Documentation** | 5 | 3 | 8 | 7% |
| **TOTAL** | **75** | **30-37** | **105-112** | **100%** |

### What This Means:

- **40% increase** in hours (not doubling), reflecting truly new features only
- Most story map features were already anticipated in original proposal
- BuddyPress and GeoDirectory handle majority of Epic 1-6 features natively
- Only Epic 7 (gift cards/e-commerce) is significantly new work
- Event calendar is a straightforward plugin integration

### Risk Mitigation:

- Complex features (verification, mapping) already allocated adequate time in original scope
- New features are plugin-based (WooCommerce, events) reducing custom development risk
- Client clarification checkpoints for advanced features (recurring events, advanced GeoDirectory add-ons)
- Phased approach allows for course correction
- Regular Basecamp updates and weekly sync meetings
- Buffer for additional requirements: 0-30 hours depending on client selections

---

*This document combines product vision with technical implementation strategy. The revised 105-112 hour estimate (up from 75 hours baseline by 40%) accurately reflects genuinely new features from the story map. Most features were already covered by the original BuddyPress + GeoDirectory scope. Final hours may increase by 0-30 hours pending client clarifications on event features and GeoDirectory add-ons.*
