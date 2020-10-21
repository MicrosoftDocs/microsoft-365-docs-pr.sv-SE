---
title: Ändra namnservrar för att konfigurera Microsoft med NameCheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Lär dig hur du konfigurerar din Microsoft Custom Domain med NameCheap om du vill att Microsoft ska hantera dina DNS-poster. '
ms.openlocfilehash: e305abb7768b286dbd24336c1dab39d919f9a0ac
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646457"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a>Ändra namnservrar för att konfigurera Microsoft med NameCheap

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.
  
Följ de här anvisningarna om du vill att Microsoft ska hantera dina DNS-poster åt dig. (Om du vill kan du [hantera alla dina Microsoft DNS-poster på NameCheap](create-dns-records-at-namecheap.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering

1. Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. Välj **domän lista** i list rutan under **konto** **på Start sidan.** 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Välj **Advanced DNS**.
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. Välj **Add New Record**i avsnittet **Host Records** .
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. Välj **TXT Record** i listrutan **Type**.
    
    > [!NOTE]
    > List rutan **typ** visas automatiskt när du väljer **Lägg till ny post**.
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    (Välj **TTL** -värdet i list rutan.) 
    
|**Typ**|**Host**|**Värde**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |30 min  <br/> |
   
   ![NameCheap-BP-verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. Markera kontrollen **Spara ändringar** (bock markering). 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)

För att slutföra konfigurationen av din domän med Microsoft ändrar du domänens NS-poster hos domän registratorn så att de pekar på Microsofts primära och sekundära namnservrar. Detta konfigurerar Microsoft för att uppdatera domänens DNS-poster åt dig. Vi lägger till alla poster så att e-post, Skype för företag - Online och den offentliga webbplatsen fungerar med domänen så att du kan börja.
  
> [!CAUTION]
> När du ändrar domänens NS-poster så att de pekar på Microsoft Name Server påverkas alla tjänster som är associerade till din domän. Till exempel kommer all e-post som skickas till din domän (som rob@ *your_domain*  . com) att komma till Microsoft när du har gjort den här ändringen. 
  
> [!IMPORTANT]
>  När du har utfört stegen i det här avsnittet är de  *enda*  namnservrarna som bör finnas i listan dessa fyra: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  Följande procedur visar hur du tar bort andra, oönskade namnservrar från listan, och hur du lägger till  *korrekta*  namnservrar om de inte redan finns i listan. 
  
1. Börja med att gå till domänsidan på Namecheap genom att klicka på [den här länken](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Du uppmanas att logga in och fortsätta.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. Välj **domän lista** i list rutan under **konto** **på Start sidan.** 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. Leta reda på namnet på den domän som du vill redigera på sidan **Domain List** och välj sedan **Manage**.
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Välj **domän**.
    
    ![NameCheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. Leta reda på avsnittet **namnservrar** och välj sedan **anpassad** från List rutan **NameCheap default** . 
    
    ![NameCheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. Beroende på om det redan finns namnservrar på sidan som visas nu går du vidare till något av de två följande procedurerna.
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Om INGA namnservrar visas
<a name="BKMK_ProcedureWithOUT"> </a>

1. Välj **Lägg till namnserver** två gånger för att lägga till två nya rader.
    
    ![NameCheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. Skriv in, eller kopiera och klistra in, värdena från följande tabell i rutorna **namnserver** .
    
|||
|:-----|:-----|
|**Namnserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Namnserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Namnserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Namnserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![NameCheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. Markera kontrollen **Spara** (bock markering). 
    
    ![NameCheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Om det redan FINNS namnservrar listade

> [!CAUTION]
> Följ de här anvisningarna  *endast*  om det finns andra namnservrar utöver de fyra  *korrekta*  namnservrarna. (Ta alltså  *endast*  bort eventuella namnservrar som  *inte*  heter **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** eller **ns4.bdm.microsoftonline.com**.) 
  
1. Om det finns andra namnservrar i **namnserver** rutor tar du bort var och en genom att markera den och sedan trycka på **Delete** -tangenten på tangent bordet. 
    
    ![NameCheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. Välj **Lägg till namnserver** två gånger för att lägga till två nya rader. 
    
    ![NameCheap-BP-Redelegate-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. Skriv in, eller kopiera och klistra in, värdena från följande tabell i rutorna **namnserver** .
 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Namnserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Namnserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![NameCheap-BP-Redelegate-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. Markera kontrollen **Spara** (bock markering). 
    
    ![NameCheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän.
