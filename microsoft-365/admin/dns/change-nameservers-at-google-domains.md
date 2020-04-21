---
title: Ändra namnservrar för att konfigurera Microsoft med Google Domäner
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
- BCS160
- MET150
- MOE150
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Lär dig hur du kan konfigurera Microsoft för att hantera DNS-posterna för din anpassade domän på Google Domains.
ms.openlocfilehash: ac2f98a6ff783917d88a2bd8d28e8242e0ba41a8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629905"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>Ändra namnservrar för att konfigurera Microsoft med Google Domäner

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Följ dessa instruktioner om du vill att Microsoft ska hantera dina DNS-poster åt dig. (Om du vill kan du [hantera alla DNS-poster på Google Domains](create-dns-records-at-google-domains.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering

Innan du använder domänen med Microsoft måste vi se till att du äger den. Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
>  Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. För att komma igång, gå till din domänsida på Google Domains via [denna länk](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:
    
1. Välj **Logga in**.
    
2. Ange dina inloggningsuppgifter och välj **logga in igen**.
    
2. På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera. 
    
3. Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type (typ)** <br/> |**TTL** <br/> |**Data** <br/> |
|@  <br/> |TXT  <br/> |1H (1H)  <br/> |MS=ms *XXXXXXXX* <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. Välj **Lägg till**.
    
5. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.
  
När Microsoft hittar rätt TXT-post verifieras domänen.
  
1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Microsofts administrationscenter.</a>

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du har problem med e-postflödet eller andra problem när du har lagt till DNS-poster läser du [Hitta och åtgärda problem när du har lagt till domänen eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)

Om du vill slutföra inrättandet av domänen med Microsoft ändrar du domänens NS-poster på domänregistraren så att de pekar på Microsofts primära och sekundära namnservrar. Detta ställer in Microsoft för att uppdatera domänens DNS-poster åt dig. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.
  
> [!CAUTION]
> När du ändrar domänens NS-poster så att de pekar på Microsofts namnservrar påverkas alla tjänster som för närvarande är associerade med domänen. Till exempel alla e-postmeddelanden som skickas till din domän (t.ex. *rob@ your_domain.*  com) börjar komma till Microsoft när du har gjort den här ändringen. 
  
> [!IMPORTANT]
> Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. > När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra: 
  
1. Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:
    
1. Välj **Logga in**.
    
2. Ange dina inloggningsuppgifter och välj sedan **logga in**igen .
    
2. På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera. 
    
3. Välj **Use custom name servers** (använd anpassade namnservrar) i området **Name servers** (namnservrar) på sidan **Domains** (domäner).
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:
    
  - Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).
    
  - Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Om INGA namnservrar visas

1. Lägg till den första namnservern.
    
    I rutan **NAME SERVER** (namnserver) i avsnittet **Name servers** (namnservrar) skriver du in, eller kopierar och klistrar in, det första värdet från tabellen nedan. 
    
|||
|:-----|:-----|
|**Första namnservern** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Andra namnservern** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Tredje namnservern** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fjärde namnservern** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domäner-BP-Redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. Markera kontrollen **+ (lägg till)** om du vill skapa en tom rad. 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. Lägg till de andra tre namnserverposterna.
    
    Skapa en post i avsnittet **Använd anpassade namnservrar** med hjälp av värdena från nästa rad i tabellen och välj sedan kontrollen **+ (lägg till)** för att lägga till en annan rad. 
    
    Upprepa proceduren tills du har skapat alla fyra namnserverposterna.
    
4. Välj **Spara**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Om det redan FINNS namnservrar listade

1. Om det finns några andra namnservrar i listan väljer du **Redigera**.
    
    > [!CAUTION]
    > Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna. (Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.) 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. Ta bort var och en genom att markera den och sedan trycka på **Del**-tangenten. 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. På **NAME SERVER**-raderna i avsnittet **Name servers** (namnservrar) skriver du in, eller kopierar och klistrar in, värdena från tabellen nedan. 
    
|||
|:-----|:-----|
|**Första namnservern** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Andra namnservern** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Tredje namnservern** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fjärde namnservern** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domäner-BP-Redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. Markera kontrollen **+(add)** om du vill skapa en tom rad. 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. Lägg till de andra två namnserverposterna.
    
    Skapa en post i avsnittet **Använd anpassade namnservrar** med hjälp av värdena från nästa rad i tabellen och välj sedan kontrollen **+(add)** för att lägga till en annan rad. 
    
    Upprepa proceduren tills du har skapat alla fyra namnserverposterna.
    
6. Välj **Spara**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän. 
  
