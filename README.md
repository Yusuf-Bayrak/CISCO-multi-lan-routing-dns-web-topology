# Enterprise Multi-LAN Network Topology (Cisco Packet Tracer)

Bu proje, Cisco Packet Tracer üzerinde tasarlanmış; 3 farklı yerel ağı (LAN), yönlendirme (routing) mekanizmasını ve temel ağ servislerini (DNS, DHCP, Web HTTP) içeren kurumsal bir ağ simülasyonudur.

---

## 📌 Topoloji Mimarisi

Topoloji, bir ana yönlendirici (Router 2911) üzerinden haberleşen 3 bağımsız departman ağından oluşmaktadır:

* **LAN A (Muhasebe):** `192.168.10.0/24`
* **LAN B (Ar-Ge):** `192.168.20.0/24`
* **LAN C (Pazarlama & Reklam):** `192.168.30.0/24`

---

## 🌐 IP ve Servis Yapılandırması

| Departman / Ağ | IP Bloğu | Cihazlar | Sunucu / Rol | Sunucu IP |
| :--- | :--- | :--- | :--- | :--- |
| **Muhasebe (LAN A)** | `192.168.10.0/24` | 2 PC, Switch | DNS Server | `192.168.10.100` |
| **Ar-Ge (LAN B)** | `192.168.20.0/24` | 2 PC, Switch | DHCP Server | `192.168.20.100` |
| **Pazarlama (LAN C)** | `192.168.30.0/24` | 2 PC, Switch | Web (HTTP) Server | `192.168.30.30` |

---

## ⚙️ Uygulanan Konfigürasyonlar

* **Inter-Network Routing:** LAN A, LAN B ve LAN C arasındaki paket iletimi Cisco 2911 Router bacakları üzerinden yapılandırıldı.
* **DNS Yapılandırması:** `www.abc.com` alan adı kaydı `192.168.30.30` Web sunucusu IP adresi ile eşleştirildi.
* **HTTP Servisi:** Web sunucusunda web barındırma hizmeti devreye alındı.
* **DHCP Servisi:** Ağdaki uç birimlerin dinamik IP yapılandırması simüle edildi.

---

## ✅ Test ve Doğrulama

1. **ICMP Ping Testleri:** Farklı LAN'lardaki uç birimler (PC'ler) ve sunucular arasında uçtan uca erişilebilirlik doğrulandı.
2. **DNS & Web Çözümlemesi:** Muhasebe (LAN A) ve Ar-Ge (LAN B) ağlarındaki PC'lerin web tarayıcısından `http://www.abc.com` adresine sorunsuz erişim sağlandı.

---

## 🚀 Dosyayı Çalıştırma

1. Bilgisayarınızda **Cisco Packet Tracer** kurulu olduğundan emin olun.
2. Depodaki `.pkt` uzantılı dosyayı indirip Packet Tracer ile açın.
3. Herhangi bir PC'nin **Desktop > Web Browser** sekmesinden `www.abc.com` adresine giderek testi tekrarlayabilirsiniz.
