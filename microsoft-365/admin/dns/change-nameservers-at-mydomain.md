---
title: Ändra namnservrar för att konfigurera Office 365 med MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Lär dig hur du kan konfigurera Office 365 för att hantera DNS-posterna för din anpassade domän på MyDomain.
ms.openlocfilehash: f88f0528caf2229441fd3e5364b53864b923099f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212051"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a>Ändra namnservrar för att konfigurera Office 365 med MyDomain

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.
  
Följ instruktionerna nedan om du vill att Office 365-DNS-posterna ska hanteras i Office 365. (Om du föredrar det kan du [ hantera alla DNS-poster för Office 365 hos MyDomain ](create-dns-records-at-mydomain.md).)
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering

Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.
    
2. Välj **Domain Central** under **My Favorites**.
    
3. Under **Domain** väljer du namnet på den domän som du vill redigera.
    
4. På raden **Overview** väljer du **DNS**.
    
5. I listrutan **Modify** väljer du **TXT/SPF Record**.
    
6. Under **Content**, i rutan för den nya posten, skriver du in, eller kopierar och klistrar in, värdet från följande tabell.
    
||
|:-----|
|**Content** <br/> |
|MS=ms *XXXXXXXX*  <br/> **Obs:** Detta är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Välj **Lägg till**.
    
8. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)

Om du vill slutföra konfigurationen av domänen med Office 365 kan du ändra domänens NS-poster hos domänregistratorn så att de pekar på de primära och sekundära namnservrarna i Office 365. Då ställs Office 365 in så att domänens DNS-poster uppdateras. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.
  
> [!CAUTION]
> Om du ändrar domänens NS-poster så att de pekar på Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen. Till exempel alla e-postmeddelanden som skickas till din domän (t.ex. *rob@ your_domain.* com) börjar komma till Office 365 när du har gjort den här ändringen. 
  
> [!IMPORTANT]
> Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan.<br/> När du har slutfört stegen i det här avsnittet är de enda namnservrarna som ska visas dessa fyra:
  
1. Kom igång genom att gå till domänsidan på MyDomain genom att klicka på [den här länken](https://www.mydomain.com/controlpanel). Du uppmanas att logga in först.
    
2. Välj **Domain Central** under **My Favorites**.
    
3. Under **Domain** väljer du namnet på den domän som du vill redigera.
    
4. Välj **Namnservrar**på raden **Översikt** .
    
    ![MyDomain-BP-Redelegate-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. Välj **Use different name servers** i avsnittet **Update Name Servers**.
    
    ![MyDomain-BP-Redelegate-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. Beroende på om det redan finns namnservrar listade på sidan som visas nu fortsätter du till någon av följande två procedurer.
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>Om rätt namnservrar REDAN LISTAS

- Om rätt namnservrar redan listas, kan du hoppa över detta steg.
    
    ![MyDomain-BP-Redelegate-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>Om rätt namnservrar INTE LISTAS

> [!CAUTION]
> Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna. (Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.) 
  
1. Ta bort befintliga namnservrar genom att markera varje post i fältet **Namnserver:** och sedan tryck på **Delete** på tangentbordet. 
    
    ![MyDomain-BP-Redelegate-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. Välj **Lägg till fler** två gånger om du vill lägga till två nya namnserverrader. 
    
    ![MyDomain-BP-Redelegate-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. I rutorna för posterna skriver eller klipper och klistrar du in namnservervärdena från följande tabell.
    
|||
|:-----|:-----|
|**Namnserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Namnserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Namnserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Namnserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![MyDomain-BP-Redelegate-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. Välj **Spara**.
    
    ![MyDomain-BP-Redelegate-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
