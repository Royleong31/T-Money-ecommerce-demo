# T Money e-commerce demonstration site
- This is used to demonstrate mechant integrations with T Wallet.
- When a user clicks checkout, a new checkout ID is created on the site to uniquely identify the checkout. 
- The checkout ID is used as an idempotent ID in the merchantRequestQR mutation. So even if multiple mutation requests are sent, only 1 will succeed. This ensures that the merchant does not accidentally create multiple payment QR codes, which can lead to duplicate payments.
- Once the merchantRequestQR mutation returns a response, this site will generate a QR code with the id that is returned. 
- The user will then scan the QR code and make a payment to the ecommerce site.
- When the user is in the payments page, the site will continuously poll T Money's backend to check the status of the payment. 
- Once the payment has been confirmed, a confirmation message is shown to users.


