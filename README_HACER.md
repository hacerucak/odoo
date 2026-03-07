Odoo CRM - Lead Score Özelliği Geliştirme Raporu
Bu rapor, Odoo CRM modülüne eklediğim "Müşteri Adayı Puanlama" (Lead Scoring) özelliğinin detaylarını ve teknik sürecini içermektedir.

Özelliğin Amacı
Sisteme düşen müşteri adaylarının kalitesini ölçmek ve satış ekibinin en değerli adaylara öncelik vermesini sağlamak amacıyla bir puanlama sistemi geliştirdim. Bu sistem, iletişim bilgileri tam olan adaylara daha yüksek puan vererek onları öne çıkarır.

Uyguladığım Teknik Değişiklikler
1. Veri Modeli Geliştirmesi (Python)
addons/crm/models/crm_lead.py
 dosyasında şu değişiklikleri yaptım:

lead_score
 adında yeni bir veritabanı alanı tanımladım.
Puanı otomatik hesaplayan 
_compute_lead_score
 fonksiyonunu yazdım.
Puanlama Kriteri: E-posta adresi varsa +20 puan, telefon numarası varsa +20 puan eklenir (Maksimum 40 puan).
2. Arayüz Entegrasyonu (XML)
addons/crm/views/crm_lead_views.xml
 dosyasını güncelleyerek:

Hesaplanan puanın hem "Aday" (Lead) hem de "Fırsat" (Opportunity) ekranlarında görünmesini sağladım.
Kullanıcı dostu olması için alanı "Priority" (Öncelik) bölümünün hemen altına konumlandırdım.
Kullanım ve Sonuç
Bir müşteri adayı girildiğinde veya güncellendiğinde, sistem iletişim bilgilerini kontrol ederek puanı anında hesaplar. Bu sayede CRM ekranında her adayın yanında sayısal bir kalite skoru görünür.

Bu geliştirme, projenin çatallanmış (fork) versiyonuna feat: add lead scoring feature to CRM module mesajıyla eklenmeye hazırdır.
