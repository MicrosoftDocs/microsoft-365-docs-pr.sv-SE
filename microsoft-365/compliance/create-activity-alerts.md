---
title: Skapa aktivitetsaviseringar
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
ROBOTS: NOINDEX, NOFOLLOW
description: Lägga till och hantera aktivitetsaviseringar i säkerhets- & säkerhets- och efterlevnadscenter så att Microsoft 365 skickar e-postmeddelanden när användare utför specifika aktiviteter
ms.openlocfilehash: 0d5133bd46be6a5a548f2b733bae202f3a611646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162404"
---
# <a name="create-activity-alerts"></a>Skapa aktivitetsaviseringar

Du kan skapa en aktivitetsavisering som skickar ett e-postmeddelande när användare utför specifika aktiviteter i Office 365. Aktivitetsaviseringar påminner om att söka efter händelser i granskningsloggen, förutom att du får ett e-postmeddelande när en händelse för en aktivitet som du har skapat en avisering för inträffar. 
  
 **Varför ska jag använda aktivitetsaviseringar i stället för att söka i granskningsloggen?** Det kan finnas vissa typer av aktivitet eller aktivitet som utförs av specifika användare som du verkligen vill veta om. I stället för att behöva komma ihåg att söka i granskningsloggen efter dessa aktiviteter kan du använda aktivitetsaviseringar för att Microsoft 365 ett e-postmeddelande när användarna utför de aktiviteterna. Du kan till exempel skapa en aktivitetsavisering för att meddela dig när en användare tar bort filer i SharePoint, eller så kan du skapa en avisering för att meddela dig när en användare permanent tar bort meddelanden från postlådan. E-postmeddelandet som skickas till dig innehåller information om vilken aktivitet som utförts och användaren som utförde den.

> [!NOTE]
> Aktivitetsaviseringar är föråldrade. Vi rekommenderar att du börjar använda aviseringsprinciper i säkerhets- och efterlevnadscentret i stället för att skapa nya aktivitetsaviseringar. Aviseringsprinciper ger ytterligare funktioner, till exempel möjligheten att skapa en aviseringsprincip som utlöser en  avisering när en användare utför en angiven aktivitet, och visa aviseringar på sidan Visa aviseringar i säkerhets- och efterlevnadscentret. Mer information finns i [Aviseringsprinciper](alert-policies.md).
  
## <a name="confirm-roles-and-configure-audit-logging"></a>Bekräfta roller och konfigurera granskningsloggning

- Du måste ha tilldelats rollen Organisationskonfiguration i Säkerhets- & säkerhets- och efterlevnadscenter för att hantera aktivitetsaviseringar. Som standard är den här rollen tilldelad rollgrupperna Efterlevnadsadministratör och Organisationshantering. Mer information om hur du lägger till medlemmar i rollgrupper finns i Ge [användare åtkomst till Säkerhets- & Efterlevnadscenter.](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md)
    
- Du (eller någon annan administratör) måste först aktivera granskningsloggning för organisationen innan du kan börja använda aktivitetsaviseringar. Det gör du genom att klicka på **Starta inspelning av användar- och administratörsaktivitet** på **sidan Aktivitetsaviseringar.** (Om du inte ser länken har granskning redan aktiverats för organisationen.) Du kan också aktivera granskning på sidan **Granskningsloggsökning** i Säkerhets- och & (gå till **Sök** \> **granskningsloggsökning**). Du behöver bara göra det här en gång för din organisation.
  
