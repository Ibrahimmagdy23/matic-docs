---
id: meta-transactions
title: ธุรกรรม Meta
sidebar_label: Overview
description: เรียนรู้เกี่ยวกับธุรกรรม Meta และวิธีใช้งาน
keywords:
  - docs
  - polygon
  - matic
  - transactions
  - meta transactions
  - gasless
image: https://matic.network/banners/matic-network-16x9.png
slug: meta-transactions
---

การเรียกสัญญาอัจฉริยะรายวันอยู่ที่ระดับสูงสุดประมาณ 2.5 ถึง 3 ล้านครั้งต่อวันDApp เริ่มตระหนักถึงประโยชน์ใช้สอยของตัวเอง แต่ก็กำลังตกเป็นเหยื่อของความสำเร็จของตนเองหรือความสำเร็จของผู้อื่นเนื่องจากค่าแก๊สนอกจากนี้ ยังมีอุปสรรคในการเริ่มต้นใช้งานของผู้ใช้และความท้าทายของ UX ในปัจจุบันที่ไม่ได้แก้ไขได้ง่ายๆ

## การให้บริการสัญญาอัจฉริยะ {#servicing-smart-contracts}

สัญญาอัจฉริยะผ่านการออกแบบมาให้เป็นเครื่องกำหนดสถานะที่ดำเนินการเมื่อมีการจ่ายค่าธรรมเนียมการทำธุรกรรมเพื่อดำเนินการกับลอจิกของสัญญาโดยใช้ทรัพยากรการคำนวณของเครือข่ายซึ่งทำได้โดยแบบจำลองตัววัดค่าแก๊สบน Ethereum (และ Polygon)

## สถานะปัจจุบันของการทำธุรกรรม {#the-current-state-of-transacting}

มีข้อจำกัดสำหรับรูปแบบธุรกรรมแบบดั้งเดิมนี้บน Ethereum (และบล็อกเชนอื่นๆ ที่คล้ายคลึงกัน)ข้อจำกัดทั่วไปคือผู้ใช้ไม่มีวิธีจ่ายค่าแก๊สตามค่าเริ่มต้น ผู้ส่งของธุรกรรมจะทำหน้าที่เป็นผู้ชำระเงิน เนื่องจากรูปแบบการทำงานเหล่านี้มีร่วมกันเป็นคู่ ดังนั้นหากผู้ใช้พยายามสร้างและส่งธุรกรรม พวกเขาจะต้องรับผิดชอบค่าแก๊สที่เกี่ยวข้องในทำนองเดียวกัน หากผู้ใช้สร้าง โต้ตอบหรือเรียกใช้ DApp ผู้ใช้ต้องจ่ายค่าแก๊ส

ไม่ควรคาดหวังให้ผู้ใช้ทั่วไปซื้อคริปโตและจ่ายค่าแก๊สเพื่อโต้ตอบกับแอปพลิเคชันสิ่งที่สามารถทำได้เพื่อจัดการปัญหานี้คือการแยกผู้ส่งธุรกรรมออกจากการทำหน้าที่เป็นผู้ชำระเงิน ซึ่งช่วยเปิดโอกาสให้ขยายการดำเนินการธุรกรรมและเริ่มสร้างประสบการณ์การทำธุรกรรมราบรื่น

แทนที่จะดำเนินการกับธุรกรรมโดยตรง จะมีมิดเดิลแวร์ (ผ่านบุคคลที่สาม) เข้ามาเพื่อจัดการกับค่าแก๊สธุรกรรม Meta มีประโยชน์ก็ตรงนี้นั่นเอง

## ธุรกรรม Meta คืออะไร {#what-are-meta-transactions}

ธุรกรรม Meta ช่วยให้ทุกคนโต้ตอบกับบล็อกเชนได้ผู้ใช้ไม่จำเป็นต้องมีโทเค็นเพื่อชำระค่าบริการของเครือข่ายผ่านค่าธรรมเนียมการทำธุรกรรมทำได้โดยการแยกส่วนผู้ส่งธุรกรรมและผู้จ่ายค่าแก๊ส

โซลูชันที่สามารถช่วยผู้ใช้ใหม่เริ่มใช้งานและช่วยเหลือผู้ใช้ปัจจุบันได้

ผู้ดำเนินการธุรกรรมทำหน้าที่เป็นผู้ส่งแทนที่จะจ่ายค่าแก๊ส พวกเขาเพียงสร้างคำขอธุรกรรมโดยลงนามในการกระทำที่ต้องการ (พารามิเตอร์ธุรกรรม) กับคีย์ส่วนตัวธุรกรรม Meta เป็นธุรกรรม Ethereum ปกติที่มีพารามิเตอร์เพิ่มเติมในการสร้างธุรกรรม Meta

พารามิเตอร์ธุรกรรมที่ลงนามแล้วจะได้รับการส่งไปยังเครือข่ายรอง ซึ่งทำหน้าที่เป็นผู้ส่งต่อแม้ว่าจะมีรูปแบบที่แตกต่างกัน แต่โดยทั่วไปผู้ส่งต่อจะเลือกว่าธุรกรรมใดคุ้มค่าต่อการส่งด้วยการตรวจสอบความถูกต้องของธุรกรรมดังกล่าว (เช่น ความเกี่ยวข้องกับ DApp)เมื่อตรวจสอบความถูกต้องแล้ว ผู้ส่งต่อจะ Wคำขอ (ข้อความที่ลงนาม) ไว้ในธุรกรรมที่เกิดขึ้นจริง (ซึ่งหมายถึงมีการชำระค่าแก๊ส)และเผยแพร่ไปยังเครือข่าย โดยที่สัญญาจะ Unwrap ธุรกรรมโดยการตรวจสอบความถูกต้องของลายเซ็นเริ่มแรกและดำเนินการในนามของผู้ใช้

