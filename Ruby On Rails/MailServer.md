# Rails Mailserver

### Opinions

* Smtp buat kirim2 email dari app pake sendgrid..
Email@domain.com nya pake zoho.
* Ato klo punya mailchimp yg pro, bisa pake mandrill utk smtp nya..
* Bisa pake fitur inbound webhook nya sendgrid.. ntr konten2nya di parsing di app dan ditampilin di app nya..
https://sendgrid.com/docs/API_Reference/Webhooks/parse.html                         
dulu pake mandrill.. cm skrng mandrill cm bsa dipake klo ada mailchimp pro..😪                         
Misal user register.. lalu dpt email mamat@app.com
mamat sblm @ itu sbg identifier nya.. klo orang ngirim ke email itu, app akan cari user by mamat tsb.. lalu diproses (simpen ke db, lalu ditampilkan di inbox page)                         
Dan kyknya pake inbound webhook lbh costless drpd bikin mail server sendiri. Dan kyknya klo pake server sendiri, susah integrasiin klo ada user baru = bikin email.

Klo pake inbound, email tsb abstrak 😸

* Alternatif mailserver use SMTP elasticsmtp

