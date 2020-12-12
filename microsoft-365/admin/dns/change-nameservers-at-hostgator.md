---
title: Ändra namnservrar för att konfigurera Microsoft med Host Gator
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
- BCS160
- MET150
- MOE150
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Lär dig hur du kan konfigurera Microsoft för att hantera DNS-posterna för din anpassade domän på Host gator.
ms.openlocfilehash: 34e7bbe3abc084185f72f4fef004ad891492ef3c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658026"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>Ändra namnservrar för att konfigurera Microsoft 365 med Host Gator

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.
  
Följ de här anvisningarna om du vill att Microsoft ska hantera dina DNS-poster åt dig. (Om du vill kan du [hantera alla dina Microsoft DNS-poster på Host Gator](create-dns-records-at-hostgator.md).)
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Ange att domänen ska peka på värdkontot.

> [!IMPORTANT]
> Du måste utföra den här proceduren innan du utför proceduren i följande avsnitt, **Lägga till en TXT-post för verifiering**.
  
Följ dessa steg för att associera domänen med värdkontona.
  
1. Kom igång genom att gå till kundportalen på Hostgator genom att klicka på [den här länken](https://portal.hostgator.com/domain/manage). Du uppmanas att logga in.
    
    ![Hostgator-BP - Omdelegera-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Välj fliken **domäner** .
    
    ![Hostgator-BP - Omdelegera-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Välj den domän som du vill uppdatera i området **Mina domäner** på sidan **hantera domäner** .
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. På sidan **Domains Overview** i området **Name servers** väljer du **change**.
    
    ![Hostgator-BP - Omdelegera-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Välj det **värd konto** som är kopplat till din domän i list rutan **Välj värd konto** på sidan **namnservrar** för din domän.
    
    ![Hostgator-BP - Omdelegera-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Välj **Save Name servers**.
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering

> [!IMPORTANT]
> Innan du utför den här proceduren måste du först utföra proceduren i det första avsnittet i den här artikeln, [peka domänen på ditt värd konto.](#point-your-domain-to-your-hosting-account).
  
Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.
  
1. Kom igång genom att gå till sidan cPanel på Hostgator Du uppmanas att logga in först.
    
    (Varje konto på Hostgator har tilldelats en unik cPanel-adress. cPanel-adressen bör se ut ungefär så här: https://YourSiteAddress:secure-port-number. E-postmeddelandet du fick från Hostgator vid registreringen anger adressen.)
    
    > [!IMPORTANT]
    > Du måste ha ett konto på Hostgator för att associera en cPanel med domänen. För att komma igång kan du antingen köpa ett värd konto från Host gator eller [ändra domänens namnserver (NS-poster)](#change-your-domains-nameserver-ns-records) så att de pekar på Microsoft. 
  
2. På sidan **kontroll panelen** i området **domäner** väljer du **avancerad DNS Zone Editor**.
    
    (Du kan behöva rulla nedåt.) 
    
3. Gå till sidan **Advanced DNS Zone Editor** och området **Add a Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
|Använd ditt  *domännamn*  . (Till exempel fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |9.1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Välj **Add Record**.
    
5. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)

För att slutföra konfigurationen av din domän med Microsoft ändrar du domänens NS-poster hos domän registratorn så att de pekar på Microsofts primära och sekundära namnservrar. Detta konfigurerar Microsoft för att uppdatera domänens DNS-poster åt dig. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.
  
> [!CAUTION]
> När du ändrar domänens NS-poster så att de pekar på Microsoft Name Server påverkas alla tjänster som är associerade till din domän. Till exempel kommer all e-post som skickas till din domän (som rob@ *your_domain*  . com) att komma till Microsoft när du har gjort den här ändringen.
  
> [!IMPORTANT]
> Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till korrekta namnservrar om de inte redan finns i listan. När du har slutfört stegen i det här avsnittet är de enda namnservrar som ska visas här fyra:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com** och **NS4.bdm.microsoftonline.com**.
  
1. Kom igång genom att gå till kundportalen på Hostgator genom att klicka på [den här länken](https://portal.hostgator.com/domain/manage). Du uppmanas att logga in.
    
    ![Hostgator-BP - Omdelegera-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Välj fliken **domäner** . 
    
    ![Hostgator-BP - Omdelegera-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Välj den domän som du vill uppdatera i området **Mina domäner** på sidan **hantera domäner** . 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Välj **ändra** i området **Name servers** på sidan **Domain Overview** .
    
    ![Hostgator-BP - Omdelegera-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Välj det **värd konto** som är kopplat till din domän i list rutan **Välj värd konto** på sidan **namnservrar** för din domän. 
    
    ![Hostgator-BP - Omdelegera-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Välj **Ange namn** automatiskt.
    
    ![Hostgator-BP - Omdelegera-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **Varning**! Följ de här anvisningarna bara om du har en annan namnservrar än de fyra korrekta namnservrar. (Det är bara att ta bort alla aktuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com** eller **NS4.bdm.microsoftonline.com**.)
  
        Fortfarande på sidan **Name Servers** för din domän tar du bort varje namnserver i listan genom att markera den och sedan trycka på **Delete** på tangentbordet. 
    
   ![Hostgator-BP - Omdelegera-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. I listan med namnservrar skriver du in, eller kopierar och klistrar in, de första två värdena från följande tabell.
    
|||
|:-----|:-----|
|**Name Server 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2:** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Name Server 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Name Server 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Host Gator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Lägg till de andra namnservervärdena.
    
    Välj **(+)** Lägg till och skriv eller kopiera och klistra in värdet från nästa rad i tabellen i rutan för posten. 
    
    Upprepa proceduren tills du har skapat alla fyra namnserverposterna.
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Välj **Save Name servers**.
    
    ![Hostgator-BP - Omdelegera-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.
