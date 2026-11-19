# เว็บไซต์ลอยกระทง — เชื่อมต่อ Supabase

## ตั้งค่าการเชื่อมต่อ
ไฟล์ `index.html` กำหนด Project URL และ Publishable key สำหรับโปรเจกต์ Supabase ที่แจ้งมาแล้ว

## ฐานข้อมูล
ไฟล์ `setup.sql` ใช้สร้างตาราง `public.krathongs` และนโยบาย RLS สำหรับอ่าน/ส่งกระทง
หากรัน SQL แล้ว ไม่ต้องรันซ้ำ

## เปิด Realtime
ใน Supabase Dashboard ไปที่ Database → Publications (หรือ Database → Replication)
เลือก publication `supabase_realtime` แล้วเปิด/เพิ่มตาราง `public.krathongs` ให้ส่งเหตุการณ์ INSERT
จากนั้นตรวจสอบว่าเว็บไซต์แสดงสถานะ “เชื่อมต่อฐานข้อมูลกลางแล้ว”

## เผยแพร่เว็บไซต์
อัปโหลดไฟล์ `index.html` และ `maunchon_mascot.png` ไปยัง Netlify โดยคงไฟล์ไว้ในโฟลเดอร์เดียวกัน

## ความปลอดภัย
Publishable key ใช้ในเบราว์เซอร์ได้ แต่การเข้าถึงข้อมูลถูกควบคุมด้วย RLS
อย่าใส่ Secret key หรือ service_role key ในเว็บไซต์
