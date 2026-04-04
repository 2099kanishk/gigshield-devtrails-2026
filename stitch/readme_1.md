# GigShield 🛡️
## AI-Powered Parametric Insurance for Zepto Q-Commerce Delivery Partners

**Guidewire DEVTrails 2026 | Phase 1: Ideation & Foundation**

> Insurance that works as fast as your delivery

---

## 📋 Table of Contents
- [Problem Statement](#-problem-statement)
- [Persona & Scenarios](#-persona--scenarios)
- [Solution Overview](#-solution-overview)
- [Application Workflow](#-application-workflow)
- [Weekly Premium Model](#-weekly-premium-model)
- [Parametric Triggers](#-parametric-triggers)
- [Platform Choice: Web vs Mobile](#-platform-choice-web-vs-mobile)
- [AI/ML Integration Plan](#-aiml-integration-plan)
- [Technology Stack](#-technology-stack)
- [Development Plan](#-development-plan)
- [Team](#-team)

---

## 🎯 Problem Statement

India's Q-commerce delivery partners, particularly those working with **Zepto**, face significant income loss due to external disruptions beyond their control:

- **Environmental**: Heavy rain, extreme heat, severe pollution
- **Social**: Curfews, strikes, zone closures  
- **Technical**: Platform outages, payment failures

**Impact**: Partners lose 20-30% of monthly income (₹5,000-10,000) with **zero safety net**.

**GigShield addresses this gap** by providing AI-powered, zero-touch income protection through parametric insurance.

---

## 👤 Persona & Scenarios

### Selected Persona: Zepto Q-Commerce Delivery Partner

**Why Zepto?**
1. **Highest trip frequency**: 15-25 deliveries/day (vs 8-12 for food delivery)
2. **Strictest time windows**: 10-minute delivery slots = immediate income impact
3. **Hyper-local operations**: 2-3 km radius enables granular pricing
4. **Peak hour dependency**: 70% earnings concentrated in 6-10 PM slot

### Typical Partner Profile

| Attribute | Details |
|-----------|---------|
| **Name** | Rahul Kumar |
| **Age** | 22 years |
| **Base Location** | Andheri, Mumbai |
| **Weekly Income** | ₹6,500-7,500 |
| **Work Hours** | 10 hours/day, 6 days/week |
| **Primary Zones** | 3 pin codes (400053, 400058, 400061) |
| **Vehicle** | Electric scooter (leased) |

### Real-World Scenarios

#### **Scenario 1: Heavy Monsoon Rain**
**Date**: July 18, 2026 | **Location**: Andheri, Mumbai

**Normal Evening (6-10 PM)**:
- Orders: 22 × ₹55 = ₹1,210

**Rainy Day (Rainfall: 28mm in 3 hours)**:
- Orders: 7 × ₹55 = ₹385 (roads waterlogged, customers cancel)
- **Income Loss**: ₹825

**GigShield Response**:
- OpenWeatherMap API detects 28mm rainfall (trigger: >20mm)
- System auto-creates claim
- GPS validates partner in affected zone
- **Payout**: ₹825 to UPI in 15 minutes

---

#### **Scenario 2: Extreme Heatwave**
**Date**: May 22, 2026 | **Location**: Delhi NCR

**Normal Lunch (12-2 PM)**:
- Orders: 12 × ₹50 = ₹600

**Heatwave (44°C, Zepto safety advisory)**:
- Orders: 0 (partner stays indoors)
- **Income Loss**: ₹600

**GigShield Response**:
- IMD API reports 44°C (trigger: >40°C)
- **Payout**: ₹300 (50% coverage for safety hours)

---

#### **Scenario 3: Platform Outage**
**Date**: March 10, 2026 | **Location**: Bangalore

**Peak Dinner (7:30-9 PM)**:
- Expected: 12 orders × ₹60 = ₹720

**App Down (90 minutes)**:
- Actual: ₹0
- **Income Loss**: ₹720

**GigShield Response**:
- Mock status API detects outage >30 min
- **Payout**: ₹720 (hourly rate × duration)

---

## 💡 Solution Overview

**GigShield** provides:

✅ **Zero-touch claims**: Automatic trigger detection → payout  
✅ **Weekly pricing**: ₹40-90/week based on AI risk assessment  
✅ **15-minute payouts**: From trigger to UPI credit  
✅ **Income loss only**: No health/vehicle/accident coverage  
✅ **Fraud prevention**: Multi-layer ML validation  

### Value Proposition
- **For Partners**: Financial safety net, weekly affordability
- **For Zepto**: Improved partner retention
- **For Insurers**: Scalable, data-driven parametric model

---

## 🔄 Application Workflow

### Partner Journey

```
1. ONBOARDING (2 minutes)
   ├─ Phone OTP verification / Google OAuth
   ├─ Select primary delivery zone (pin code)
   ├─ Link UPI ID for auto-debit & payouts
   └─ View AI-generated weekly premium quote
   
2. POLICY PURCHASE (30 seconds)
   ├─ Review premium (base + risk multiplier)
   ├─ See coverage (triggers, max payouts)
   ├─ One-click purchase
   ├─ Policy active for 7 days
   └─ SMS confirmation sent
   
3. DAILY OPERATION (Zero effort)
   ├─ System monitors 5 triggers 24/7
   ├─ AI validates disruptions real-time
   └─ Partner works normally
   
4. CLAIM PROCESSING (15 minutes)
   ├─ Trigger detected (API)
   ├─ Auto-claim creation
   ├─ Fraud validation (GPS, activity, duplicates)
   ├─ Payout calculation
   ├─ UPI transfer
   └─ Push notification sent
   
5. RENEWAL (Day 5)
   ├─ SMS reminder: "Policy expires in 2 days"
   ├─ Auto-renew / manual skip option
   └─ New premium based on updated risk
```

### Admin Dashboard Views

```
ADMIN DASHBOARD
├─ Real-Time Metrics
│  ├─ Active policies count
│  ├─ Weekly premiums collected
│  ├─ Weekly payouts
│  └─ Loss ratio (target: 60-70%)
│
├─ Zone Risk Heatmap
│  ├─ Color-coded map
│  ├─ 7-day disruption probability
│  └─ High-risk alerts
│
├─ Predictive Analytics
│  ├─ Expected claim volume (next week)
│  ├─ Premium adjustment suggestions
│  └─ Seasonal trends
│
└─ Fraud Alerts
   ├─ Flagged claims list
   ├─ Fraud reason breakdown
   └─ Manual review queue
```

---

## 💰 Weekly Premium Model

### Why Weekly?
- Aligns with Zepto's weekly payout cycle
- Lower barrier (₹60 vs ₹240/month)
- Flexibility to skip low-risk weeks

### Pricing Formula

```
Final Premium = Base Premium (₹50) × AI Risk Multiplier (0.6-2.0)
```

### XGBoost Model Inputs (15 features)

| Category | Features |
|----------|----------|
| **Weather Forecast** | 7-day rain probability, max temperature, min AQI |
| **Historical Claims** | Zone claim rate (30-day, 90-day) |
| **Seasonal** | Is monsoon (Jun-Sep), Is summer (Apr-May) |
| **Zone-Specific** | Flood history score, avg pollution |
| **Platform** | Outage frequency, festive demand multiplier |
| **Partner** | Tenure weeks (loyalty discount) |

### Example Pricing

| Zone | Location | Weather | History | **Premium** | Multiplier |
|------|----------|---------|---------|-------------|------------|
| Low Risk | Koramangala, BLR | Low rain | 2 claims/90d | **₹40/week** | 0.8× |
| Medium | Indiranagar, BLR | Moderate | 8 claims/90d | **₹60/week** | 1.2× |
| High Risk | Andheri, Mumbai | High rain | 22 claims/90d | **₹75/week** | 1.5× |
| Extreme | Delhi NCR | Heatwave | 15 claims/90d | **₹90/week** | 1.8× |

### Coverage Details
- **Period**: 7 days from purchase
- **Max Payout/Week**: ₹3,500 (50% of median weekly income)
- **Renewal**: Auto-renew with 2-day SMS reminder
- **Payment**: UPI auto-debit

### Business Viability
**Target Loss Ratio**: 60-70% (industry standard for parametric)

**Example (1,000 partners)**:
- Weekly premiums: 1,000 × ₹60 = ₹60,000
- Target payouts: ₹42,000 (70%)
- Operating margin: ₹18,000/week
- **Annual revenue**: ₹31.2 lakh (sustainable)

---

## ⚡ Parametric Triggers

### What is Parametric Insurance?

**Traditional**: Partner files claim → Documents → Manual verification → 7-15 days

**Parametric (GigShield)**: Objective trigger detected → Auto-verification → 15 minutes

### Trigger Definitions

| Trigger | Condition | Data Source | Payout Logic | Max Payout |
|---------|-----------|-------------|--------------|------------|
| **Heavy Rain** | >20mm in 3 hours | OpenWeatherMap API | `hourly_income × blocked_hours` | ₹1,500 |
| **Extreme Heat** | >40°C (12-4 PM) | IMD API | `50% × daily_avg × hours` | ₹800 |
| **Severe Pollution** | AQI >400 for 4+ hrs | CPCB API | `40% × daily_average` | ₹600 |
| **App Outage** | >30 min downtime | Mock Status API | `hourly_income × duration` | ₹1,000 |
| **Curfew/Strike** | Govt advisory | Mock Alert API | `full_day_avg` (capped) | ₹2,000 |

### Payout Calculation

```python
# Calculate partner's hourly income
hourly_income = last_30_days_earnings / total_active_hours

# Determine affected hours
if trigger == "heavy_rain":
    hours = rain_duration_above_threshold
elif trigger == "extreme_heat":
    hours = 4  # Fixed window
elif trigger == "pollution":
    hours = aqi_duration_above_400 / 60
elif trigger == "app_outage":
    hours = outage_minutes / 60
elif trigger == "curfew":
    hours = 10  # Full working day

# Apply coverage percentage
coverage = {
    "heavy_rain": 1.0,      # 100%
    "app_outage": 1.0,      # 100%
    "curfew": 1.0,          # 100%
    "extreme_heat": 0.5,    # 50% (safety hours)
    "pollution": 0.4        # 40%
}

# Calculate payout
payout = hourly_income × hours × coverage[trigger]
payout = min(payout, MAX_PAYOUT)  # Apply cap
final_payout = round(payout / 10) * 10  # Round to ₹10
```

### Monitoring System

```
Cron Job (every 15 minutes)
    ↓
Query External APIs
    ├─ OpenWeatherMap (weather)
    ├─ IMD (temperature)
    ├─ CPCB (AQI)
    └─ Mock Status (outage/curfew)
    ↓
Compare vs trigger thresholds
    ↓
For each active policy in zone:
    ├─ Create claim
    ├─ Fraud validation
    ├─ Calculate payout
    └─ Initiate UPI transfer
    ↓
Push notification to partner
```

---

## 📱 Platform Choice: Web vs Mobile

### Decision: **Web-First Progressive Web App (PWA)**

### Comparison

| Criterion | Web PWA ✅ | Native App ❌ |
|-----------|-----------|---------------|
| Development Speed | Single codebase | 2 codebases (iOS + Android) |
| Time to Market | Deploy instantly | App store approval (7-14 days) |
| Updates | Push live updates | Wait for store review |
| User Onboarding | No download needed | Must install from store |
| Storage | ~5MB cached | ~50-100MB |
| Offline Support | ✅ Service workers | ✅ Native |
| Push Notifications | ✅ Web push | ✅ Native |
| GPS Access | ✅ Geolocation API | ✅ Native GPS |
| Cost | Lower (one team) | Higher (2 teams) |

### PWA Capabilities

**Supported Features**:
- ✅ Installable (Add to home screen)
- ✅ Offline mode (View active policy when offline)
- ✅ Push notifications (Claim approvals, payouts)
- ✅ GPS access (Fraud detection)
- ✅ Fast loading (<3s with service worker caching)

### Mobile-First Design

Even though web-based, we follow mobile-first principles:
- Touch-optimized UI (48px minimum tap targets)
- Thumb-friendly bottom navigation
- SMS-based OTP auth (no password)
- Optimized for 3G networks

### Future: Native App (Post-Hackathon)
Once validated with PWA, convert to React Native (90% code reuse) for better discoverability.

---

## 🤖 AI/ML Integration Plan

AI/ML is **core to the business model**, not cosmetic. Three critical applications:

### 1. Premium Calculation (XGBoost)

**Objective**: Dynamically price policies based on hyper-local risk

**Model**: XGBoost Regressor

**Why XGBoost?**
- Excellent for tabular data
- Fast inference (<10ms)
- Interpretable feature importance
- Handles missing values

**Training Pipeline**:

```python
# Features (15 parameters)
features = [
    'zone_id', 'month', 'day_of_week',
    '7day_rain_prob', '7day_max_temp', '7day_min_aqi',
    'claim_rate_30d', 'claim_rate_90d',
    'is_monsoon', 'is_summer',
    'zone_flood_history', 'zone_avg_pollution',
    'platform_outage_freq', 'festive_demand',
    'partner_tenure_weeks'
]

# Target: Historical risk multipliers
target = [0.8, 1.5, 1.2, 0.9, ...]

# Train model
from xgboost import XGBRegressor

model = XGBRegressor(
    n_estimators=100,
    max_depth=6,
    learning_rate=0.1
)
model.fit(X_train, y_train)

# Save
import joblib
joblib.dump(model, 'premium_pricing_v1.pkl')
```

**API Endpoint**:

```
POST /api/v1/calculate-premium
{
  "partner_id": "ZPT123",
  "zone_pincode": "560034"
}

Response:
{
  "base_premium": 50,
  "risk_multiplier": 1.2,
  "final_premium": 60,
  "risk_factors": {
    "weather_risk": "medium",
    "zone_history": "low",
    "seasonal_risk": "high"
  }
}
```

**Evaluation Metrics**:
- MAE (Mean Absolute Error): <0.15
- R² Score: >0.75
- Business Metric: Loss ratio 60-70%

---

### 2. Fraud Detection (Multi-Layer)

**Objective**: Prevent fraudulent claims, maintain <1% false positive rate

#### Layer 1: Anomaly Detection (Isolation Forest)

```python
from sklearn.ensemble import IsolationForest

# Features
features = [
    'claim_amount',
    'claim_hour',
    'days_since_last_claim',
    'claims_this_week',
    'amount_vs_partner_avg',
    'amount_vs_zone_avg'
]

# Train on historical claims
iso_forest = IsolationForest(contamination=0.05)
iso_forest.fit(historical_claims)

# Predict
anomaly_score = iso_forest.decision_function([new_claim])
is_anomaly = anomaly_score < -0.5

if is_anomaly:
    flag_for_manual_review()
```

#### Layer 2: GPS Validation

```python
def validate_gps(claim):
    # Get partner GPS logs during trigger
    gps_logs = get_partner_gps(
        partner_id, 
        claim.trigger_start, 
        claim.trigger_end
    )
    
    # Check 1: In trigger zone?
    trigger_zone = get_trigger_geofence(claim.zone)
    points_in_zone = count_points_in_zone(gps_logs, trigger_zone)
    
    if points_in_zone < len(gps_logs) * 0.7:
        return {"valid": False, "reason": "GPS location mismatch"}
    
    # Check 2: GPS spoofing (impossible speed)
    for i in range(len(gps_logs) - 1):
        speed = calc_speed(gps_logs[i], gps_logs[i+1])
        if speed > 60:  # >60 km/h for bike
            return {"valid": False, "reason": "GPS spoofing detected"}
    
    return {"valid": True}
```

#### Layer 3: Activity Cross-Check

```python
def cross_check_activity(claim):
    # Query delivery logs
    deliveries = get_partner_deliveries(
        partner_id,
        claim.trigger_start,
        claim.trigger_end
    )
    
    if len(deliveries) > 0:
        # Partner delivered during "blocked" time
        return {
            "valid": False,
            "reason": f"Completed {len(deliveries)} deliveries during claimed disruption"
        }
    
    return {"valid": True}
```

#### Layer 4: Duplicate Prevention

```python
def check_duplicate(claim):
    # Generate hash
    claim_hash = hash(f"{partner_id}_{trigger_type}_{date}")
    
    # Check Redis
    if claim_hash in redis.smembers("processed_claims"):
        return {"valid": False, "reason": "Duplicate claim"}
    
    # Store hash (7-day TTL)
    redis.sadd("processed_claims", claim_hash)
    redis.expire("processed_claims", 604800)
    
    return {"valid": True}
```

#### Fraud Decision Logic

```python
def process_with_fraud_check(claim):
    # Layer 1
    if detect_anomaly(claim):
        return "FLAGGED_ANOMALY"
    
    # Layer 2
    gps_result = validate_gps(claim)
    if not gps_result['valid']:
        return "REJECTED"
    
    # Layer 3
    activity_result = cross_check_activity(claim)
    if not activity_result['valid']:
        return "REJECTED"
    
    # Layer 4
    dup_result = check_duplicate(claim)
    if not dup_result['valid']:
        return "REJECTED"
    
    # Approved
    initiate_payout(claim)
    return "APPROVED"
```

---

### 3. Predictive Analytics

**Next-Week Risk Heatmap**:

```python
def generate_risk_heatmap():
    zones = get_all_zones()
    risk_map = {}
    
    for zone in zones:
        # 7-day forecast
        forecast = get_weather_api(zone.pincode, days=7)
        
        # Calculate disruption hours
        rain_hours = count_hours(forecast, 'rain_mm', >20)
        heat_hours = count_hours(forecast, 'max_temp', >40)
        pollution_hours = count_hours(forecast, 'aqi', >400)
        
        total_risk_hours = rain_hours + heat_hours + pollution_hours
        
        # Expected claims
        partners = count_active_partners(zone)
        expected_claims = partners * (total_risk_hours / 168) * 0.8
        
        # Expected payout
        avg_payout = 750
        expected_payout = expected_claims * avg_payout
        
        risk_map[zone.pincode] = {
            "risk_level": categorize_risk(total_risk_hours),
            "expected_claims": round(expected_claims),
            "expected_payout": round(expected_payout)
        }
    
    return risk_map
```

**Premium Adjustment Suggestions**:

```python
def suggest_adjustments():
    metrics = get_current_week_metrics()
    loss_ratio = metrics['payouts'] / metrics['premiums']
    
    suggestions = []
    
    if loss_ratio > 0.75:  # Too high
        high_loss_zones = find_zones_with_loss_ratio(>0.8)
        
        for zone in high_loss_zones:
            new_multiplier = zone.multiplier * 1.15
            suggestions.append({
                "zone": zone.pincode,
                "action": "INCREASE",
                "from": zone.current_premium,
                "to": 50 * new_multiplier,
                "reason": f"Loss ratio {zone.loss_ratio:.1%}"
            })
    
    elif loss_ratio < 0.60:  # Too low
        low_loss_zones = find_zones_with_loss_ratio(<0.5)
        
        for zone in low_loss_zones:
            new_multiplier = max(0.6, zone.multiplier * 0.90)
            suggestions.append({
                "zone": zone.pincode,
                "action": "DECREASE",
                "from": zone.current_premium,
                "to": 50 * new_multiplier,
                "reason": "Can attract more partners"
            })
    
    return suggestions
```

---

### ML Development Roadmap

| Phase | Milestone | Approach |
|-------|-----------|----------|
| **Phase 1** | Model design, mock data | Define features, synthetic data |
| **Phase 2** | Prototype | Train XGBoost on mock, integrate API |
| **Phase 3** | Real data & tuning | Collect real data, retrain models |
| **Phase 4** | Production | A/B testing, monitoring, continuous learning |

---

## 🛠️ Technology Stack

### Frontend

```
React.js 18.2
├── UI: TailwindCSS 3.3 + Shadcn/ui
├── State: Redux Toolkit
├── Routing: React Router v6
├── HTTP: Axios
├── Maps: Leaflet.js
├── Charts: Recharts
├── Forms: React Hook Form + Zod
└── PWA: Workbox (service worker)
```

---

### Backend

**Option 1: Node.js + Express** (Phase 2)
```
Node.js 20 LTS
├── Framework: Express.js 4.18
├── Auth: JWT (jsonwebtoken)
├── Validation: Joi / Zod
└── Logging: Winston
```

**Option 2: Python FastAPI** (Phase 3 - ML integration)
```
Python 3.11
├── Framework: FastAPI 0.109
├── ORM: SQLAlchemy 2.0 (async)
├── Validation: Pydantic
└── Server: Uvicorn
```

**Decision**: Start with **Node.js** (Phase 2), migrate ML endpoints to **FastAPI** (Phase 3)

---

### Database

```
MongoDB 7.0 (Primary)
├── Collections:
│   ├── partners
│   ├── policies
│   ├── claims
│   ├── payouts
│   └── zones
└── Indexing: (partner_id, date), (zone_id, trigger_type)

Redis 7.2 (Cache)
├── Session management
├── Rate limiting
├── Trigger state cache
└── Duplicate prevention

InfluxDB 2.7 (Time-Series)
├── weather_data (15-min intervals)
├── partner_earnings (hourly)
└── claim_metrics (volume over time)
```

---

### ML Microservice

```
Python 3.11
├── ML: scikit-learn 1.3, XGBoost 2.0
├── Data: pandas 2.1, numpy 1.24
├── Serving: FastAPI
├── Storage: joblib, MLflow
└── Deploy: Docker on AWS Lambda
```

**Endpoints**:
```
POST /ml/premium-pricing
POST /ml/fraud-detection/anomaly
POST /ml/predict-risk
```

---

### External APIs

| Service | API | Purpose | Tier |
|---------|-----|---------|------|
| OpenWeatherMap | Weather Forecast | Rain, temp triggers | Free (60/min) |
| IMD | Weather Data | Official temp data | Free |
| CPCB | Air Quality | AQI triggers | Free |
| Razorpay | Payments | UPI payouts | Test Mode |
| Twilio | SMS | OTP, notifications | Free trial |
| Google Maps | Geocoding | Pin code → lat/lon | Free tier |
| Mock APIs | Status/Alerts | Outage/curfew triggers | Custom-built |

---

### DevOps

```
Git + GitHub
├── CI/CD: GitHub Actions
├── Frontend: Vercel
├── Backend: Render / Railway
├── ML Service: AWS Lambda
├── Database: MongoDB Atlas
└── Redis: Upstash

Monitoring:
├── Errors: Sentry
├── Performance: Datadog
└── Uptime: UptimeRobot
```

---

### Architecture Diagram

```
┌─────────────────────────────────────┐
│    USER DEVICES (PWA)                │
│ Mobile (Android/iOS) | Desktop      │
└────────────┬────────────────────────┘
             │ HTTPS
             ↓
┌─────────────────────────────────────┐
│      FRONTEND (Vercel CDN)           │
│  React + Tailwind | Service Worker  │
└────────────┬────────────────────────┘
             │ REST API
             ↓
┌─────────────────────────────────────┐
│    API GATEWAY (Express - Render)   │
│  JWT Auth | Rate Limiting | CORS    │
└────────────┬────────────────────────┘
             │
   ┌─────────┼─────────┬────────┐
   │         │         │        │
   ↓         ↓         ↓        ↓
┌─────┐ ┌─────────┐ ┌────────┐ ┌───────┐
│Auth │ │ Policy  │ │Trigger │ │ Claim │
│Svc  │ │ Service │ │Monitor │ │  Svc  │
└─────┘ └────┬────┘ └────────┘ └───┬───┘
             │                      │
             ↓                      ↓
     ┌──────────────────────────────────┐
     │   ML MICROSERVICE (AWS Lambda)   │
     │  Premium Pricing | Fraud Detect  │
     └──────────────────────────────────┘
             │
             ↓
┌─────────────────────────────────────┐
│          DATA LAYER                  │
│  MongoDB | Redis | InfluxDB         │
└─────────────────────────────────────┘
             │
             ↓
┌─────────────────────────────────────┐
│    EXTERNAL INTEGRATIONS             │
│ Weather | Payments | SMS | Mock APIs│
└─────────────────────────────────────┘
```

---

## 📅 Development Plan

### **Phase 1: Foundation** (Weeks 1-2) ✅ CURRENT

**Deliverables**:
- ✅ Complete README (this document)
- ✅ 15-slide pitch deck
- ✅ 2-minute strategy video
- ✅ GitHub repository setup

**Activities**:
- Persona research (Zepto partners)
- Define 5 triggers with thresholds
- Design premium logic (XGBoost features)
- Database schema (MongoDB collections)
- ML model pseudocode
- Wireframes (Figma)
- Record 2-min video

---

### **Phase 2: Core Prototype** (Weeks 3-4)

**Deliverables**:
- Registration & login (OTP auth)
- Policy purchase + AI premium
- Mock trigger listener (3-5 triggers)
- Auto-claim creation
- Partner dashboard
- 2-minute demo video

**Tasks**:

**Week 3**:
- Frontend: React + Tailwind, routing
- Backend: Express, MongoDB connection
- Auth: Phone OTP, JWT
- Policy API: Create, fetch policy
- ML: Train XGBoost on mock data
- Premium API: Integrate ML model

**Week 4**:
- Trigger listener: Cron (OpenWeatherMap, 15min)
- Auto-claim: Detect → Create → Calculate
- Mock payout: Log to DB
- Dashboard: Policy status, payout history
- Testing: E2E flow

---

### **Phase 3: Production Features** (Weeks 5-6)

**Deliverables**:
- Multi-layer fraud detection
- Razorpay integration (test mode)
- Partner dashboard (polished)
- Admin dashboard (analytics)
- 5-minute final demo video
- Updated pitch deck

**Tasks**:

**Week 5**:
- Fraud Layer 1: Isolation Forest
- Fraud Layer 2: GPS validation
- Fraud Layer 3: Activity cross-check
- Fraud Layer 4: Duplicate prevention
- Razorpay: Test UPI payouts

**Week 6**:
- Partner dashboard: Charts, timeline
- Admin dashboard: Loss ratio, heatmap
- Predictive analytics: Risk forecast
- Optimization: Caching, indexing
- Final testing: E2E, edge cases
- Record 5-min video
- Update pitch deck

---

## 👥 Team

**Team Lead**: Kanishk  
**Role**: Full Stack + ML Integration  
**Batch**: 2026  

**Team Members**:
- [Add teammate names and roles]

---

## 📹 Demo Video

**Phase 1 Strategy Video (2 minutes)**: [Link to be added]  
_Covers: Problem, Persona, Solution, Pricing, AI/ML Plan, Tech Stack_

---

## 📄 License

MIT License - Guidewire DEVTrails 2026

---

## 🙏 Acknowledgments

- **Guidewire DEVTrails** for the problem statement
- **Zepto** for inspiring the persona
- **OpenWeatherMap, Razorpay, Twilio** for API access
- India's gig workers who deserve protection

---

**Built with ❤️ for India's delivery heroes**
