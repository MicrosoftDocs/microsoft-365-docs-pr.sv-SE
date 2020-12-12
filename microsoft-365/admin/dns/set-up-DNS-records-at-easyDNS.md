---
title: Skapa DNS-poster på easyDNS för Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på easyDNS för Microsoft.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656825"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Skapa DNS-poster på easyDNS för Microsoft

[Läs frågor och svar om domäner ](../setup/domains-faq.yml) om du inte hittar det du letar efter. 
  
Du måste lägga till följande DNS-poster på din registrators webbplats för att dirigera e-post till Microsoft, använda din domän för Teams och Skype för företag, och så vidare.
  
Obs! SRV-poster är för närvarande inte tillgängliga under alla easyDNS-tjänste paket. Du kan behöva uppgradera till en högre tjänst nivå med easyDNS för att lägga till SRV-poster som krävs för Skype för företag.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Verifiera att du äger domänen med en TXT-post

1. Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter. 
    
2. Under rubriken **alla domäner** väljer du **DNS.**
    
3. Under rubriken **TXT Records** väljer du knappen Redigera (Skift nyckel ikonen). 
    
4. Ange följande poster i textfälten:
    
    |**Värd**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX (Använd det värde du gav på sidan Domains Center-domäner)  <br/> |
   
5. Välj **Nästa**. 
    
6. Kontrol lera att posten är korrekt och välj sedan **Bekräfta**. 
    
7. Vänta några minuter innan du fortsätter, så att den post som du just skapade kan spridas via Internet och identifieras av Microsoft.
    
8. Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
    
9. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
10. På sidan **Domains** väljer du den domän du verifierar. 
    
11. På sidan **Setup** väljer du **Start setup.**
    
12. På sidan **Verify domain** väljer du **Verify**. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Lägga till en MX-post för att dirigera e-post till Microsoft

1. Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter. 
    
2. Under rubriken **alla domäner** väljer du **DNS.**
    
3. Under rubriken **MX Records** väljer du knappen Redigera (Skift nyckel ikonen). 
    
4. Ange följande poster i textfälten:
    
    |**E-POST FÖR ZONEN**|**E-POSTSERVER**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>. mail.protection.outlook.com (Hämta \<domain-key\> värdet från sidan Domains för administrations centret)  <br/> |siffrorna  <br/> |
   
2. Om du vill spara dina andra MX-poster för säkerhets kopiering kan du kopiera dem till en annan plats. Innan du fortsätter tar du bort alla andra MX-poster här.
    
5. Välj **Nästa**. 
    
6. Kontrol lera att posten är korrekt och välj sedan **Bekräfta**. 
    
## <a name="add-the-required-cname-records"></a>Lägga till de CNAME-poster som krävs

1. Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter. 
    
2. Under rubriken **alla domäner** väljer du **DNS.**
    
3. Under rubriken **CNAME/Ali-poster** väljer du knappen Redigera (Skift nyckel ikonen). 
    
4. Ange följande poster i textfälten:


    |**HOST (värd)**|**Adress (måste sluta med ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Välj **Nästa**. 
    
6. Kontrol lera att posten är korrekt och välj sedan **Bekräfta**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost

1. Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter. 
    
2. Under rubriken **alla domäner** väljer du **DNS.**
    
3. Under rubriken **TXT Records** väljer du knappen Redigera (Skift nyckel ikonen). 
    
4. Ange följande poster i textfälten:
    
    |**Värd**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Välj **Nästa**. 
    
6. Kontrol lera att posten är korrekt och välj sedan **Bekräfta**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft

Obs! SRV-poster är för närvarande inte tillgängliga under easyDNS ' Domain plus Service Level. Du kan behöva uppgradera till en högre service nivå med easyDNS för att lägga till SRV-poster 
  
1. Gå till [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) och logga in med dina inloggnings uppgifter. 
    
2. Under rubriken **alla domäner** väljer du **DNS.**
    
3. Under rubriken **SRV Records** väljer du knappen Redigera (Skift nyckel ikonen). 
    
4. Ange följande poster i textfälten:
    
    |**SERVICE (tjänst)**|**PROTO**|**HOST (värd)**|**PRI**|**WGT**|**PORT**|**MÅL (måste sluta med ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |9.1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |9.1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Välj **Nästa**. 
    
6. Kontrol lera att posten är korrekt och välj sedan **Bekräfta**. 
    

