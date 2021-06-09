# Release Notes

## June 2021

### 2021-06-21

1. AOS_Products: change relationship of AOS Products and Markers to one-to-many 
2. Markers
  * add marker_type_c: origin, destination

## May 2021

### 2021-05-26

1. Account: 客戶類型 改為 多選 account_type -> multiple_enum 
2. AOS_Products: 新增 提前預訂天數 advance_booking_days_c 
3. AOS_Products_Quotes 增加 出團日 departure_datetime_c
4. AOS_Invoice status 
  * 新增修改狀態 status
     * 原本
       Paid,Canceled,Not Paid,Return
     * 新增
       Paid,PendingPaymentConfirmation,Unpaid,<br>
       Cancelled,Rescheduling,Returning,Returned
  * 新增 payment_method
      credit,credit_union,paypal,<br>
      installment,applepay,atm,<br>
      stripeCreditcard,other,remittance,<br>
      paynow
  * 新增 發票號碼 receipt_number_c
5. 新增 Map-Markers Module
