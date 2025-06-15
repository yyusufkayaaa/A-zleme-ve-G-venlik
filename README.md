# Ag ızleme ve guvenlik 
 Analizi Projesi ADIMLARI
NOT: ADIMLARIN EKRAN GÖRSELLERİ DEPODA MEVCUTTUR.

HTTP portunu izlemek için "sudo tcpdump port 80" komutunu yazdık ve sonrasında başka bir terminal üzerinden example.com sitesine istek gönderdik.

Gönderdiğimiz istek sonrası, izlediğimiz port üzerine log düşmeye başladı.

Sonrasında "sudo iptables -P INPUT DROP sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT sudo iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT" Komutları ile Firewall kuralları oluşturduk.

Bir sonraki adımda "sudo tcpdump -i eth0 -w trafik.txt" komutu kullanarak izlediğimiz port'un logları bu dosya üzerine yazılıyor ve anlık Ağ izleme ve güvenlik analizi yapmış oluyoruz.
