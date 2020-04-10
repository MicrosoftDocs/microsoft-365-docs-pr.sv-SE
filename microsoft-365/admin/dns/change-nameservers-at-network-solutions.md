---
title: Ändra namnservrar för att konfigurera Office 365 med Network Solutions
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Lär dig att konfigurera din anpassade Office 365-domän med Network Solutions om du vill att Office 365 ska hantera dina DNS-poster. '
ms.openlocfilehash: df80cc925fab965b73873916dff7fc4dea74a661
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211889"
---
# <a name="change-nameservers-to-set-up-office-365-with-network-solutions"></a>Ändra namnservrar för att konfigurera Office 365 med Network Solutions

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.
  
Följ instruktionerna nedan om du vill att Office 365-DNS-posterna ska hanteras i Office 365. (Om du föredrar det kan du [hantera alla DNS-poster för Office 365 hos Network Solutions](create-dns-records-at-network-solutions.md).)
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a>Lägga till en TXT-post på Network Solutions för att verifiera att det är din domän

Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
Följ stegen nedan eller [titta på videon (börja vid 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.
    
    > [!IMPORTANT]
    > Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** .
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Markera kryssrutan bredvid namnet på den domän som du uppdaterar.
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Välj **Redigera DNS**.
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Välj **Hantera avancerade DNS-poster**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Hantera avancerade DNS-poster](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Redigera TXT-poster**.
    
    ![Välj Redigera TXT-poster](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena i följande tabell.
    
|**Host**|**TTL**|**Text**|
|:-----|:-----|:-----|
|@  <br/> (Värdet ändras till **@ (None)** när du sparar posten.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs:** Detta är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Skriva eller klistra in värden i rutorna för den nya posten](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Välj **Fortsätt**.
    
    ![Välj Fortsätt](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Välj **Spara ändringar**.
    
    ![Välj Spara ändringar](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)

Om du vill slutföra konfigurationen av domänen med Office 365 kan du ändra domänens NS-poster hos domänregistratorn så att de pekar på de primära och sekundära namnservrarna i Office 365. Då ställs Office 365 in så att domänens DNS-poster uppdateras. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.
  
> [!CAUTION]
> Om du ändrar domänens NS-poster så att de pekar på Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen. Till exempel kommer all e-post som skickas till din domän (till exempel rob@ *your_domain*  .com) till Office 365 när du har gjort den här ändringen.
  
Vill du ändra namnserverposterna så att du kan konfigurera din domän i Office 365? Följ stegen nedan eller [titta på videon (börja vid 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!IMPORTANT]
>  När du har slutfört stegen i det här avsnittet är de *enda* namnservrarna som ska visas dessa fyra: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**och **ns4.bdm.microsoftonline.com**. Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till  *korrekta*  namnservrar om de inte redan finns i listan. 
  
1. Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.
    
    > [!IMPORTANT]
    > Innan du väljer **knappen Logga in** väljer du först Hantera mina **domännamn** i **listrutan Logga in till:** . 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Markera kryssrutan bredvid namnet på den domän som du uppdaterar.
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Välj **Redigera DNS**.
    
    ![Välj Redigera DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Välj **Flytta DNS**.
    
    ![NätverkLösningarBP-Redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:
    
  - Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).
    
  - Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Om INGA namnservrar visas

1. Välj **Lägg till fler namnservrar**i avsnittet Ange **domännamnsservrar** på sidan **Domäner** .
    
    ![NätverkLösningarBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. På sidan **Domain Names** skriver eller kopierar och klistrar du in namnservervärdena från följande tabell. 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NätverkLösningarBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. Välj **Flytta DNS**.
    
    ![NätverkLösningarBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. Välj **Spara ändringar**.
    
    ![NätverkLösningarBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Om det redan FINNS namnservrar listade

> [!CAUTION]
> Följ de här anvisningarna  *endast*  om det finns andra namnservrar utöver de fyra  *korrekta*  namnservrarna. (Ta alltså  *endast*  bort eventuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** eller **ns4.bdm.microsoftonline.com**.)
  
1. Om det finns andra namnservrar tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten.
    
    ![NätverkLösningar-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. Välj **Lägg till fler namnservrar**.
    
    ![NätverkLösningarBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. På sidan **Domain Names** skriver eller kopierar och klistrar du in namnservervärdena från följande tabell.
 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NätverkLösningarBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. Välj **Flytta DNS**.
    
    ![NätverkLösningarBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. Välj **Spara ändringar.**
    
    ![NätverkLösningarBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän.
