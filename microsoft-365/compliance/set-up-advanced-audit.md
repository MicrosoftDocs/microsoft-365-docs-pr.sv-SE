---
title: Konfigurera avancerad granskning i Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: I den här artikeln beskrivs hur du ställer in Avancerad granskning så att du kan utföra undersökningar av en forensisk undersökning när användarkonton har komprometterats eller undersöka andra säkerhetsrelaterade incidenter.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314415"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>Konfigurera avancerad granskning i Microsoft 365

Om organisationen har en prenumeration och licensiering för slutanvändare som stöder avancerad granskning utför du följande steg för att konfigurera och använda de ytterligare funktionerna i Avancerad granskning.

![Arbetsflöde för att konfigurera Avancerad granskning för användare](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a>Steg1: Konfigurera avancerad granskning för användare

För Avancerad granskning-funktioner som möjligheten att logga viktiga händelser, till exempel MailItemsAccessed och Send, måste användarna ha tilldelats rätt E5-licens. Dessutom måste appen/tjänstplanen Advanced Auditing vara aktiverad för dessa användare. Du kan kontrollera att appen Advanced Auditing har tilldelats användarna genom att utföra följande steg för varje användare:

1. I [Administrationscenter för Microsoft 365](https://admin.microsoft.com/Adminportal) går du till **Användare** > **Aktiva användare** och väljer en användare.

2. Klicka på **Licenser och appar** på den utfällbara sidan med användaregenskaper.

3. I avsnittet **Licenser** kontrollerar du att användaren har tilldelats en E5-licens eller har tilldelats en lämplig tilläggslicens. En lista över licenser som stöder Avancerad granskning finns i [Licenskrav för avancerad granskning.](auditing-solutions-overview.md#advanced-audit-1)

4. Visa avsnittet **Appar** och kontrollera att kryssrutan **Microsoft 365 Advanced Auditing** är markerad.

5. Om kryssrutan inte är markerad markerar du den och klickar sedan på **Spara ändringar.**

   Loggning av granskningsposter för MailItemsAccessed och Send startar inom 24 timmar. Du måste utföra steg 3 för att börja loggning av två andra viktiga händelser för Avancerad granskning: SearchQueryInitiatedExchange och SearchQueryInitiatedSharePoint.

Om organisationen tilldelar licenser till grupper av användare med hjälp av gruppbaserad licensiering måste du inaktivera licenstilldelningen för Microsoft 365 Advanced Auditing för gruppen. När du har sparat ändringarna kontrollerar du att Microsoft 365 Advanced Auditing är inaktiverat för gruppen. Aktivera sedan licenstilldelningen för gruppen igen. Instruktioner för hur du använder gruppbaserad licensiering finns i [Tilldela licenser till användare efter gruppmedlemskap i Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).

Om du har anpassat postlådeåtgärder som loggas på användarpostlådor eller delade postlådor, granskas inte automatiskt nya nödvändiga händelser som släppts av Microsoft för dessa postlådor. Information om hur du ändrar postlådeåtgärderna som granskas för varje inloggningstyp finns i avsnittet ”Ändra eller återställa postlådeåtgärder som loggas som standard” i [Hantera postlådegranskning](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).

## <a name="step-2-enable-crucial-events"></a>Steg 2: Aktivera avgörande händelser

Du måste aktivera två avgörande händelser (SearchQueryInitiatedExchange och SearchQueryInitiatedSharePoint) som ska loggas när användare utför sökningar i Exchange Online och SharePoint Online. Om du vill aktivera de här två händelserna för användare kör du följande kommando (för varje användare) [i Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

I en geomiljö med flera platser  måste du köra det tidigare kommandot Uppsättningspostlåda i skogen där användarens postlåda finns. Kör följande kommando för att identifiera användarens postlådas plats: 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

Om kommandot för att aktivera granskning av sökfrågor tidigare kördes i en annan skog än den användarens postlåda finns i, måste du ta bort värdet searchQueryInitiated från användarens postlåda genom att köra och sedan lägga till det i användarens postlåda i skogen där användarens postlåda `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` finns.

## <a name="step-3-set-up-audit-retention-policies"></a>Steg 3: Konfigurera bevarandeprinciper för granskning

Utöver standardprincipen som behåller granskningsposter för Exchange, SharePoint och Azure AD i ett år kan du skapa ytterligare kvarhållningsprinciper för granskningsloggar så att de uppfyller kraven för organisationens säkerhetsåtgärder, IT- och efterlevnadsgrupper. Mer information finns i [Hantera kvarhållningsprinciper för granskningsloggar](audit-log-retention-policies.md).

## <a name="step-4-search-for-crucial-events"></a>Steg 4: Sök efter viktiga händelser

Nu när du har ställt in Avancerad granskning för din organisation kan du söka efter avgörande händelser och andra aktiviteter när du genomför avgörande undersökningar. När du har slutfört steg 1 och steg 2 kan du söka i granskningsloggen efter avgörande händelser och andra aktiviteter under undersökningar av komprometterade konton och andra typer av säkerhets- och efterlevnadsundersökningar. Mer information om en undersökning av komprometterade användarkonton genom att använda den viktiga händelsen MailItemsAccessed finns i Använda avancerad granskning för att undersöka [komprometterade konton.](mailitemsaccessed-forensics-investigations.md)