:::note คำว่า Meta และ Batch อาจดูคล้ายกันในบางส่วน

คำอธิบาย: ธุรกรรม Meta แตกต่างจากธุรกรรมแบตช์ ตรงที่ธุรกรรมแบตช์คือธุรกรรมหนึ่งๆ ที่สามารถส่งหลายธุรกรรมพร้อมกันและดำเนินการจากผู้ส่งรายเดียว(ที่ใช้ครั้งเดียวตามที่ระบุ) ตามลำดับ

:::

โดยสรุป ธุรกรรม Meta เป็นรูปแบบการออกแบบที่:

* ผู้ใช้ (ผู้ส่ง) ลงนามคำขอด้วยคีย์ส่วนตัวและส่งไปยังผู้ส่งต่อ
* ผู้ส่งต่อ Wrap คำขอลงในธุรกรรมและส่งไปยังสัญญา
* สัญญา Unwrap ธุรกรรมและดำเนินการ

ธุรกรรมดั้งเดิมบ่งบอกว่า "ผู้ส่ง" ก็เป็น "ผู้ชำระเงิน" ด้วยเมื่อนำความเป็น "ผู้ชำระเงิน" ออกจาก"ผู้ส่ง" ตัว "ผู้ส่ง" ก็จะกลายเป็นเหมือน "ผู้ตั้งใจ" กล่าวคือผู้ส่งแสดงเจตนาต่อธุรกรรมที่พวกเขาต้องการให้ดำเนินการบนบล็อกเชน โดยการลงนามข้อความที่มีพารามิเตอร์เฉพาะที่เกี่ยวข้องกับข้อความของพวกเขา และไม่ใช่ธุรกรรมที่สร้างขึ้นทั้งหมด

## กรณีการใช้งาน {#use-cases}

คุณสามารถจินตนาการถึงความสามารถของธุรกรรม Meta สำหรับการปรับขนาด DApp และการโต้ตอบกับสัญญาอัจฉริยะได้ผู้ใช้ไม่เพียงสามารถสร้างธุรกรรมแบบไม่ใช้ค่าแก๊สได้เท่านั้น แต่ยังสามารถทำได้หลายครั้งและด้วยเครื่องมืออัตโนมัติ ธุรกรรม Meta สามารถมีอิทธิพลต่อแอปพลิเคชันรุ่นถัดไปสำหรับกรณีการใช้งานจริงธุรกรรม Metaช่วยให้เกิดประโยชน์อย่างแท้จริงในลอจิกของสัญญาอัจฉริยะ ซึ่งมักถูกจำกัดเนื่องจากค่าแก๊สและการโต้ตอบที่ต้องมีในเชน

### ตัวอย่างพร้อมการโหวต {#example-with-voting}

ผู้ใช้ต้องการมีส่วนร่วมในการกำกับดูแลในเชน และพวกเขาต้องการโหวตเพื่อผลลัพธ์หนึ่งผ่านสัญญาการโหวตผู้ใช้จะลงนามข้อความ ซึ่งระบุการตัดสินใจของผู้ใช้ในการโหวตสัญญาหนึ่งแต่ดั้งเดิม พวกเขาจะต้องจ่ายค่าแก๊สสำหรับการโต้ตอบกับสัญญา (และรู้วิธีโต้ตอบกับสัญญา) แต่พวกเขาสามารถลงนามธุรกรรม Meta (นอกเชน) ด้วยข้อมูลที่จำเป็นสำหรับการโหวตและส่งต่อไปยังผู้ส่งต่อซึ่งจะทำธุรกรรมในนามของพวกเขา

ข้อความที่ลงนามได้รับการส่งไปยังผู้ส่งต่อ (พารามิเตอร์ธุรกรรมที่ลงนามเกี่ยวกับข้อมูลการโหวต)ผู้ส่งต่อตรวจสอบว่าธุรกรรมนี้เป็นการโหวตที่สำคัญ, Wrap คำขอการโหวตลงในธุรกรรมจริง,จ่ายค่าแก๊ส และเผยแพร่ไปยังสัญญาการโหวตทุกอย่างจะออกมาเมื่อถึงจุดสิ้นสุดของสัญญาการโหวตและการโหวตดำเนินการในนามผู้ใช้

## ลองดูสิ {#try-them-out}

สมมติว่าคุณคุ้นเคยกับวิธีต่างๆ ในการผสานรวมธุรกรรม Meta ในDApp ของคุณ และขึ้นอยู่กับว่าคุณกำลังย้ายไปยังธุรกรรม Meta หรือสร้าง DApp ใหม่ในการใช้งาน

ในการผสานรวม DApp ของคุณกับธุรกรรม Meta บน Polygon คุณสามารถเลือกหนึ่งในผู้ส่งต่อต่อไปนี้หรือสร้างโซลูชันที่กำหนดเอง:

* [Biconomy](https://docs.biconomy.io/products/enable-gasless-transactions)
* [Gas Station Network (GSN)](https://docs.opengsn.org/#ethereum-gas-station-network-gsn)
* [Infura](https://infura.io/product/ethereum/transactions-itx)
* [Gelato](https://docs.gelato.network/developer-products/gelato-relay-sdk)
