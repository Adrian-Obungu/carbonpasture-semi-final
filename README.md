# CarbonPasture – Semi-Final Demo

CarbonPasture is a **climate-tech platform** that rewards farmers for methane reduction practices.  
This demo showcases the **end-to-end flow**: **USSD → REST API → MPESA (Daraja sandbox) → local credit ledger**.

---

## 🚜 Problem
- Smallholder and large-scale farmers struggle to **track methane emissions**.  
- Limited access to **financial incentives** prevents adoption of sustainable practices.  
- Existing carbon markets are complex, leaving farmers excluded.  

---

## 🌍 Our Solution
CarbonPasture provides:
- **USSD Interface**: Farmers can submit methane readings without internet.  
- **Credits & Ledger**: Farmers earn carbon credits stored securely in a tamper-proof local ledger.  
- **MPESA Integration**: Real-time payments via STK Push (Daraja sandbox).  
- **Fallback Systems**: 99% uptime with local ledger + mock fallback for payment API outages.  

---

## 📖 Features in the Demo
- 📞 **Farmer Registration via USSD**  
- 🌱 **Methane Data Submission**  
- 💰 **Credit Awarding (Carbon Credits)**  
- 📲 **MPESA STK Push Integration** (Sandbox)  
- 🔐 **Secure Local Ledger** for data integrity  
- ⚡ **One-click Demo Script (`start-demo.sh`)**  

---

## ⚙️ Quickstart

Clone repo & install dependencies:
```bash
git clone https://github.com/Adrian-Obungu/carbonpasture-semi-final.git
cd carbonpasture-semi-final
npm install

Run demo:

./start-demo.sh


Start ngrok for callback:

ngrok http 4001


Trigger a test USSD session:

curl -s -X POST http://127.0.0.1:4000/ussd \
  -d "sessionId=demo-s2" \
  -d "phoneNumber=+254700000002" \
  -d "text=2*farmSmoke*12.3"


Trigger payment:

node payment.js --farmer farmSmoke --phone +254700000002 --amount 1

📊 Demo Workflow

USSD submission → farmer enters methane reading.

REST API logs reading and issues credits.

Ledger updates with secure entry.

MPESA STK Push sends payment to farmer.

Callback Listener updates transaction status.

🧩 Project Structure
carbonpasture-semi-final/
├── rest-api.js          # Main REST API
├── ussd.js              # USSD handler
├── payment.js           # MPESA integration
├── mpesa-callback.js    # STK Push callback listener
├── start-demo.sh        # One-click demo runner
├── data/                # Demo data (credits, logs)
├── scripts/             # Maintenance scripts
├── README.md            # This file
└── demo.md              # Hackathon demo instructions

🎯 Next Steps

Expand beyond smallholder → large-scale farmers.

Introduce Progressive Web App (PWA) interface.

Partner with climate organizations tackling flooding & methane.

Explore carbon credits funding schools & community projects.

👥 Team

Adrian Obungu & team — Hackathon Semi-Finals 2025

📹 Deliverables

carbonposture-demo.mp4 – Demo video

README.md – Main documentation

demo.md – Pitch/demo guide

releaseall.pdf – Image/Video release form (UNEP requirement)


---

This structure is **pitch-ready**, technical enough for developers, and clear enough for non-technical judges.  

👉 Question: do you want me to also generate a **lighter README.txt** (1-page, 
