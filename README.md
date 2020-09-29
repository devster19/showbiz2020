# GMM SHOWBIZ
ตัวอย่าง API Response สำหรับ GMM SHOWBIZ

## คำอธิบาย Response (object)
+ type : (string) ตัวกำหนดประเภทของ Push Notification
+ userData: {} (object)
    + id : (string) GMM Member ID
    + name : (string) ชือ-สกุล
    + email: (string) อีเมล
    + token: (string) token ของผู้ใช้งาน
    + deviceId: (string) device ID สำหรับใช้ในการยิง Push Notification
+ orderData: : [{}]  (Array of object)
    + orderId : (string) ไอดีสั่งซื้อสินค้า
    + description: (string) รายละเอียดสำหรับต้องการระบุเพิ่มเติม,
    + orderStatus: (string) สภานะการส่งสินค้า
    + totalPrice: (number) ยอดชำระทั้งหมด
    + createdDate": (datetime) วันเวลาทำการสั่งซื้อ
    + deliveredDate: (datetime) วันเวลาส่งสินค้า
    + orderItems: [{}]  (Array of object)
        - id: (string) ไอดีสินค้า
        - name: (string) ชื่อของสินค้า
        - category: (string) ประเภทของสินค้า
        - price: (number) ราคาสินค้า
        - discount: (number) ส่วนลดของสินค้า
        - description: (string) ข้อรายละเอียดเพิ่มเติมของสินค้า    
        - productImage: (string) ลิ้งครูปภาพสินค้า    
        - productUrl: (string) ลิ้งคสินค้า                         
  

        
## Create a New Push Notification [/notification]

### After purchase items from GMM SHOP  [POST]
* ทำการยิง push notification โดยส่งรายละเอียดในการสั่งซื้อสินค้า

+ Request (application/json)

        {
            "type":"gmmshop",
            "userData":{
                "memberId": "gmm-1000873",
                "name":"สมพล ชอบฟังเพลง",
                "email":"c.somphol19@mail.com"
                "token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoi4Liq4Lih4Lie4LilIOC4iuC4reC4muC4n-C4seC4h-C4sOC4nuC4peC4hyJ9",
                "deviceId":"FCDBD8EF-62FC-4ECB-B2F5-92C9E79AC7F9"
            },
            "orderData":[
                {
                    "orderId": "ae76865",
                    "description": "",
                    "orderStatus":"send",
                    "totalPrice":790.00,
                    "createdDate": "2019-07-25T08:45:00",
                    "deliveredDate": null,
                    "orderItems":[
                        {
                            "id": "ae76865-001",
                            "name": "T-Shirt Give Me 5 โลโก้",
                            "category":"T-Shirt"
                            "price": 390.00,
                            "discount":40.00
                            "description": "",
                            "productImage":"https://www.gmmshops.com/pic_thumb?src=uploads/pro…6404-shirt%20Logo%20Give%20Me%205.jpg&w=418&h=500",
                            "productUrl":"https://www.gmmshops.com/product/t-shirt-give-me-5-%E0%B9%82%E0%B8%A5%E0%B9%82%E0%B8%81%E0%B9%89-1234",
                            
                        },
                        {
                            "id": "ae76865-302",
                            "name": "ป้าย LED I <3 PECK",
                            "category":"peck-official-merchirt"
                            "price": 400.00,
                            "discount":00.00
                            "description": "ป้ายไฟพิเศษ สำหรับแฟนคลับของเป็ก ผลิตโชค",
                            "productImage":"https://www.gmmshops.com/pic_thumb?src=uploads/pro…6404-shirt%20Logo%20Give%20Me%205.jpg&w=418&h=500",
                            "productUrl":"https://www.gmmshops.com/product/t-shirt-give-me-5-%E0%B9%82%E0%B8%A5%E0%B9%82%E0%B8%81%E0%B9%89-1234",
                            
                        }
                    ]
                }
            ]
        }
        
+ Response 201 (application/json)

    + Body

            {
                "id": "b98881cc-1e94-4366-bbd9-db8f3429292b",
                "result": "Notification created!"
            }





            
