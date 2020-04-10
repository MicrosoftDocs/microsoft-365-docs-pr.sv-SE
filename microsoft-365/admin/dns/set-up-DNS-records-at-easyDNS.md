---
title: Skapa DNS-poster på easyDNS för Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på easyDNS för Office 365.
ms.openlocfilehash: 9d48896de8f841863e25929a46b2f1d2e1b3ced2
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210558"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a>Skapa DNS-poster på easyDNS för Office 365

[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter. 
  
Du måste lägga till alla följande DNS-poster på registratorns webbplats för att dirigera e-post till Office 365, använda domänen för Teams och Skype för företag och så vidare.
  
SRV-poster är för närvarande INTE tillgängliga under alla easyDNS-servicepaket. Du kan behöva uppgradera till en högre servicenivå med easyDNS för att lägga till SRV-poster som krävs för Office 365 Skype för företag.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Kontrollera att du äger domänen med en TXT-post

1. Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter. 
    
2. Välj dns under rubriken **alla domäner.** **dns.**
    
3. Under rubriken **TXT-poster** väljer du redigeringsknappen (skiftnyckelikonen). 
    
4. Ange följande poster i textfälten:
    
    |**Värd**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXX (Använd det värde som du har angett på sidan Domäner för administrationscenter)  <br/> |
   
5. Välj **NÄSTA**. 
    
6. Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**. 
    
7. Vänta några minuter innan du fortsätter, så att posten som du just skapade kan spridas över Internet och identifieras av Office 365.
    
8. Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.
    
9. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
10. På sidan **Domains** väljer du den domän du verifierar. 
    
11. Välj **Starta inställningar** på sidan **Installationsprogrammet.**
    
12. På sidan **Verify domain** väljer du **Verify**. 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a>Lägga till en MX-post för att dirigera e-post till Office 365

1. Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter. 
    
2. Välj dns under rubriken **alla domäner.** **dns.**
    
3. Under rubriken **MX-poster** väljer du redigeringsknappen (skiftnyckelikonen). 
    
4. Ange följande poster i textfälten:
    
    |**POST FÖR ZON**|**E-POSTSERVER**|**Pref**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domännyckeln\>.mail.protection.outlook.com (Hämta ditt \<domännyckelvärde\> från sidan Domäner för administrationscenter)  <br/> |0  <br/> |
   
2. Om du vill spara dina andra MX-poster för säkerhetskopiering kan du kopiera dem någonstans. Innan du går vidare tar du bort alla andra MX-poster här.
    
5. Välj **NÄSTA**. 
    
6. Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**. 
    
## <a name="add-the-required-cname-records"></a>Lägga till de CNAME-poster som krävs

1. Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter. 
    
2. Välj dns under rubriken **alla domäner.** **dns.**
    
3. Under rubriken **CNAME/Alias-poster** väljer du redigeringsknappen (skiftnyckelikonen). 
    
4. Ange följande poster i textfälten:


    |**HOST (värd)**|**Adress (Måste sluta med ett ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Välj **NÄSTA**. 
    
6. Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost

1. Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter. 
    
2. Välj dns under rubriken **alla domäner.** **dns.**
    
3. Under rubriken **TXT-poster** väljer du redigeringsknappen (skiftnyckelikonen). 
    
4. Ange följande poster i textfälten:
    
    |**Värd**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Välj **NÄSTA**. 
    
6. Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365

SRV-poster är för närvarande INTE tillgängliga under easyDNS Domain Plus-tjänstnivå. Du kan behöva uppgradera till en högre servicenivå med easyDNS för att lägga till SRV-poster 
  
1. Gå [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) till och logga in med dina autentiseringsuppgifter. 
    
2. Välj dns under rubriken **alla domäner.** **dns.**
    
3. Under rubriken **SRV-poster** väljer du redigeringsknappen (skiftnyckelikonen). 
    
4. Ange följande poster i textfälten:
    
    |**SERVICE (tjänst)**|**Proto**|**HOST (värd)**|**Pri**|**Wgt**|**PORT**|**TARGET(Måste sluta med ett ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Välj **NÄSTA**. 
    
6. Kontrollera att posten är korrekt och välj sedan **BEKRÄFTA**. 
    

