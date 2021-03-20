---
title: Skapa DNS-poster på GoDaddy för Microsoft
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på GoDaddy för Microsoft.
ms.openlocfilehash: d0163447abdc7b9fe5afd4f471f24ee09de40d50
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910252"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a>Skapa DNS-poster på GoDaddy för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.

Om GoDaddy är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.

När du har lagt till dessa poster på GoDaddy är din domän konfigurerad för att fungera med Microsoft-tjänster.

> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.

> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner** väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Välj **TXT (Text)** i listrutan. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.

    |**Record type** |**Värd**|**TXT Value**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (Text)|@|MS=ms *XXXXXXXX*<br>**Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)|1 timme  <br>(Välj ett värde i listrutan.)|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. Välj **Spara**.

6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.

Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.

När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.



4. På sidan **Verify domain** väljer du **Verify**.



> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner** väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Välj **MX (Mail Exchanger)** i listrutan.

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.

    (Välj **TTL-värdet** i listrutan.)

    |**Record type**|**Värd**|**Pekar på**|**Prioritet**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Obs!** Skaffa ditt  *\<domain-key\>*  Microsoft-konto.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml) <br/> |1 timme  <br/> |

6. Välj **Spara**.

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Lägga till CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner** väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. Välj **CNAME (Alias)** i listrutan.

    ![GoDaddy-BP-Configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. Skapa den första CNAME-posten.

    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.

    (Välj **TTL-värdet** i listrutan.)

    |**Record type**|**Värd**|**Pekar på**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 timme  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 timme  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 timme  <br/> |
    |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 timme  <br/> |
    |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 timme  <br/> |



6. Upprepa de här stegen för att lägga till nästa CNAME-post tills du har skapat alla sex CNAME-posterna.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden.

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner** väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Välj **TXT (Text)** i listrutan.

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.

    (Välj **TTL-värdet** i listrutan.)

    |**Record type**|**Värd**|**TXT Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |1 timme  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. Välj **Spara**.


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner** väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Välj **SRV (Service)** (SRV (tjänst)) i listrutan.

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. Skapa den första SRV-posten.

    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.

    (Välj värdena **Record type** **och TTL** i listrutan.)

    |**Record type**|**Namn**|**Mål**|**Protokoll**|**Tjänst**|**Prioritet**|**Vikt**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 timme  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 timme  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. Upprepa **steg 5 för** att skapa den andra SRV-posten.

7. Välj **Spara**.

> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).