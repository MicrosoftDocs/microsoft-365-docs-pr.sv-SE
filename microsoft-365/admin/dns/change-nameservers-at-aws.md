---
title: Ändra namnservrar för att konfigurera Microsoft med Amazon Web Services (AWS)
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Lär dig hur du kan konfigurera Microsoft för att hantera dina DNS-poster på Amazon Web Services (AWS). '
ms.openlocfilehash: 6efe06400652783ffbc6732b5c6327067c5c484c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400683"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>Ändra namnservrar för att konfigurera Microsoft med Amazon Web Services (AWS)

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Följ dessa instruktioner om du vill att Microsoft ska hantera dina DNS-poster åt dig. (Om du vill kan du [hantera alla dina Microsoft DNS-poster på AWS](create-dns-records-at-aws.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.
    
2. På sidan **Resurser** väljer du **Värdzoner**.
    
3. Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.** 
    
4. Välj **Skapa postuppsättning**.
    
5. I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten. 
    
    (Välj värdena för **Type** och **Routing Policy** i listrutorna.) 
    
    > [!TIP]
    > Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type (Typ)** <br/> |**Alias** <br/> |**TTL (sekunder)** <br/> |**Värde** <br/> |**Routing Policy (Routningsprincip)** <br/> |
|(Lämna det här fältet tomt)  <br/> |TXT - text  <br/> |Nej  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Enkelt <br/> |
   
6. Välj **Skapa**.
    
7. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)

Om du vill slutföra inrättandet av domänen med Microsoft ändrar du domänens NS-poster på domänregistraren så att de pekar på Microsofts primära och sekundära namnservrar. Detta ställer in Microsoft för att uppdatera domänens DNS-poster åt dig. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.
  
> [!CAUTION]
> När du ändrar domänens NS-poster så att de pekar på Microsofts namnservrar påverkas alla tjänster som för närvarande är associerade med domänen. Till exempel börjar all e-post som skickas till din domän (t.ex. *rob@ your_domain* .com) komma till Microsoft när du har gjort den här ändringen. 
  
> [!IMPORTANT]
>  Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. >  När du har utfört stegen i det här avsnittet är de enda namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.
    
2. På sidan **Resurser** väljer du **Värdzoner**.
    
3. Välj namnet på den domän som du vill redigera i kolumnen **Domännamn** på sidan **Värdzoner.** 
    
4. Välj undergruppen **Nameserver**. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. I **NS - Name server**-undergruppen, i **Value**, tar du bort alla namnservrar genom att markera dem alla och sedan trycka på **Delete** på tangentbordet. 
    
    > [!CAUTION]
    > Följ bara dessa steg om du har andra befintliga namnservrar än de fyra korrekta namnservrarna. (Det vill an, ta bara bort alla aktuella namnservrar som *inte* namnges **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**eller **ns4.bdm.microsoftonline.com**.) 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. I **området TTL (Sekunder):** väljer du **1h** (1 timme). 
    
    ![Välj 1H i en timme](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. Fortfarande i **NS - Name server**-undergruppen och i värderutan **Value**: Skriv eller kopiera och klistra in värdet för första raden - **First line** - från tabellen nedan. Tryck på **Retur** på tangentbordet och skriv eller kopiera och klistra in värdet för nästa **rad**. 
    
    > [!IMPORTANT]
    > Varje namnservervärde  *måste*  stå på en egen rad i värderutan: **Value**. Se bildförklaringen nedan. 
  
|||
|:-----|:-----|
|**Första raden (First line)** <br/> |ns1.bdm.microsoftonline.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
|**Andra raden (Second line)** <br/> |ns2.bdm.microsoftonline.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
|**Tredje raden (Third line)** <br/> |ns3.bdm.microsoftonline.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
|**Fjärde raden (Fourth line)** <br/> |ns4.bdm.microsoftonline.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
   
   ![Skriva eller klistra in värdet för första raden i rutan Värde](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. Välj **Spara postuppsättning**.
    
    ![Välj Spara postuppsättning](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän. 
