TRIPLEMATE Defect Report V1.6 — Mobile Offline

ไฟล์นี้เป็นเว็บแอปแบบ PWA สำหรับใช้งานออฟไลน์หลังเปิดผ่าน HTTPS และเพิ่มลงหน้าจอหลักแล้ว

วิธีใช้ iPhone / Android (ฟรี):
1. สร้าง GitHub repository แบบ Public (ระวัง: ไฟล์โค้ดเป็นสาธารณะ แต่ข้อมูลโครงการ/รูปภาพจะอยู่ในเบราว์เซอร์ของแต่ละเครื่อง ไม่ถูกอัปโหลดขึ้น GitHub)
2. Upload index.html, sw.js, manifest.webmanifest และโฟลเดอร์ icons ไปยัง root ของ repository
3. Settings > Pages > Deploy from a branch > main / (root) > Save
4. เปิด URL https://USERNAME.github.io/REPOSITORY/ บน Safari (iPhone) หรือ Chrome (Android) ขณะออนไลน์ครั้งแรก
5. iPhone: Share > Add to Home Screen; Android: เมนู > Add to Home screen / Install app
6. เปิดแอปจากหน้าจอหลักอย่างน้อยหนึ่งครั้งขณะออนไลน์ จากนั้นทดสอบ Airplane Mode

ข้อจำกัดสำคัญ:
- ข้อมูลและรูปภาพแยกตามอุปกรณ์ ไม่มีการซิงก์
- บันทึกใน localStorage ของ origin เว็บไซต์; พื้นที่มีจำกัดและ iOS อาจลบข้อมูลเว็บเมื่อพื้นที่ไม่พอ
- สำรองข้อมูล JSON เป็นประจำ และเก็บไฟล์สำรองใน Files/Drive ที่คุณควบคุม
- หากเปิด index.html จาก Files โดยตรง จะไม่ติดตั้ง service worker และไม่รับประกันการเก็บข้อมูลหรือการส่งออก PDF บน iOS
- PDF: ใช้ Export PDF แล้วเลือก Print/Share > Save to Files ตามเมนูของระบบ; ตรวจสอบหน้าปกและกรอบ After ว่างก่อนส่ง
- ไม่ต้องเสียค่า Hosting รายเดือนสำหรับ GitHub Pages ตามโควตาฟรี ณ วันที่ใช้งาน แต่ต้องมีอินเทอร์เน็ตในการติดตั้งครั้งแรก

ทดสอบบนคอมพิวเตอร์: เปิดโฟลเดอร์แล้วรัน python -m http.server 8000 จากนั้นเปิด http://localhost:8000
