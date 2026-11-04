# 🏦 Bank DApp × Infura

เว็บแอปพลิเคชันแบบกระจายศูนย์ (DApp) สำหรับ **ฝากเงิน / ถอนเงิน / ตรวจสอบยอดเงิน** ผ่าน Smart Contract บน Ethereum Testnet
ระบบอ่านข้อมูลจาก blockchain ผ่าน **Infura** และใช้กระเป๋า **MetaMask** ยืนยันรายการฝากและถอน

🔗 **เว็บไซต์:** https://thanapoomwi.github.io/bank-dappInfura/

| | |
|---|---|
| ผู้จัดทำ | ธนภูมิ วิธานกรกุล (Tanapoom Witrankronkoon) |
| รหัสนักศึกษา | 66068660 |
| Network | Hoodi Testnet (Chain ID `560048`) |
| Contract Address | `0xFeC3b089CDc3da263D529a9BFb2daC1c92d272Fb` |
| ดู Contract บน Explorer | https://hoodi.etherscan.io/address/0xFeC3b089CDc3da263D529a9BFb2daC1c92d272Fb |

---

## ✅ สิ่งที่ต้องมีก่อนใช้งาน

1. **เบราว์เซอร์ที่ติดตั้ง MetaMask** — ดาวน์โหลดได้ที่ https://metamask.io/download/
2. **ETH บน Hoodi Testnet** — ขอฟรีได้จาก Hoodi faucet (ใช้จ่ายค่า gas และใช้ฝาก)

---

## 🚀 วิธีใช้งาน

เมื่อเปิดหน้าเว็บ ระบบจะ **เชื่อมต่อ Infura → Smart Contract → MetaMask ให้อัตโนมัติ** (ครั้งแรก MetaMask จะเด้งขึ้นมาขออนุญาต ให้กด **Connect**)

### ① เชื่อมต่อ Infura + Smart Contract (อัตโนมัติ)

การ์ดแรกแสดงสถานะการเชื่อมต่อกับ blockchain

- **Network** — `Hoodi Testnet (chainId 560048)`
- **Latest block** — เลข block ล่าสุด อัปเดตเองทุก 12 วินาที
- **Contract** — address ของ Smart Contract ที่ใช้งาน

เมื่อป้ายมุมขวาบนขึ้น **Connected** และวงกลมหมายเลข 1 เป็นสีเขียว แปลว่าพร้อมแล้ว

### ② เชื่อมต่อ MetaMask

- ถ้ายังไม่เชื่อมต่อ ให้กดปุ่ม **🦊 Connect MetaMask**
- ถ้า MetaMask ไม่ได้อยู่บน Hoodi ระบบจะ **ขอสลับ network ให้อัตโนมัติ** (และเพิ่ม Hoodi ให้ถ้ายังไม่มี) → กด **Approve / Switch** ใน MetaMask
- เมื่อสำเร็จ ปุ่มจะเปลี่ยนเป็น **✅ Connected 0x1234…abcd** และแสดง
  - **Account** — address ของกระเป๋าที่ใช้อยู่
  - **Wallet ETH** — ยอด ETH ในกระเป๋า
  - **Deployed by** — address ของผู้สร้าง contract

กล่องสถานะจะแสดง *"เชื่อมต่อ Infura, Smart Contract และ MetaMask อัตโนมัติสำเร็จ — พร้อมใช้งาน"*

### ③ ตรวจสอบยอดเงิน (Check Balance)

- ยอดเงินที่ฝากไว้ในธนาคารแสดงเป็นตัวเลขขนาดใหญ่ (หน่วย ETH)
- กด **🔄 Check Balance** เพื่อดึงยอดล่าสุด
- **ไม่เสียค่า gas** และไม่ต้องยืนยันใน MetaMask

### ④ ฝากเงิน (Deposit)

1. ใส่จำนวน ETH ที่ต้องการฝาก เช่น `0.01`
2. กด **Deposit**
3. MetaMask จะเด้งขึ้นมา → ตรวจสอบจำนวนเงินและค่า gas → กด **Confirm**
4. รอประมาณ 12–15 วินาที จนกล่องสถานะแสดง *"ฝากเงิน … ETH สำเร็จ ✔"*
5. ยอดในธนาคารจะเพิ่มขึ้น และยอด Wallet ETH จะลดลง (รวมค่า gas)

### ⑤ ถอนเงิน (Withdraw)

1. ใส่จำนวน ETH ที่ต้องการถอน (ต้องไม่เกินยอดที่ฝากไว้)
2. กด **Withdraw** → ยืนยันใน MetaMask
3. เมื่อสำเร็จ เงินจะกลับเข้ากระเป๋า MetaMask และยอดในธนาคารจะลดลง

> 💡 ทุกครั้งที่ทำรายการ กล่องสถานะจะมีลิงก์ **Transaction Hash** กดเพื่อดูรายละเอียดบน Hoodi Etherscan ได้

---

## ℹ️ ข้อควรรู้

- **ยอดเงินแยกตามบัญชี** — แต่ละ address มียอดของตัวเอง ใครก็ใช้เว็บนี้ได้ด้วยกระเป๋าของตัวเอง และเห็นเฉพาะยอดของตัวเอง
- **ไม่มี MetaMask ก็เปิดเว็บได้** — จะเห็นข้อมูล network และ contract แต่จะดูยอด ฝาก หรือถอนไม่ได้จนกว่าจะเชื่อมต่อ MetaMask
- **เปลี่ยนบัญชีหรือ network ใน MetaMask** หน้าเว็บจะรีเฟรชและเชื่อมต่อใหม่ให้อัตโนมัติ
- **ฝาก / ถอน มีค่า gas** เสมอ จึงต้องมี ETH เหลือในกระเป๋ามากกว่าจำนวนที่จะฝากเล็กน้อย
- **MetaMask ต้องอยู่บน Hoodi Testnet** ถ้าอยู่ network อื่น ปุ่ม Deposit / Withdraw จะกดไม่ได้

## 🛠️ แก้ปัญหาเบื้องต้น

| ข้อความที่เห็น | สาเหตุ / วิธีแก้ |
|---|---|
| เชื่อมต่อ Infura ไม่สำเร็จ / ป้ายขึ้น *หลุดการเชื่อมต่อ* | เชื่อมต่อ blockchain ไม่ได้ชั่วคราว → ตรวจสอบอินเทอร์เน็ตแล้วรีเฟรชหน้าเว็บ |
| ไม่พบ MetaMask | ยังไม่ได้ติดตั้ง MetaMask หรือเปิดจากมือถือ → ติดตั้ง extension แล้วรีเฟรช (บนมือถือให้เปิดผ่านเบราว์เซอร์ในแอป MetaMask) |
| สลับ network ไม่สำเร็จ … กรุณาเลือก Hoodi Testnet ใน MetaMask เอง | กด Reject ตอนขอสลับ network → เลือก Hoodi ใน MetaMask เอง แล้วรีเฟรช |
| ผู้ใช้ยกเลิกรายการใน MetaMask | กด Reject ในหน้าต่าง MetaMask → ทำรายการใหม่อีกครั้ง |
| กรุณาใส่จำนวนเงินที่มากกว่า 0 | ช่องจำนวนว่างหรือเป็น 0 |
| ยอดเงินไม่พอ — not enough money | ถอนเกินยอดที่ฝากไว้ → กด Check Balance แล้วใส่จำนวนใหม่ |
| insufficient funds | ETH ในกระเป๋าไม่พอสำหรับจำนวนเงิน + ค่า gas → ขอเพิ่มจาก Hoodi faucet |
