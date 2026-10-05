ICHI-JAPAN v1.5.9 · Build 1590
UX / VISUAL BALANCE RELEASE — Final polish before v1.6
อัปเดต 5 ตุลาคม 2026

เป้าหมายรุ่นนี้
- ไม่เพิ่มระบบใหญ่ใหม่ และไม่ตัดฟังก์ชันเดิม
- จัดลำดับข้อมูลใหม่ให้คิดเหมือน “แอปใช้จริงระหว่างทริป” มากกว่าเว็บที่สะสมฟีเจอร์
- ทำ visual rhythm, spacing, card hierarchy, typography และ mobile touch targets ให้เป็นระบบเดียวกันทั้งเว็บ
- ใช้ฐาน v1.5.8 Build 1583 เดิม จึงคง Ticket & Booking, Immigration Coach, Joint Kiosk, Transportation, Discover, Money, Offline และข้อมูลทริปทั้งหมด
- localStorage key ยังเป็น tabi-v1 เดิม

แนวคิด UX หลัก
1) หนึ่งหน้าต้องตอบหนึ่งคำถามหลักก่อน
   - Dashboard: ตอนนี้ต้องรู้อะไร / ทำอะไรต่อ
   - Plan: วันนี้ไปไหน ลำดับอะไร และมีอะไรต้องแก้
   - Travel: ตอนนี้ต้องใช้เครื่องมือเดินทางตัวไหน
   - Money: ใช้ไปเท่าไร และจะบันทึกรายการอะไร
   - Trip: เอกสาร/ที่พัก/ความพร้อมของทริป
2) Primary action เด่นกว่าปุ่มรอง
3) เครื่องมือเสริมไม่แย่งสายตาจากงานหลัก
4) Mobile ต้องกดด้วยนิ้วเดียวได้ และข้อความสำคัญไม่เล็กจนต้องเพ่ง
5) ไม่ซ่อนฟังก์ชันเดิมเพื่อแลกกับความสวย — เปลี่ยนเฉพาะลำดับ/ความเด่น/บริบท

สิ่งที่ปรับใน v1.5.9

A. GLOBAL VISUAL SYSTEM
- กำหนดความกว้าง content, radius, gap, shadow และ surface ชุดเดียวกัน
- ลดความรู้สึก “กล่องซ้อนกล่อง” ด้วยเส้นขอบ/เงาที่เบาลง
- Top bar เป็น sticky blur แบบเบา เพื่อใช้งานบนหน้าที่ยาว
- Sidebar desktop กระชับขึ้น พร้อม active state ที่เห็นง่ายแต่ไม่หนา
- Title ทุกหน้ามีน้ำหนักและระยะห่างใกล้เคียงกัน
- Card / Button / Notice / Form ใช้สัดส่วนเดียวกันมากขึ้น
- Dialog บนมือถือเป็น bottom sheet เพื่อเอื้อมนิ้วถึงง่ายกว่า modal กลางจอ

B. DASHBOARD
- คง Smart Logic และทุกการ์ดเดิม
- ปรับ Hero / Readiness / Status Deck / Action Queue / Timeline / Food / Quick Tools ให้มี hierarchy ชัดขึ้น
- Desktop ใช้ main + side column ที่บาลานซ์กว่าเดิม
- Mobile เปลี่ยน status เป็นแถวเลื่อนแนวนอน ไม่บีบการ์ดหลายใบลงจอ
- แก้ข้อความ Dashboard บนมือถือที่บางส่วนเล็กเกินไปให้กลับมาอ่านได้จริง
- Quick Tools เป็น 2×2 บนมือถือ

C. TRAVEL — จุดที่ปรับมากที่สุด
ลำดับใหม่:
  หัวหน้าเดินทาง
  → 6 เครื่องมือหลัก
  → เครื่องมือที่เลือก
  → เนื้อหา/Action ของเครื่องมือนั้น

- 6 เครื่องมือยังอยู่ครบ: สนามบิน / เส้นทาง / แผนที่ / ภาษา / ตม. ญี่ปุ่น / มารยาท
- เปลี่ยนชื่อบน UI ให้สั้นและสแกนง่าย โดย data/action เดิมไม่เปลี่ยน
- Desktop 6 ช่องในแถวเดียว
- Mobile 3×2 เพื่อไม่ต้องเลื่อนหาฟังก์ชันหลัก
- Quick Rail Guide จะโผล่เฉพาะหน้า “เส้นทาง” และ “แผนที่” ไม่แทรกทุก tab
- Airport tabs เปลี่ยนเป็น horizontal chips เลื่อนได้บนมือถือ
- คู่มือสนามบินแบ่ง main task + side helper ชัดขึ้น
- Immigration / Joint Kiosk ใช้ visual hierarchy ชุดเดียวกับ Travel

D. PLAN
ปัญหาเดิม: ฟีเจอร์ที่เพิ่มหลายรุ่นทำให้ Smart Planner / Day Status ถูก prepend ก่อนชื่อหน้า
ลำดับใหม่:
  ชื่อหน้า
  → วันที่
  → Smart guidance / conflict
  → Day status
  → Itinerary

