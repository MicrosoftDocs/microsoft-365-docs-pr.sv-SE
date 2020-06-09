---
title: Aktivera Office 365 ATP - SharePoint, OneDrive & Teams
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1276faf9883fda9bb73674b27f3e5fb1a648d5d3
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613402"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivera ATP för SharePoint, OneDrive och Microsoft Teams

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hemanvändare och letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från att oavsiktligt dela skadliga filer. När en skadlig fil upptäcks blockeras filen så att ingen kan öppna, kopiera, flytta eller dela den förrän ytterligare åtgärder vidtas av organisationens säkerhetsteam. Läs den här artikeln om du vill aktivera ATP för SharePoint, OneDrive och Teams, konfigurera aviseringar som ska meddelas om identifierade filer och vidta nästa steg.

Om du vill definiera (eller redigera) ATP-principer måste du tilldelas en lämplig roll. Några exempel beskrivs i följande tabell:

|Roll|Var/hur tilldelas|
|---------|---------|
|global administratör|Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Läs [mer om Microsoft 365-administratörsroller.)](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Säkerhetsadministratör|Administrationscenter för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Hantering av Exchange Online-organisation|Administrationscenter för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivera ATP för SharePoint, OneDrive och Microsoft Teams

**Innan du påbörjar den här proceduren kontrollerar du att granskningsloggning redan är aktiverat för din Microsoft 365-miljö**. Detta görs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online. Mer information finns i [Aktivera eller inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets- eller skolkonto.

2. I säkerhets- & Compliance Center, i det vänstra navigeringsfönstret, under **Hothantering,** väljer du **Policy** \> **Principsäkra bilagor**.

   ![I Security & Compliance Center väljer du Policy för hantering \> av hot](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

   ![Aktivera Avancerat skydd mot hot för SharePoint Online, OneDrive för företag och Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. Klicka på **Spara**.

5. Granska (och, beroende på vad som är lämpligt, redigera) organisationens [principer för säkra bilagor](set-up-atp-safe-attachments-policies.md) och principer för säkra [länkar](set-up-atp-safe-links-policies.md).

6. (Rekommenderas) Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern _DisallowInfectedFileDownload_ inställd på *true*.

   - Om du ställer in parametern på *true* blockerar alla åtgärder (utom Ta bort) för identifierade filer. Personer kan inte öppna, flytta, kopiera eller dela identifierade filer.

   - Om du ställer in parametern för *att fela* blockerar alla åtgärder utom Ta bort och hämta. Personer kan välja att acceptera risken och ladda ner en upptäckt fil.

7. Tillåt upp till 30 minuter innan ändringarna sprids till alla Microsoft 365-datacenter.

8. (Rekommenderas) Fortsätt att ställa in aviseringar för identifierade filer.

Mer information om hur du använder PowerShell med Microsoft 365 finns i [Hantera Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).

Mer information om användarupplevelsen när en fil har identifierats som skadlig finns [i Vad du ska göra när en skadlig fil hittas i SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/en-us/office/what-to-do-when-a-malicious-file-is-found-in-sharepoint-online-onedrive-or-microsoft-teams-01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="set-up-alerts-for-detected-files"></a>Konfigurera aviseringar för identifierade filer

Om du vill få ett meddelande när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du ställa in en avisering.

1. I [Säkerhets- & Compliance Center](https://protection.office.com)väljer du **Aviseringar** \> **Hantera aviseringar**.

2. Välj **Ny aviseringsprincip**.

3. Ange ett namn för aviseringen. Du kan till exempel skriva skadliga filer i bibliotek.

4. Skriv en beskrivning för aviseringen. Du kan till exempel skriva Notifierar administratörer när skadliga filer identifieras i SharePoint Online, OneDrive eller Microsoft Teams.

5. Gör följande i avsnittet Skicka den **här varningen när...**

   a. I listan **Aktiviteter** väljer du **Identifierad skadlig kod i filen**.

   b. Lämna fältet **Användare** tomt.

6. I avsnittet **Skicka den här aviseringen till...** väljer du en eller flera globala administratörer, säkerhetsadministratörer eller säkerhetsläsare som ska få ett meddelande när en skadlig fil identifieras.

7. Klicka på **Spara**.

Mer information om aviseringar finns [i Skapa aktivitetsaviseringar i Säkerhets- & Compliance Center](../../compliance/create-activity-alerts.md).

## <a name="next-steps"></a>Nästa steg

1. [Visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

2. [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