- Du kan skapa aviseringar för samma aktiviteter som du kan söka efter i granskningsloggen. I avsnittet [Mer information](#more-information) finns en lista över vanliga scenarier (och den specifika aktivitet som ska övervakas) som du kan skapa aviseringar för. 
    
- Du kan  använda sidan Aktivitetsaviseringar i Säkerhets- och efterlevnadscenter för & för att skapa aviseringar endast för aktiviteter som utförs av användare som finns med i organisationens adressbok. Du kan inte använda den här sidan för att skapa aviseringar om aktiviteter som utförs av externa användare som inte finns med i adressboken. 
    
## <a name="create-an-activity-alert"></a>Skapa en aktivitetsavisering

1. Gå till [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Logga in med ditt arbets- eller skolkonto.
    
3. På sidan **Aktivitetsaviseringar** klickar du på ![ Lägg till ikon ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Ny.**

   Den utfällna sidan för att skapa en aktivitetsavisering visas.

    
    ![Skapa en aktivitetsavisering](../media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. Skapa en aktivitetsavisering genom att fylla i följande fält:
    
    a. **Namn** – Ange ett namn på aviseringen. Aviseringsnamnen måste vara unika inom organisationen.
    
    b. **Beskrivning** (valfritt) – Beskriv aviseringen, t.ex. de aktiviteter och användare som spåras, och vilka användare som e-postaviseringar skickas till. Beskrivningar är ett snabbt och enkelt sätt att beskriva syftet med aviseringen för andra administratörer.
    
    c. **Aviseringstyp** – kontrollera att **alternativet** Anpassad är markerat. 

    d. **Skicka den här aviseringen när** – Klicka **på Skicka den här aviseringen när** och sedan konfigurera de här två fälten:
    
    - **Aktiviteter** – Klicka på listrutan för att visa de aktiviteter som du kan skapa en avisering för. Det här är samma aktivitetslista som visas när du söker i granskningsloggen. Du kan välja en eller flera specifika aktiviteter eller så kan du klicka på aktivitetsgruppnamnet för att markera alla aktiviteter i gruppen. En beskrivning av de här aktiviteterna finns i avsnittet "Granskade aktiviteter" i [Söka i granskningsloggen.](search-the-audit-log-in-security-and-compliance.md#audited-activities) När en användare utför någon av de aktiviteter som du har lagt till i aviseringen skickas en e-postavisering. 
    
     - **Användare** – Klicka i den här rutan och välj sedan en eller flera användare. Om användarna i den här rutan utför de aktiviteter som du har lagt till **i** rutan Aktiviteter skickas en avisering. Lämna rutan **Användare** tom för att skicka en avisering när en användare i organisationen utför de aktiviteter som anges av aviseringen. 

    e. Skicka den **här** aviseringen till – Klicka  på Skicka den här aviseringen och klicka sedan i rutan Mottagare  och skriv ett namn för att lägga till en användare som kommer att få en e-postavisering när en användare (anges i rutan Användare) utför en aktivitet (anges i **rutan** Aktiviteter).  Observera att du som standard läggs till i listan över mottagare. Du kan ta bort ditt namn från den här listan.
    
5. Klicka **på Spara** för att skapa aviseringen. 
    
    Den nya aviseringen visas i listan på sidan **Aktivitetsaviseringar.** 
    
    ![En lista med aviseringar visas på sidan Aktivitetsaviseringar](../media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    Status för aviseringen är På **.** Observera att de mottagare som får en e-postavisering när en avisering skickas också visas. 
  
## <a name="turn-off-an-activity-alert"></a>Inaktivera en aktivitetsavisering

Du kan inaktivera en aktivitetsavisering så att en e-postavisering inte skickas. När du har inaktiverat aktivitetsaviseringen visas den fortfarande i listan med aktivitetsaviseringar för organisationen, och du kan fortfarande visa dess egenskaper.
  
1. Gå till Gå till [https://protection.office.com/managealerts](https://protection.office.com/managealerts) .
    
2. Logga in med ditt arbets- eller skolkonto.
    
3. Klicka på den avisering du vill inaktivera i listan med aktivitetsaviseringar för organisationen.
    
4. På sidan **Redigera avisering** klickar du på **växlingsknappen** På för att ändra status till **Av** och klickar sedan på **Spara**.
    
    Statusen för aviseringen på sidorna **Aktivitetsaviseringar** är inställd på **Av**. 
    
Om du vill aktivera en aktivitetsavisering igen  upprepar du dessa steg och klickar på växlingsknappen Av för att ändra status till **På.**
  
## <a name="more-information"></a>Mer information

- Här är ett exempel på e-postmeddelandet som skickas till användare som anges i fältet Skickat  denna avisering till (och visas **under** Mottagare på sidan Aktivitetsaviseringar ) i efterlevnadscentret för säkerhet och &. 
    
    ![Exempel på ett e-postmeddelande som skickats för en aktivitetsavisering](../media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Här är några vanliga dokument- och e-postaktiviteter som du kan skapa aktivitetsaviseringar för. I tabellerna beskrivs aktiviteten, namnet på aktiviteten som du vill skapa en avisering för och  namnet på aktivitetsgruppen som aktiviteten visas under i listrutan Aktiviteter. En fullständig lista med aktiviteter som du kan skapa aktivitetsaviseringar för finns i avsnittet "Granskade aktiviteter" i [Söka i granskningsloggen.](search-the-audit-log-in-security-and-compliance.md#audited-activities)
    
    > [!TIP]
    > Du kanske vill skapa en aktivitetsavisering för bara en aktivitet som utförs av en användare. Eller så kanske du vill skapa en aktivitetsavisering som spårar flera aktiviteter som utförts av en eller flera användare. 
  
    I följande tabell visas några vanliga dokumentrelaterade aktiviteter i SharePoint eller OneDrive för företag.
    
    |**När en användare gör det här ...**|**Skapa en avisering för den här aktiviteten**|**Aktivitetsgrupp**|
    |:-----|:-----|:-----|
    |Visar ett dokument på en webbplats.  <br/> |Öppnad fil  <br/> |Fil- och mappaktiviteter  <br/> |
    |Redigerar eller ändrar ett dokument.  <br/> |Ändrad fil  <br/> |Fil- och mappaktiviteter  <br/> |
    |Delar ett dokument med en användare utanför organisationen.  <br/> |Dela fil, mapp eller webbplats  <br/> Och  <br/> Delningsinbjudan skapad  <br/> Mer information finns i Använda [delningsgranskning i granskningsloggen](use-sharing-auditing.md).  <br/> |Aktiviteter för delning och åtkomstbegäran  <br/> |
    |Laddar upp eller laddar ned ett dokument.  <br/> |Uppladdad fil  <br/> Och/eller  <br/> Nedladdad fil  <br/> |Fil- och mappaktiviteter  <br/> |
    |Ändrar åtkomstbehörigheter till en webbplats.  <br/> |Webbplatsbehörigheter ändrade  <br/> |Aktiviteter för webbplatsadministration  <br/> |

    I följande tabell visas några vanliga e-postrelaterade aktiviteter i Exchange Online.

    |**När en användare gör det här ...**|**Skapa en avisering för den här aktiviteten**|**Aktivitetsgrupp**|
    |:-----|:-----|:-----|
    |Tar bort (rensar) ett e-postmeddelande permanent från postlådan.  <br/> |Meddelanden rensades från postlådan  <br/> | Exchange postlådeaktiviteter  <br/> |
    |Skickar ett e-postmeddelande från en delad postlåda.  <br/> |Meddelande skickades med behörigheten Skicka som  <br/> Och  <br/> Meddelande skickades med behörigheten Skicka för  <br/> | Exchange postlådeaktiviteter  <br/> |
   
- Du kan också använda cmdletarna **New-ActivityAlert** och **Set-ActivityAlert** i Security & Compliance Center PowerShell för att skapa och redigera aktivitetsaviseringar. Tänk på följande om du använder dessa cmdlets för att skapa eller redigera aktivitetsaviseringar: 
    
  - Om du använder en cmdlet för att lägga till en  aktivitet i aviseringen som inte visas i listrutan Aktiviteter visas ett meddelande på egenskapssidan för aviseringen med meddelandet "Den här aviseringen har anpassade åtgärder som inte visas i väljaren". 
    
  - En god anledning att använda cmdlet:arna för att skapa eller redigera en aktivitetsavisering är att skicka e-postaviseringar till någon utanför organisationen. Den externa användaren visas i listan med mottagare för aviseringen. Men om du tar bort den externa användaren från aviseringen kan användaren inte läggas till i aviseringen på ny sida med hjälp av **sidan Redigera** avisering. Du måste lägga till den externa användaren på nytt med hjälp av cmdleten **Set-ActivityAlert** eller använda cmdleten **New-ActivityAlert** för att lägga till samma (eller andra) externa användare i en ny avisering. 
