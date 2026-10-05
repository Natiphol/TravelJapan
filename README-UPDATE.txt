ICHI-JAPAN v1.5.8 · Build 1582
Joint Kiosk Arrival Guide + Immigration Coach Update
อัปเดต 5 ตุลาคม 2026

ฐานของรุ่นนี้
- ใช้ source v1.5.7 Build 1570 ที่ผู้ใช้ส่งมาเป็นฐานโดยตรง
- ไม่ใช้ Emergency Restore / 1.5.8 Build 1580 เป็นฐาน
- ไม่เปลี่ยน localStorage key: tabi-v1
- Transportation, Ticket & Booking 2.0, Immigration Coach 52 หัวข้อ, Money, Hotel, Discover และข้อมูลเดิมอยู่ครบ

ของใหม่: JOINT KIOSK ARRIVAL GUIDE
- เพิ่มการ์ด Joint Kiosk ในหน้า เดินทาง > เตรียม ตม.
- เพิ่มคู่มือแบบเต็มใน Modal โดยไม่ทำหน้า Immigration ยาวเกินไป
- แสดง flow: Visit Japan Web QR + Passport → Joint Kiosk → Dedicated Immigration Booth → Baggage Claim → Customs Gate
- สนามบินที่หน้า Japan Customs ระบุว่ารองรับ ณ 5 ต.ค. 2026:
  • Narita T1 / T2 / T3
  • Haneda T2 / T3
  • Kansai T1 / T2
  • Fukuoka
- เน้นสนามบินของทริปปัจจุบันอัตโนมัติ (NRT/HND/KIX)
- ข้อควรรู้: ทำทีละคน, ต่ำกว่า 135 ซม. ใช้ตู้ไม่ได้, ถอดสิ่งปิดบังใบหน้า, รถเข็นใช้ได้, non-IC passport มีข้อจำกัด e-Gate
- เตือนชัดว่า Joint Kiosk ไม่ได้รับประกันว่าจะไม่ถูกตรวจเพิ่มเติมโดยศุลกากร
- ไม่ใช้คำโฆษณาว่า “เร็วขึ้น 20 นาที” เพราะแหล่งทางการไม่ได้รับประกันตัวเลขดังกล่าว
- แหล่งข้อมูลและวันที่ตรวจล่าสุดอยู่ในหน้าเว็บ

รูปประกอบ ICHI-JAPAN
- joint-kiosk-overview.png
- joint-kiosk-steps.png
- joint-kiosk-rules.png
รูปเหล่านี้เป็นภาพประกอบที่จัดทำใหม่สำหรับ ICHI-JAPAN ไม่ใช่ไฟล์ภาพต้นฉบับจากโพสต์ที่ผู้ใช้ส่งมา
รายละเอียดข้อเท็จจริงให้ยึดข้อความในหน้าเว็บและแหล่ง Official ซึ่งตรวจ 5 ต.ค. 2026

แหล่งข้อมูลทางการ
- Japan Customs — Joint Kiosk
  https://www.customs.go.jp/kaigairyoko/pilot_kiosk.html
- Japan Customs — Narita T1/T2 expansion, operation from 24 Sep 2026
  https://www.customs.go.jp/kaigairyoko/20260918.html
- Digital Agency — Visit Japan Web Guide
  https://services.digital.go.jp/visit-japan-web/guide/
- Visit Japan Web
  https://www.vjw.digital.go.jp/
- Immigration Services Agency — Landing procedures
  https://www.moj.go.jp/isa/immigration/procedures/zyouriku_00001.html

Offline
- รูป Joint Kiosk ทั้ง 3 รูปถูกเพิ่มเข้า guide pack ของ Service Worker
- Core build reference ใช้ 1582 ตรงกันใน index/app/discover/service worker
- หลังอัปเดต ให้เข้า ทริปของฉัน > เตรียมใช้ออฟไลน์ใหม่ เพื่อเก็บ guide pack รุ่นใหม่

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
- README-UPDATE.txt
- joint-kiosk-overview.png
- joint-kiosk-steps.png
- joint-kiosk-rules.png

วิธีอัปเดต GitHub Pages
1. สำรอง JSON จากเว็บเดิมก่อน
2. แตก ZIP แล้วอัปโหลดไฟล์ทั้งหมดทับที่ root ของ repository TravelJapan
3. Commit และรอ GitHub Pages deploy
4. เปิดเว็บขณะออนไลน์แล้วปิดแท็บเก่า/เปิดใหม่
5. ตรวจ footer ให้ขึ้น v1.5.8 · b1582
6. เข้า ทริปของฉัน > ตรวจอัปเดต
7. กดเตรียมใช้ออฟไลน์ใหม่
8. ทดสอบ เดินทาง > เตรียม ตม. > เปิดคู่มือ Joint Kiosk

Regression ที่ต้องผ่าน
- app.js / travel-data.js / discover.js / places-data.js syntax ผ่าน
- version/build references เป็น 1.5.8 / 1582
- localStorage key ยังเป็น tabi-v1
- Immigration QA 52 หัวข้อเดิมไม่ถูกลบ
- Booking/Transportation functions เดิมยังอยู่
- Service Worker guide pack มี Joint Kiosk images ครบ 3 ไฟล์

============================================================
HOTFIX · Build 1582 — Joint Kiosk guide navigation
============================================================
- แก้ปุ่ม “เปิดคู่มือ Joint Kiosk” ที่ Build 1581 บาง browser กดแล้วไม่เปิด modal
- เปลี่ยนเป็นเปิดหน้า joint-kiosk.html โดยตรง ไม่พึ่ง custom click-handler
- รูป Joint Kiosk ทั้ง 3 รูปกดดูเต็มภาพได้
- เพิ่ม joint-kiosk.html เข้า Offline Guide Pack ของ Service Worker
- ไม่เปลี่ยน localStorage key (tabi-v1)
- Ticket / Booking / Immigration Coach / Transportation เดิมไม่เปลี่ยนโครงข้อมูล
