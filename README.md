## Subdomain axtarışı   — Web əsaslı Subdomain Enumeration Aləti (Python + Flask)

Bu layihə Python dili və Flask web çərçivəsi ilə yazılmış bir *Subdomain Enumeration* (subdomain tapma) alətidir. 
İstifadəçi interfeysi sadə və istifadəsi asandır — brauzerdən daxil olaraq domain adı verilir və 4 fərqli passiv mənbədən subdomain-lər toplanır.

## Əsas Xüsusiyyətlər

- *Web interfeys* — Flask ilə hazırlanıb, localhost:5000 ünvanında çalışır.
- *Daxil edilən domain* üçün subdomain-ləri tapır:
  - crt.sh (SSL sertifikatları arxivindən)
  - RapidDNS
  - BufferOver DNS
  - Wayback Machine (web.archive.org)
- Tapılan bütün subdomain-lər təmizlənmiş şəkildə və səliqəli list formatında göstərilir.
- Sadə və istifadəçi dostu HTML interfeysi



### Əvvəlcədən Tələblər (Dependencies)

Layihənin işləməsi üçün aşağıdakı Python kitabxanalarını quraşdırmalısınız:

pip install flask requests

## İSTİFADƏ QAYDASI 
kodu  subdomain.py  fayılına yerləşdiririk python3 ilə işə salırıq.

python3 subdomain.py


## Brauzerdə aç 
http://127.0.0.1:5000



## Alqoritm belə işləyir:

1. İstifadəçi POST sorğusu ilə domain adı daxil edir.
2. Aşağıdakı metodlar çağırılır:

get_subdomains_crtsh(domain)
get_subdomains_rapiddns(domain)
get_subdomains_buffer(domain)
get_subdomains_wayback(domain)

3. Hər metod öz mənbəsindən nəticə qaytarır.
4. Bütün nəticələr set() ilə birləşdirilərək təkrarlar silinir.
5. Tapılan subdomain-lər brauzerdə göstərilir.
