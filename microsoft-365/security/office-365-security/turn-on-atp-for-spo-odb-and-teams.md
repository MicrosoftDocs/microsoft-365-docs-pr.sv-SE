---
title: Aktivera Office 365 ATP – SharePoint, OneDrive & Teams
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
ms.openlocfilehash: 6109cecc79b4db876ee595d4786d176ae7f42f5d
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656557"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivera ATP för SharePoint, OneDrive och Microsoft Teams

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hem användare letar efter information om säkra länkar i Outlook kan du läsa mer i [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) skyddar din organisation från oavsiktlig delning av skadliga filer. När en skadlig fil identifieras blockeras den så att ingen kan öppna, kopiera, flytta eller dela den innan ytterligare åtgärder vidtas av organisationens säkerhets team. Läs den här artikeln om du vill aktivera ATP för SharePoint, OneDrive och Teams, konfigurera aviseringar om du vill få meddelanden om identifierade filer och ta nästa steg.

Om du vill definiera (eller redigera) ATP-principer måste du ha en lämplig roll. Några exempel beskrivs i följande tabell:

****

|Roll|Där/hur kopplat|
|---|---|
|global administratör|Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Säkerhets administratör|Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Organisations hantering i Exchange Online|Administrations Center för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivera ATP för SharePoint, OneDrive och Microsoft Teams

**Innan du påbörjar den här proceduren bör du kontrol lera att gransknings loggning redan är aktiverat för din Microsoft 365-miljö**. Det gör du vanligt vis av någon som har rollen gransknings loggar som tilldelats i Exchange Online. Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).

1. Gå till <https://protection.office.com> och logga in med ditt arbets-eller skol konto.

2. I det vänstra navigerings **fältet under säkerhets**& Compliance Center väljer du **policy** \> **Safe Attachments**.

   ![Välj Threat Management policy i Center för säkerhet & efterlevnad \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

   ![Aktivera avancerat skydd för SharePoint Online, OneDrive för företag och Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. Klicka på **Spara**.

5. Granska (och, om tillämpligt, redigera) organisationens principer för [säkert bifogade filer](set-up-atp-safe-attachments-policies.md) och [säkra länkar](set-up-atp-safe-links-policies.md).

6. Lämpligt Som global administratör eller SharePoint Online-administratör kör du cmdleten **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** med parametern _DisallowInfectedFileDownload_ angiven till *True*.

   - Om du anger parametern till *True* blockeras alla åtgärder (förutom borttagning) för identifierade filer. Personer kan inte öppna, flytta, kopiera eller dela identifierade filer.

   - Om du anger parametern till *falskt* blockeras alla åtgärder förutom Delete och nedladdning. Andra kan välja att acceptera risken och hämta en identifierad fil.

7. Tillåt upp till 30 minuter för att ändringarna ska spridas till alla Microsoft 365-datacenter.

8. Lämpligt Fortsätt med att konfigurera aviseringar för identifierade filer.

Mer information om hur du använder PowerShell med Microsoft 365 finns i [Hantera Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).

Om du vill veta mer om användar upplevelsen när en fil har identifierats som skadlig, se [vad du kan göra när en skadlig fil finns i SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="set-up-alerts-for-detected-files"></a>Konfigurera aviseringar för identifierade filer

Om du vill få aviseringar när en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams har identifierats som skadlig kan du ställa in en avisering.

1. I fönstret [säkerhets & efterlevnad](https://protection.office.com)väljer du **aviseringar** \> **Hantera aviseringar**.

2. Välj **ny aviserings princip**.

3. Ange ett namn för aviseringen. Du kan till exempel skriva in skadliga filer i bibliotek.

4. Ange en beskrivning av aviseringen. Du kan till exempel skriva meddelanden administratörer när skadliga filer upptäcks i SharePoint Online, OneDrive eller Microsoft Teams.

5. Gör följande i avsnittet **Skicka aviseringen när...** :

   a. Välj **upptäckt skadlig kod i filen**i listan **aktiviteter** .

   b. Lämna fältet **användare** tomma.

6. I avsnittet **Skicka aviseringen till... väljer du** en eller flera globala administratörer, säkerhets administratörer eller säkerhets läsare som ska få avisering när en skadlig fil identifieras.

7. Klicka på **Spara**.

Om du vill veta mer om aviseringar läser [du skapa aktivitets aviseringar i avsnittet säkerhets & efterlevnad](../../compliance/create-activity-alerts.md).

## <a name="next-steps"></a>Nästa steg

1. [Visa information om skadliga filer som identifieras i SharePoint, OneDrive eller Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

2. [Hantera meddelanden och filer i karantän som administratör i Microsoft 365](manage-quarantined-messages-and-files.md)
