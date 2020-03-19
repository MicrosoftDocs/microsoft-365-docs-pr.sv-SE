---
title: Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Lär dig hur du aktiverar ATP för SharePoint, OneDrive och Teams, inklusive hur du ställer in aviseringar för identifierade filer.
ms.openlocfilehash: 2596dade32d387669eb136856b7a24a66134a773
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806050"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Advanced Threat Protection](office-365-atp.md). Om du är hemanvändare som letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från att oavsiktligt dela skadliga filer. När en skadlig fil identifieras blockeras filen så att ingen kan öppna, kopiera, flytta eller dela den tills ytterligare åtgärder vidtas av organisationens säkerhetsteam. Läs den här artikeln om du vill aktivera ATP för SharePoint, OneDrive och Teams, konfigurera aviseringar som ska meddelas om identifierade filer och gör nästa steg.

Om du vill definiera (eller redigera) ATP-principer måste du tilldelas en lämplig roll. Några exempel beskrivs i följande tabell:

|Roll|Var/hur tilldelad|
|---------|---------|
|Global administratör för Office 365|Personen som registrerar sig för att köpa Office 365 är som standard en global administratör. (Se [Om Office 365-administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) att lära sig mer.)|
|Säkerhetsadministratör|Administrationscenter för[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory ( )|
|Exchange Online Organisation Management|Administrationscenter[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)för Exchange ( ) <br>eller <br>  PowerShell-cmdlets (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivera ATP för SharePoint, OneDrive och Microsoft Teams

**Innan du påbörjar den här proceduren kontrollerar du att granskningsloggning redan är aktiverad för Office 365-miljön**. Detta görs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online. Mer information finns i [Aktivera eller inaktivera granskningsloggen för Office 365.](../../compliance/turn-audit-log-search-on-or-off.md)

1. Gå [https://protection.office.com](https://protection.office.com)till och logga in med ditt arbets- eller skolkonto.

2. Välj **Threat management** **Principsäkra** \> **bifogade filer**i det vänstra navigeringsfönstret i Office 365 Security & Compliance Center.

   ![Välj Principer för säkerhets& efterlevnad \> väljer du principer för hantering av hot](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

   ![Aktivera avancerat hotskydd för SharePoint Online, OneDrive för företag och Microsoft-team](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. Klicka på **Spara**.

5. Granska (och, beroende på vad som är lämpligt, redigera) organisationens [principer för säkra bilagor](set-up-atp-safe-attachments-policies.md) och principer för säkra [länkar](set-up-atp-safe-links-policies.md).

6. (Rekommenderas) Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern _DisallowInfectedFileDownload_ inställd på *true*.

   - Om du ställer in parametern på *true* blockeras alla åtgärder (utom Ta bort) för identifierade filer. Personer kan inte öppna, flytta, kopiera eller dela identifierade filer.

   - Om du ställer in parametern på *false* block blockerar alla åtgärder utom Ta bort och hämta. Personer kan välja att acceptera risken och ladda ner en upptäckt fil.

7. Ge upp till 30 minuter innan ändringarna sprids till alla Office 365-datacenter.

8. (Rekommenderas) Fortsätt att konfigurera aviseringar för identifierade filer.

Mer information om hur du använder PowerShell med Office 365 finns i [Hantera Office 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).

Mer information om användarupplevelsen när en fil har identifierats som skadlig läser du [Vad du ska göra när en skadlig fil hittas i SharePoint Online, OneDrive eller Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="set-up-alerts-for-detected-files"></a>Konfigurera aviseringar för identifierade filer

Om du vill ta emot ett meddelande när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du skapa en avisering.

1. I [Office 365 Security & Compliance Center](https://protection.office.com)väljer du **Aviseringar** \> **Hantera aviseringar**.

2. Välj **Ny aviseringsprincip**.

3. Ange ett namn på aviseringen. Du kan till exempel skriva Skadliga filer i bibliotek.

4. Skriv en beskrivning för aviseringen. Du kan till exempel skriva Meddelar administratörer när skadliga filer identifieras i SharePoint Online, OneDrive eller Microsoft Teams.

5. Gör följande i avsnittet Skicka den **här aviseringen när...**

   A. I listan **Aktiviteter** väljer du **Upptäckt skadlig kod i filen**.

   B. Lämna fältet **Användare** tomt.

6. Markera en eller flera globala administratörer, säkerhetsadministratörer eller säkerhetsläsare i avsnittet Skicka den **här aviseringen till...**

7. Klicka på **Spara**.

Mer information om aviseringar finns [i Skapa aktivitetsaviseringar i Office 365 Security & Compliance Center](../../compliance/create-activity-alerts.md).

## <a name="next-steps"></a>Nästa steg

1. [Visa information om skadliga filer som upptäckts i SharePoint- eller OneDrive- eller Microsoft-teams](malicious-files-detected-in-spo-odb-or-teams.md)

2. [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md)
