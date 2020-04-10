---
title: Ändra namnservrar för att konfigurera Office 365 med Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Läs om hur du kan konfigurera Office 365 för att hantera dina DNS-poster på Bluehost. '
ms.openlocfilehash: dbd06791df2e7f8e6ca085b82dc880e9626c065c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212347"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a>Ändra namnservrar för att konfigurera Office 365 med Bluehost

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Följ instruktionerna nedan om du vill att Office 365-DNS-posterna ska hanteras i Office 365. (Om du föredrar det kan du [hantera alla DNS-poster för Office 365 hos Bluehost](create-dns-records-at-bluehost.md).)
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering

Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm). Du uppmanas att logga in först.
    
2. Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen. 
    
    (Du kan behöva rulla nedåt.) 
    
3. Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området **domain_name** .
    
4. Gå till sidan **DNS Zone Editor** och området Add DNS Record. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. Välj **lägg till post**.
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
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
> Om du ändrar domänens NS-poster så att de pekar på Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen. Till exempel kommer all e-post som skickas till din domän (till exempel rob@ *your_domain*  .com) till Office 365 när du har gjort den här ändringen. 
  
> [!IMPORTANT]
>  Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. >  När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm). Du uppmanas att logga in först.
    
2. Markera kryssrutan för domänen i **området domain_name** på **domänsidan** och välj sedan **namnservrar**.
    
    ![Bluehost-BP - Omdelegera-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. Välj **Använd anpassade namnservrar**i området **domain_name** .
    
    ![Bluehost-BP - Omdelegera-1-2](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. Beroende på om det redan finns namnservrar listade på sidan som visas nu, fortsätter du till en av följande procedurer:
    
  - Om **INGA** namnservrar visas [Om INGA namnservrar visas](#if-there-are-no-nameservers-already-listed).
    
  - Om det redan **FINNS** namnservrar listade [Om det redan FINNS namnservrar listade](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Om INGA namnservrar visas

1. I avsnittet **Use Custom Nameservers** skriver eller kopierar och klistrar du in värdena från följande tabell. 
    
|||
|:-----|:-----|
|**Första tomma raden** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Andra tomma raden** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. Välj **Lägg till rad**.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. I avsnittet **Use Custom Nameservers** skriver eller kopierar och klistrar du in värdena från den första raden i följande tabell på den nya, tomma raden. 
    
|||
|:-----|:-----|
|**Tredje tomma raden** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fjärde tomma raden** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. Om du vill lägga till den fjärde namnserverposten väljer du **Lägg till rad** igen och skapar en post med värdena från den sista raden i tabellen ovan. 
    
5. Välj **spara namnserverinställningar**.
    
    ![Bluehost-BP - Omdelegera-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Om det redan FINNS namnservrar listade

> [!CAUTION]
> Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna. (Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.) 
  
1. Om det finns andra namnservrar tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten. 
    
    ![Bluehost-BP - Omdelegera-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. I avsnittet **Use Custom Nameservers** skriver eller kopierar och klistrar du in värdena från följande tabell. 
    
|||
|:-----|:-----|
|**Första tomma raden** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Andra tomma raden** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. Välj **Lägg till rad**.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. I avsnittet **Use Custom Nameservers** skriver eller kopierar och klistrar du in värdena från den första raden i följande tabell på den nya, tomma raden. 
    
|||
|:-----|:-----|
|**Tredje tomma raden** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Fjärde tomma raden** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. Om du vill lägga till den fjärde namnserverposten väljer du **Lägg till rad** igen och skapar en post med värdena från den sista raden i tabellen ovan. 
    
6. Välj **spara namnserverinställningar**.
    
    ![Bluehost-BP - Omdelegera-1-4](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
  
