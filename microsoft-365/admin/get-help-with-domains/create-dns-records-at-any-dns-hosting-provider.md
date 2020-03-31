---
title: Skapa DNS-poster på vilken DNS-värd som helst för Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: Lär dig verifiera din domän och skapa DNS-poster på vilken DNS-värd som helst för Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 2d3c726f70ffb4588f7ae2fc8b53bf8f0c60e258
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809077"
---
# <a name="create-dns-records-at-any-dns-hosting-provider-for-office-365"></a>Skapa DNS-poster på vilken DNS-värd som helst för Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Kontrollera listan med [värdspecifika instruktioner](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver. 
  
Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).
  
Om du vill konfigurera posterna själv är det de här posterna som ska läggas till. Observera att verifieringsposten och MX-posten är unika för domänen. Om du vill konfigurera dem måste du skaffa och använda ett särskilt "token"-värde för din domän. I anvisningarna nedan förklaras hur du gör det.
  
> [!IMPORTANT]
> Det exakta namnet på rutorna eller *fälten* som du skriver eller klistrar in information i, för att skapa varje typ av DNS-post, skiljer sig åt för varje DNS-värd. Det kan finnas hjälp på DNS-värdens webbplats som kan hjälpa dig att mappa de anvisningar som vi visar här till de exakta fälten på webbplatsen. Kom ihåg att kontrollera i [Skapa DNS-poster för Office 365](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx) om vi har stegvisa instruktioner för din DNS-värd. > Vissa DNS-värdar tillåter inte att du skapar alla nödvändiga posttyper, vilket [orsakar tjänstbegränsningar](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) i Office 365. Om värden för din domän inte har stöd för exempelvis SRV-, TXT- eller CNAME-poster rekommenderar vi att du [överför din domän](../get-help-with-domains/buy-a-domain-name.md) till en DNS-värd som har stöd för alla nödvändiga poster. Om du vill ha en snabb och automatiserad process som konfigurerar med Office 365 rekommenderar vi att du överför domänen till GoDaddy. 
  
> [!NOTE]
> Det brukar bara ta några minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>Lägga till en TXT- eller MX-post för verifiering
<a name="BKMK_verify"> </a>

> [!NOTE]
> Du skapar bara en av dessa poster. TXT är den vanligaste posttypen, men den stöds inte av vissa DNS-värdar. I sådana fall skapar du en MX-post istället. 
  
Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
 **Ta reda på var på din DNS-värds webbplats som du kan skapa en ny post.**
  
1. Logga in på din DNS-värds webbplats.
    
2. Välj din domän.
    
3. Gå till den sida där du kan redigera DNS-poster för din domän.
    
 **Skapa posten.**
  
1. Beroende på om du skapar en TXT-post eller en MX-post gör du något av följande:
    
  - **Om du skapar en TXT-post använder du följande värden:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type**|**Alias** eller **Host Name**|**Värde**|**TTL**|
