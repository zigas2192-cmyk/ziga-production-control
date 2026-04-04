# ZIGA Production Control

**One Contact Flow System — Production Module (App 2)**
M4 · M6 · M7 · M8 · M9 · M10

🔗 **Live:** https://zigas2192-cmyk.github.io/ziga-production-control/

---

## Stack
- Static HTML/JS → GitHub Pages (ฟรี)
- Microsoft MSAL.js → Azure AD auth (@ziga.co.th)
- Microsoft Graph API → SharePoint Lists
- IBM Plex Sans Thai + IBM Plex Mono

---

## SharePoint Lists ที่ใช้

| List | ชื่อ | หน้าที่ |
|------|------|---------|
| L4 | Mcoil_Inventory | คลัง MCID + น้ำหนักสลิต |
| L6 | OSE_Production | ใบงานสลิต OSE |
| L7 | DailyPlan_OFM | แผนผลิตรายวัน OFM |
| L8 | Defect_FMQA08 | บันทึกของเสีย QA |

**SharePoint Site:** `zigainnovation.sharepoint.com/sites/msteams_1fdd76`

---

## Modules & ผู้รับผิดชอบ

| Module | ผู้รับผิดชอบ | List | Tab |
|--------|------------|------|-----|
| M4 | จอย (คลัง IR) | L4 | รับเหล็ก |
| M6 | Duke (AP) | L6 | วางแผน OSE |
| M7 | แป๋ม (AS) | L7 | วางแผน OFM |
| M8 | จอย (คลัง IR) | L4 | รับเหล็ก |
| M9 | สุภาพ / เอกภพ / สามารถ (Slitter) | L4 | สลิท+น้ำหนัก |
| M10 | Duke (AP) | L4+L6 | AX Calc |

---

## Roles & พนักงาน (42 คน)

| Role | จำนวน | ตัวอย่าง |
|------|--------|---------|
| 👑 ผู้บริหาร / บัญชี | 16 | ตุ้ย, แข, แอน, ฐปนี |
| 📊 AP | 1 | Duke (จตุรณ) |
| 📅 AS | 1 | แป๋ม (สุวิภา) |
| 🏭 คลัง IR | 2 | ณัฏฐากุญช์, ทวีศักดิ์ |
| ⚙️ Slitter | 3 | เอกภพ, สุภาพ, สามารถ |
| 🔧 พนักงานผลิต | 13 | เครื่องรีด, ลบคม, เกลียว, แพ็ค |
| 🔍 QA | 4 | อดิศักดิ์, วรรณรดา, อภินันท์, สุกานดา |
| 👷 Supervisor | 2 | ทิพยเนตร, มนตรี |

> พนักงานฝ่ายขาย / จัดซื้อ / HR / ช่างซ่อม → ไม่มีสิทธิ์เข้าใช้งาน

---

## Azure AD

| Field | Value |
|-------|-------|
| Tenant | zigainnovation |
| Tenant ID | `2c7e3ab4-6d2f-491e-87cc-8be0a96f1a68` |
| App Name | ZIGA-ProductionControl |
| Client ID | `YOUR_CLIENT_ID_HERE` ← ใส่หลัง App Registration |
| Redirect URI | `https://zigas2192-cmyk.github.io/ziga-production-control/` |
| Permissions | Sites.ReadWrite.All, User.Read (Delegated) |

### ขั้นตอน App Registration
1. portal.azure.com → Azure AD → App registrations → New registration
2. Name: `ZIGA-ProductionControl`
3. Account type: **This organization only (zigainnovation)**
4. Redirect URI: **Single-page application (SPA)** → URL ด้านบน
5. Register → copy **Application (client) ID**
6. แก้ `index.html` บรรทัด `clientId: 'YOUR_CLIENT_ID_HERE'`
7. API permissions → Add → Microsoft Graph → Delegated → `Sites.ReadWrite.All` + `User.Read`
8. Grant admin consent

---

## Related
- [ZIGA-Mcoil-OSE](https://github.com/zigas2192-cmyk/ziga-mcoil-ose) — M1–M3 Purchasing / LC / Shipping

---

## Go Live Target: 1 พ.ค. 2568

| Phase | วันที่ | Scope |
|-------|--------|-------|
| W0 Setup | 1–5 เม.ย. | Site, Lists, Users |
| Phase 1 | 6–8 เม.ย. | M1–M4 |
| หยุด | 9–18 เม.ย. | — |
| Phase 2 | 21–25 เม.ย. | M5–M8 |
| Phase 3 | 28–30 เม.ย. | M9–M10 |
| **Go Live** | **1 พ.ค.** | 🚀 |