- ไม่เปลี่ยน logic ของ Smart Day Planner หรือ Time Conflict
- Day control เป็น 2×2 บนมือถือ
- Event controls เลื่อนแนวนอนได้เมื่อต้องใช้หลาย action เพื่อไม่บีบข้อความ
- Route actions เรียงอ่านง่ายขึ้นบนจอเล็ก

E. DISCOVER
- ลด Hero และ filter area ให้ไม่กินพื้นที่ก่อนถึงผลลัพธ์
- Desktop 3 columns / tablet 2 / mobile 1
- Card spacing, image, description และ action ใช้น้ำหนักใกล้กัน
- Data Quality / checked date / source / status เดิมอยู่ครบ

F. MONEY
- Wallet summary กับ ledger ถูกจัดให้เป็นหนึ่ง workflow มากขึ้น
- Desktop ให้ ledger มีพื้นที่อ่านรายการมากกว่า summary
- Mobile ยุบเป็นหนึ่งคอลัมน์
- รายจ่าย / รายรับ / cash / settle / refund / summary / tax-free เดิมอยู่ครบ

G. TRIP
- คงโครงที่เสถียรจาก 1.5.3: ข้อมูลทริป → ที่พัก → ticket/docs → readiness → emergency → offline/backup → version
- ปรับเฉพาะ radius, spacing, shadow และความกว้างรวม
- Version/update ยังอยู่ด้านล่างเหมือนเดิม

H. NOW / LIVE INFORMATION
- External status cards ใช้ระยะและ typography เดียวกัน
- 2 columns บนจอกว้าง / 1 column บนมือถือ
- ไม่เปลี่ยนแหล่งข้อมูลหรือสถานะ live/manual เดิม

I. MOBILE RULES
- <= 900px ตัด desktop sidebar ออกและใช้ bottom nav
- <= 720px เนื้อหาเป็น one-column เมื่อเหมาะสม
- bottom nav 7 รายการเดิมอยู่ครบ
- เพิ่ม safe-area spacing
- Travel tabs 3×2
- Dashboard status เป็น horizontal scroll
- Dialog เป็น bottom sheet
- ลดจุดที่ข้อความ 8–9px ในหน้าหลักให้กลับมาอ่านได้ดีขึ้น

สิ่งที่ตั้งใจ “ไม่เปลี่ยน”
- localStorage key: tabi-v1
- โครงสร้างข้อมูลทริป
- Transportation / Route Pack
- Smart Logic / Time Conflict / Smart Day Planner
- Ticket & Booking 2.0
- Immigration Coach 52 หัวข้อ
- Joint Kiosk guide / carousel / offline guide
- Discover database / Data Quality
- Money / split / refund / cash / export
- Hotel / docs / IndexedDB attachments
- Offline Packs / Service Worker behavior
- Fuji Visibility
- Live Trip

Version / cache
- APP_VERSION: 1.5.9
- APP_BUILD: 1590
- core asset query: v=1590
- service worker cache: ichi-1.5.9-build1590
- Joint Kiosk HTML + images ยังคงอยู่ใน Guide offline pack

Regression / static checks
- JavaScript syntax: app.js / travel-data.js / discover.js / places-data.js / sw.js
- Build/version references: 1590 ตรงกันใน index/app/discover/service worker/version.json
- data-action ที่มีใน v1.5.8 b1583: ไม่ถูกลบ
- switch action cases ที่มีใน v1.5.8 b1583: ไม่ถูกลบ
- app.js เมื่อ normalize version/build ต่างจาก b1583 เฉพาะ UX layer ที่ append เพิ่ม
- ไม่มีการเปลี่ยน localStorage key

วิธีอัปเดต GitHub Pages
1. แนะนำให้เปิดเว็บเดิม > ทริปของฉัน > ส่งออกสำรอง ก่อนอัปเดต
2. แตก ZIP แล้วอัปโหลดไฟล์ในชุดนี้ทับที่ root ของ repository TravelJapan
3. Commit แล้วรอ GitHub Pages deploy
4. เปิดเว็บแบบออนไลน์ แล้วปิดแท็บเก่า/เปิดใหม่
5. ตรวจ footer ให้ขึ้น v1.5.9 · b1590
6. เข้า ทริปของฉัน > ตรวจอัปเดต
7. กด “เตรียมใช้ออฟไลน์” ใหม่หลังยืนยันว่า UI เปิดครบ
8. แนะนำทดสอบ Dashboard / Plan / Travel / Money / Trip / Discover บนมือถือจริงก่อน freeze 1.5.9

ไฟล์ใน ZIP
- index.html
- app.js
- style.css
- travel-data.js
- sw.js
- version.json
- discover.js
- discover.css
- places-data.js
- recover.html
- joint-kiosk.html
- joint-kiosk-overview.png
- joint-kiosk-steps.png
- joint-kiosk-rules.png
- README-UPDATE.txt
