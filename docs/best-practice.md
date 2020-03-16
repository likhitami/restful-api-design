# API (Application Programming Interface) 

- Http Method.
- Http status code.
- Api endpoint.
- Sorting, searching, filtering and pagination.
- Naming.
- Versioning.

## [Http Method (Verb)](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods).
ปกติแล้ว http method ที่เราคุ้นเคยนั้นมี get และ post ในการออกแบบ api นั้น เราสามารถใช้ verb อื่นเพื่อเข้าถึงและกระทำบางอย่างกับข้อมูล ซึ่ง verb หลัก ๆ ที่มักใช้กันนั้นมี 4 verb ประกอบด้วย
- **GET** ดึงข้อมูลจาก resource
- **POST** สร้างข้อมูลใหม่
- **PUT** ปรับปรุงข้อมูล หรือสร้างใหม่กรณีที่ไม่มีอยู่
- **DELETE** ลบข้อมูล

## Http Status Code.
**2xx (Success)**
 - *200 Ok* code มาตรฐานสำหรับ request สำเร็จ
 - *201 Create* สร้างข้อมูลใหม่สำเร็จ
 - *204 No Content* สำเร็จ แต่ไม่ต้องการส่งข้อมูลใด ๆ กลับ
 **4xx (Client Error)**
 - *400 Bad Request*
 - *401 Unauthorized * การเข้าถึงไม่ได้รับอนุญาต
 - *403 Forbidden* การเข้าถึงได้รับอนุญาต แต่ไม่สามารถเข้าถึง resource ได้ 
 - *404 Not Found*
 **5xx (Server Error)**
 - *500 Internal Server Error* เกิดปัญหาบางอย่างใน server และต้องการแก้ไขจากผู้ดูแล
 - *503 Service Unavailable* เซิฟเวอร์ไม่สามารถเข้าถึงได้ อาจจะเกิดจากการปรับปรุง server หรือ server ล่ม

## API Endpoint.
จุดเรียกใช้งาน api โดยทั่วไปจะมีคำที่เกี่ยวข้องอยู่ 3 คำคือ resource, collections และ url  
- **Resource** object ตัวหนึ่งซึ่งใช้แทนบางอย่างเช่น รถ, คน, พนักงาน
- **Collections** กลุ่มของ resource และเป็นรูปพหูพจน์ของ resource เสมอ เช่น กลุ่มของพนักงาน, กลุ่มของรถ เป็นต้น หากถามว่าแล้วบริษัท เป็นกลุ่มของพนักงานใช่หรือไม่ 
คำตอบคือ ไม่ใช่ เนื่องจากบริษัทนั้นเป็นตัวแทนของตัวบริษัทเอง โดยมีกลุ่มของพนักงานเป็นหนึ่งในคุณบัติเท่านั้น
- **URL (Uniform Resource Locator)** เป็นเส้นทางเพื่อเข้าถึง resource เช่น /employees เพื่อเข้าถึงพนักงานทั้งหมด หรือ /employees/2 เพื่อเข้าถึงพนักงานที่มี id = 2 เป็นต้น  

การตั้งชื่อ endpoint นั้น
- ควรจะมีเพียงชื่อของ resource เท่านั้น ไม่ควรจะมี verb อยู่ภายในด้วย เช่น  
ตั้งชื่อว่า /employees แทนการตั้งชื่อ /getAllEmployee
- ควรตั้งชื่อเป็นพหูพจน์ หรือก็คือ collections นั่นเอง
- เพื่อให้ชื่อเป็นไปในแนวทางเดียวกัน แนะนำให้ใช้ camelCase ในการตั้งชื่อ
