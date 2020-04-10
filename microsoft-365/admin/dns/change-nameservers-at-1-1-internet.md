---
title: Ändra namnservrar för att konfigurera Office 365 med 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Lär dig hur du kan konfigurera Office 365 som drivs av 21Vianet för att hantera dina DNS-poster, när 1&1 Internet är DNS-värd.
ms.openlocfilehash: bda6a19ba7bfca20bc1764187f429e13900d8460
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212371"
---
# <a name="change-nameservers-to-set-up-office-365-with-11-ionos"></a>Ändra namnservrar för att konfigurera Office 365 med 1&1 IONOS

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Följ instruktionerna nedan om du vill att Office 365-DNS-posterna ska hanteras i Office 365. (Om du vill kan du [hantera alla dina Office 365 DNS-poster med 1&1 IONOS](create-dns-records-at-1-1-internet.md).) 
  

    
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering


Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
Följ stegen nedan eller [titta på videon (börja vid 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. För att komma igång, gå till din domänsida på 1&1 IONOS via [denna länk](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). Du uppmanas att logga in. 
    
2. Under **MY DOMAINS** väljer du **Manage Domains**.
    
3. Leta reda på den domän som du vill uppdatera på sidan **Domain Center.** Välj sedan **kontrollen Panel** **(v)** för den domänen.
    
4. Välj **Redigera DNS-inställningar**i området **Domäninställningar** .
    
5. I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.
    
    (Du kan behöva rulla nedåt.) 
    
6. Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
||||
|:-----|:-----|:-----|
|**Type** <br/> |**Prefix** <br/> |**Name Value** <br/> |
|TXT  <br/> |(Lämna det här fältet tomt.)  <br/> |MS=ms *XXXXXXXX* <br/> **Obs:** Detta är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. Välj **Spara**och **spara** sedan igen. 
    
8. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .
    
9. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
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
> När du ändrar domänens NS-post så att den pekar på Office 365-namnservrarna påverkas alla tjänster som nu associeras med din domän. Till exempel börjar all e-post som skickats till din domän (t.ex. niklas@ *din_domän*  .com) komma till Office 365 när du har gjort den här ändringen. 
  
Vill du ändra namnserverposterna så att du kan konfigurera din domän i Office 365? Följ stegen nedan eller [titta på videon (börja vid 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!IMPORTANT]
>  Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. >  När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). Du uppmanas att logga in. 
    
2. Under **MY DOMAINS** väljer du **Manage Domains**.
    
3. Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.
    
4. Välj **Redigera DNS-inställningar**i området **Domäninställningar** .
    
5. I avsnittet **Name Server Settings** väljer du **Other name servers**.
    
    (Du kan behöva rulla nedåt.)
    
6. Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:
    
  - Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).
    
  - Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Om INGA namnservrar visas

1. I rutan **Name server 1** skriver du in, eller kopierar och klistrar in, värdet från följande tabell. 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![Ange ett värde i rutan Namnserver 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. I listrutan **Additional name servers** väljer du **My secondary name servers**.
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. I rutorna **Name server 2, 3 och 4** skriver du in, eller kopierar och klistrar in, värdet från följande tabell. 
    
|||
|:-----|:-----|
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Entering name server values](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. Välj **Spara**.
    
    ![Välja Spara på sidan Inställningar för namnserver](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .
    
    ![Välja Spara i dialogrutan Redigera DNS-inställningar](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Om det redan FINNS namnservrar listade

> [!CAUTION]
> Följ de här anvisningarna  *endast*  om det finns andra namnservrar utöver de fyra  *korrekta*  namnservrarna. (Ta alltså  *endast*  bort eventuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** eller **ns4.bdm.microsoftonline.com**.) 
  
1. Om det förekommer andra namnservrar i **Name server**-rutorna tar du bort var och en genom att markera den och sedan trycka på **Delete**-tangenten. 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. I rutorna **Name server 1, 2, 3 och 4** skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
|||
|:-----|:-----|
|**Name server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name server 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name server 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Ange namnservervärden](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. Välj **Spara**.
    
    ![Välja Spara på sidan Inställningar för namnserver](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .
    
    ![Välja Spara i dialogrutan Redigera DNS-inställningar](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
  