|TXT|Gör något av följande: skriv **@**, lämna fältet tomt eller skriv domännamnet.  <br/> **Obs!** Olika DNS-värdar har olika krav för det här fältet. |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.  <br/>        [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.  |
   
  - **Om du skapar en MX-post ska du använda följande värden:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type**|**Alias** eller **Host Name**|**Värde**|**Prioritet**|**TTL**|
|MX|Skriv antingen **@** eller domännamnet. |MS=ms *XXXXXXXX* <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.    <br/>       [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Under **Prioritet** anger du en lägre prioritet än den som eventuella befintliga MX-poster har, för att undvika konflikter med den MX-post som används för e-postflöde. <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv. |
   
2. Spara posten.
    
Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
  
3. På sidan **Setup** väljer du **Start setup**.
       
4. På sidan **Verify domain** väljer du **Verify**.   
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-mx-record-to-route-email"></a>Lägga till en MX-post för att dirigera e-post
<a name="BKMK_add_MX"> </a>

Lägg till en MX-post så att e-post för din domän kommer till Office 365.  *När du uppdaterar domänens MX-post kommer nu alla nya e-postmeddelanden till alla som använder din domän till Office 365*. E-postmeddelanden som du redan har finns kvar hos din nuvarande e-postvärd, om du inte bestämmer dig för att [migrera e-postmeddelanden och kontakter till Office 365](../setup/migrate-email-and-contacts-admin.md) till Office 365. 
  
  
 **Uppgift**
  
Gå till sidan där du kan skapa poster för domänen.
  
1. Logga in på DNS-värdens webbplats.
    
2. Välj din domän.
    
3. Gå till den sida där du kan redigera DNS-poster för din domän.
    
::: moniker range="o365-worldwide"

MX-posten du lägger till innehåller ett värde (värdet **Pekar på adress**) som ser ut ungefär så här: \<MX token\>.mail.protection.outlook.com, där \<MX token\> är ett värde som MSxxxxxxx. 

::: moniker-end

::: moniker range="o365-germany"

MX-posten du lägger till innehåller ett värde (värdet **Pekar på-adress**) som ser ut ungefär så här: \<MX token\>.mail.protection.outlook.de, där \<MX token\> är ett värde som MSxxxxxxx. 

::: moniker-end

1. Lägg till en ny MX-post på DNS-värdens webbplats.
    
    Nu [får du informationen för MX-posten](../get-help-with-domains/information-for-dns-records.md) från Office 365. 
    
2. För MX-posten (i föregående steg) kopierar du värdet för **Pekar på-adress**. 
    
    Du använder det här värdet i den post du skapar på DNS-värdens webbplats enligt beskrivningen i nästa steg.
    
3. I den nya MX-posten på DNS-värdens webbplats ska du kontrollera att fälten är inställda på exakt följande värden:
    
  - **Record Type**: **MX**.
    
  - **Prioritet**: Ställ in prioriteten för MX-posten till det högsta tillgängliga värdet, vanligtvis **0**.
    
    Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)
    
  - **Värdnamn**: **@**
    
  - **Pekar på-adress**: Klistra in värdet för **Pekar på-adress** som du just kopierade från Office 365 här. 
    
  - **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. 
    
4. Spara posten.
    
Ta bort eventuella andra MX-poster.
  
Om du har MX-poster för den här domänen som skickar e-post någon annanstans än till Office 365 ska du ta bort dem allihop.
  
## <a name="add-three-cname-records"></a>Lägga till tre CNAME-poster
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Följ anvisningarna nedan för att lägga till de tre CNAME-poster som krävs för Office 365. Om det finns ytterligare CNAME-poster i Office 365 lägger du till dem genom att följa samma allmänna anvisningar som visas här.
  
På DNS-värdens webbplats skapar du tre nya CNAME-poster, vanligtvis en i taget.
  
1. I rutorna för varje ny post skriver du in eller kopierar och klistrar in följande värden. När du har lagt till de tre första nya posterna väljer du att skapa ytterligare en CNAME-post.
    
|||||
|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Värd** <br/> |**Pekar på** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 timme  <br/> |
|CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 timme  <br/> |
|CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 timme  <br/> |
   
   > [!NOTE]
   > För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. > Dessa poster gäller inte för hybriddistributioner av Exchange, Lync och Skype för företag. 
  
2. Spara posterna när du är klar.
    
::: moniker-end
::: moniker range="o365-germany"

Följ anvisningarna nedan för att lägga till de tre CNAME-poster som krävs för Office 365. Om det finns ytterligare CNAME-poster i Office 365 lägger du till dem genom att följa samma allmänna anvisningar som visas här.
  
På DNS-värdens webbplats skapar du tre nya CNAME-poster, vanligtvis en i taget.
  
1. I rutorna för varje ny post skriver du in eller kopierar och klistrar in följande värden. När du har lagt till de tre första nya posterna väljer du att skapa ytterligare en CNAME-post.
    
|||||
|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Värd** <br/> |**Pekar på** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 timme  <br/> |
|CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 timme  <br/> |
|CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 timme  <br/> |
   
   > [!NOTE]
   > För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. > Dessa poster gäller inte för hybriddistributioner av Exchange, Lync och Skype för företag. 
  
2. Spara posterna när du är klar.
    
::: moniker-end

::: moniker range="o365-21vianet"

Följ anvisningarna nedan för att lägga till de tre CNAME-poster som krävs för Office 365. Om det finns ytterligare CNAME-poster i Office 365 lägger du till dem genom att följa samma allmänna anvisningar som visas här.
  
På DNS-värdens webbplats skapar du tre nya CNAME-poster, vanligtvis en i taget.
  
1. I rutorna för varje ny post skriver du in eller kopierar och klistrar in följande värden. När du har lagt till de tre första nya posterna väljer du att skapa ytterligare en CNAME-post.
    
|||||
|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Värd** <br/> |**Pekar på** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.partner.outlook.cn  <br/> |1 timme  <br/> |
|CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 timme  <br/> |
|CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 timme  <br/> |
   
   > [!NOTE]
   > För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. > Dessa poster gäller inte för hybriddistributioner av Exchange, Lync och Skype för företag. 
  
2. Spara posterna när du är klar.
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Lägga till två CNAME-poster för MDM (Mobile Device Management) för Office 365
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Office 365 måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. > (Om du inte har MDM kan du hoppa över det här steget.) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Värd** <br/> |**Pekar på** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 timme  <br/> |
|CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 timme  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Office 365 måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. > (Om du inte har MDM kan du hoppa över det här steget.) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Värd** <br/> |**Pekar på** <br/> |**TTL** <br/> |
|CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 timme  <br/> |
|CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 timme  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.
  
Redigera den befintliga SPF-posten eller skapa en ny TXT-post för SPF på DNS-värdens webbplats.
  
> [!IMPORTANT]
> SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot. För att skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Office 365. Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din domän i Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Därefter läser du [Använda DMARC för att validera e-post i Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. I rutorna för den nya posten skriver du, eller kopierar och klistrar in, den uppsättning värden nedan som gäller för din situation.
    
|||||
|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Värd** <br/> |**TXT Value** <br/> |**TTL** <br/> |
|TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |1 timme  <br/> |
   
   För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. 
    
2. Spara posten när du är klar.
    
3. Använd något av följande [SPF-verifieringsverktyg](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) för att verifiera SPF-posten

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
Redigera den befintliga SPF-posten eller skapa en ny TXT-post för SPF på DNS-värdens webbplats.
  
> [!IMPORTANT]
> SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot. För att skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Office 365. Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din domän i Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Därefter läser du [Använda DMARC för att validera e-post i Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. I rutorna för den nya posten skriver du, eller kopierar och klistrar in, den uppsättning värden nedan som gäller för din situation.
    
|||||
|:-----|:-----|:-----|:-----|
|**Posttyp**|**Värd**|**TXT Value**|**TTL**|
|TXT (Text)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.           |1 timme|
   
   För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. 
    
2. Spara posten när du är klar.
    
3. Använd något av följande [SPF-verifieringsverktyg](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) för att verifiera SPF-posten
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
Redigera den befintliga SPF-posten eller skapa en ny TXT-post för SPF på DNS-värdens webbplats.
  
> [!IMPORTANT]
> SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot. För att skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Office 365. Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din domän i Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Därefter läser du [Använda DMARC för att validera e-post i Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. I rutorna för den nya posten skriver du, eller kopierar och klistrar in, den uppsättning värden nedan som gäller för din situation.
    
|||||
|:-----|:-----|:-----|:-----|
|**Posttyp**|**Värd**|**TXT Value**|**TTL**|
|TXT (Text)|@|v=spf1 include:spf.protection.partner.outlook.cn -all> [!NOTE]> Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.           |1 timme|
   
   För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. 
    
2. Spara posten när du är klar.
    
3. Använd något av följande [SPF-verifieringsverktyg](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) för att verifiera SPF-posten
    
::: moniker-end

## <a name="add-two-srv-records"></a>Lägga till två SRV-poster
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

På DNS-värdens webbplats skapar du två nya SRV-poster, vanligtvis en i taget. Det innebär att när du har lagt till den första SRV-posten på webbplatsen väljer du att skapa ytterligare en SRV-post.
  
1. I rutorna för varje ny post skriver du in eller kopierar och klistrar in följande värden. **(Information om hur du skapar SRV-poster när din DNS-värd inte har alla dessa separata fält finns i anteckningarna nedan.)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Namn** <br/> |**Mål** <br/> |**Protokoll** <br/> |**Tjänst** <br/> |**Prioritet** <br/> |**Vikt** <br/> |**Port** <br/> |**TTL** <br/> |
|SRV (Service)  <br/> |@  <br/> (Du kan också lämna fältet tomt om @ inte är tillåtet)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 timme  <br/> |
|SRV (Service)  <br/> |@  <br/> (Du kan också lämna fältet tomt om @ inte är tillåtet)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 timme  <br/> |
   
  > [!NOTE]
  >  För **Namn**: Om din DNS-värd inte tillåter att du ställer in detta till **@** lämnar du det tomt. Använd den här metoden *bara* när din DNS-värd har separata fält för värdena Tjänst och Protokoll. Se annars anteckningarna om Tjänst och Protokoll nedan. 

>  För **Tjänst** och **Protokoll**: Om DNS-värden inte tillhandahåller dessa fält för SRV-poster måste du ange värdena för **Tjänst** och **Protokoll** som postens **Namn**-värde. (Obs! Beroende på DNS-värd kan fältet **Namn** heta något annat, t.ex. **Värd**, **Värdnamn** eller **Underdomän**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng och separerar värdena med en punkt.  Till exempel: **Namn**: _sip._tls 

>  För **Prioritet**, **Vikt** och **Port**: Om din DNS-värd inte tillhandahåller dessa fält för SRV-poster måste du ange dem som postens **Mål**-värde. (Obs! Beroende på DNS-värd kan fältet **Mål** heta något annat, t.ex. **Innehåll**, **IP-adress** eller **Målvärd**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng och separerar värdena med blanksteg och avslutar med en punkt. Värdena måste tas med i följande ordning: Prioritet, Vikt, Port, Mål. Till exempel: **Mål**: 100 1 443 sipdir.online.lync.com. 

>  Variant för **Prioritet**, **Vikt** och **Port**: En del DNS-värdar tillhandahåller vissa, men inte alla, obligatoriska fält separat. För de här DNS-värdwebbplatserna anger du de värden som inte visas separat som en kombinerad sträng, i ordning, för postens **Mål**-värde. (Obs! Beroende på DNS-värd kan fältet **Mål** heta något annat, t.ex. **Innehåll**, **IP-adress** eller **Målvärd**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng för de fält som inte visas individuellt, och separerar värdena med blanksteg. Värdena måste tas med *i ordning*, och de värden som har separata fält tillgängliga utelämnas: Prioritet, Vikt, Port, Mål. När det till exempel finns ett separat fält för Prioritet, kopplar du bara samman värdena för Vikt, Port och Mål: **Mål**: 1 443 sipdir.online.lync.com 

> För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. 
  
2. Spara posterna när du är klar.
    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-germany"

På DNS-värdens webbplats skapar du två nya SRV-poster, vanligtvis en i taget. Det innebär att när du har lagt till den första SRV-posten på webbplatsen väljer du att skapa ytterligare en SRV-post.
  
1. I rutorna för varje ny post skriver du in eller kopierar och klistrar in följande värden. **(Information om hur du skapar SRV-poster när din DNS-värd inte har alla dessa separata fält finns i anteckningarna nedan.)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Namn** <br/> |**Mål** <br/> |**Protokoll** <br/> |**Tjänst** <br/> |**Prioritet** <br/> |**Vikt** <br/> |**Port** <br/> |**TTL** <br/> |
|SRV (Service)  <br/> |@  <br/> (Du kan också lämna fältet tomt om @ inte är tillåtet)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 timme  <br/> |
|SRV (Service)  <br/> |@  <br/> (Du kan också lämna fältet tomt om @ inte är tillåtet)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 timme  <br/> |
   
 > [!NOTE]
 >  För **Namn**: Om din DNS-värd inte tillåter att du ställer in detta till **@** lämnar du det tomt. Använd den här metoden *bara* när din DNS-värd har separata fält för värdena Tjänst och Protokoll. Se annars anteckningarna om Tjänst och Protokoll nedan. 

>  För **Tjänst** och **Protokoll**: Om DNS-värden inte tillhandahåller dessa fält för SRV-poster måste du ange värdena för **Tjänst** och **Protokoll** som postens **Namn**-värde. (Obs! Beroende på DNS-värd kan fältet **Namn** heta något annat, t.ex. **Värd**, **Värdnamn** eller **Underdomän**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng och separerar värdena med en punkt. >  Till exempel: **Namn**: _sip._tls 

>  För **Prioritet**, **Vikt** och **Port**: Om din DNS-värd inte tillhandahåller dessa fält för SRV-poster måste du ange dem som postens **Mål**-värde. (Obs! Beroende på DNS-värd kan fältet **Mål** heta något annat, t.ex. **Innehåll**, **IP-adress** eller **Målvärd**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng och separerar värdena med blanksteg och avslutar med en punkt. Värdena måste tas med i följande ordning: Prioritet, Vikt, Port, Mål. >  Till exempel: **Mål**: 100 1 443 sipdir.online.lync.de. 

>  Variant för **Prioritet**, **Vikt** och **Port**: En del DNS-värdar tillhandahåller vissa, men inte alla, obligatoriska fält separat. För de här DNS-värdwebbplatserna anger du de värden som inte visas separat som en kombinerad sträng, i ordning, för postens **Mål**-värde. (Obs! Beroende på DNS-värd kan fältet **Mål** heta något annat, t.ex. **Innehåll**, **IP-adress** eller **Målvärd**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng för de fält som inte visas individuellt, och separerar värdena med blanksteg. Värdena måste tas med *i ordning*, och de värden som har separata fält tillgängliga utelämnas: Prioritet, Vikt, Port, Mål. >  När det till exempel finns ett separat fält för Prioritet, kopplar du bara samman värdena för Vikt, Port och Mål: **Mål**: 1 443 sipdir.online.lync.de 

>  För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. 
  
2. Spara posterna när du är klar.
    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-21vianet"

På DNS-värdens webbplats skapar du två nya SRV-poster, vanligtvis en i taget. Det innebär att när du har lagt till den första SRV-posten på webbplatsen väljer du att skapa ytterligare en SRV-post.
  
1. I rutorna för varje ny post skriver du in eller kopierar och klistrar in följande värden. **(Information om hur du skapar SRV-poster när din DNS-värd inte har alla dessa separata fält finns i anteckningarna nedan.)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Posttyp** <br/> |**Namn** <br/> |**Mål** <br/> |**Protokoll** <br/> |**Tjänst** <br/> |**Prioritet** <br/> |**Vikt** <br/> |**Port** <br/> |**TTL** <br/> |
|SRV (Service)  <br/> |@  <br/> (Du kan också lämna fältet tomt om @ inte är tillåtet)  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 timme  <br/> |
|SRV (Service)  <br/> |@  <br/> (Du kan också lämna fältet tomt om @ inte är tillåtet)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 timme  <br/> |
   
 > [!NOTE]
 >  För **Namn**: Om din DNS-värd inte tillåter att du ställer in detta till **@** lämnar du det tomt. Använd den här metoden *bara* när din DNS-värd har separata fält för värdena Tjänst och Protokoll. Se annars anteckningarna om Tjänst och Protokoll nedan. 

>  För **Tjänst** och **Protokoll**: Om DNS-värden inte tillhandahåller dessa fält för SRV-poster måste du ange värdena för **Tjänst** och **Protokoll** som postens **Namn**-värde. (Obs! Beroende på DNS-värd kan fältet **Namn** heta något annat, t.ex. **Värd**, **Värdnamn** eller **Underdomän**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng och separerar värdena med en punkt. >  Till exempel: **Namn**: _sip._tls 

>  För **Prioritet**, **Vikt** och **Port**: Om din DNS-värd inte tillhandahåller dessa fält för SRV-poster måste du ange dem som postens **Mål**-värde. (Obs! Beroende på DNS-värd kan fältet **Mål** heta något annat, t.ex. **Innehåll**, **IP-adress** eller **Målvärd**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng och separerar värdena med blanksteg och avslutar med en punkt. Värdena måste tas med i följande ordning: Prioritet, Vikt, Port, Mål. >  Till exempel: **Mål**: 100 1 443 sipdir.online.partner.lync.cn. 

>  Variant för **Prioritet**, **Vikt** och **Port**: En del DNS-värdar tillhandahåller vissa, men inte alla, obligatoriska fält separat. För de här DNS-värdwebbplatserna anger du de värden som inte visas separat som en kombinerad sträng, i ordning, för postens **Mål**-värde. (Obs! Beroende på DNS-värd kan fältet **Mål** heta något annat, t.ex. **Innehåll**, **IP-adress** eller **Målvärd**.) För att konfigurera det kombinerade värdet skapar du en enskild sträng för de fält som inte visas individuellt, och separerar värdena med blanksteg. Värdena måste tas med *i ordning*, och de värden som har separata fält tillgängliga utelämnas: Prioritet, Vikt, Port, Mål. >  När det till exempel finns ett separat fält för Prioritet, kopplar du bara samman värdena för Vikt, Port och Mål: **Mål**: 1 443 sipdir.online.partner.lync.cn 

>  För **TTL**: Ställ in det här värdet på **1 timme** eller till motsvarande minuter (**60**), sekunder (**3600**) osv. 
  
2. Spara posterna när du är klar.
    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>Mer information om att uppdatera DNS-poster
<a name="BKMK_MoreAbout"> </a>

 **Om du vet hur du ska uppdatera DNS-poster hos domänens DNS-värd** använder du Office 365 DNS-värden för att redigera poster hos domänens DNS-värd, till exempel för att konfigurera en MX-post eller SPF-post. Hitta de värden som ska användas genom att [följa de här anvisningarna](../get-help-with-domains/information-for-dns-records.md) eller visa dem i domänens konfigurationsguide när du går igenom den.
  
 **Om du behöver hjälp med att ta reda på hur du lägger till de DNS-poster som krävs** läser du [Konfigurera din domän (värdspecifika anvisningar)](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide), börja med att [samla in den information du behöver för att skapa DNS-poster i Office 365](../get-help-with-domains/information-for-dns-records.md). Använd sedan de allmänna anvisningarna i det här avsnittet för att konfigurera din domäns DNS-poster så att du kan använda din domän med Office 365-tjänster, t.ex. e-post.
  
 **Om du inte har en webbplats som du använder med din egen domän** kan du ställa in Office 365 till att konfigurera och hantera DNS-posterna för domänen istället för att göra alla inställningar själv. Läs mer om de [två alternativen för att konfigurera och hantera DNS-poster för en egen domän](https://support.office.com/article/5980474a-097f-4f21-a864-21245314957f.aspx) i Office 365. 
  

