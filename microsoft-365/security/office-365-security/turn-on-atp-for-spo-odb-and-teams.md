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
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326919"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivera ATP för SharePoint, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Office 365 Avancerat skydd (ATP) för SharePoint, OneDrive och Microsoft Teams skyddar din organisation från oavsiktlig delning av skadliga filer. Mer information finns i [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).

I den här artikeln beskrivs hur du aktiverar och konfigurerar ATP för SharePoint, OneDrive och Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com>. Om du vill gå direkt till sidan **betrodda säkerhets** meddelanden via ATP öppnar du <https://protection.office.com/safeattachmentv2> .

- För att aktivera ATP för SharePoint, OneDrive och Microsoft Teams måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** i säkerhets & Compliance Center. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

- Om du vill använda SharePoint Online PowerShell för att förhindra att andra laddar ned skadliga filer måste du vara medlem i rollen [Global administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) eller [administratör för SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) i Azure AD.

- Kontrol lera att gransknings loggning är aktiverat för din organisation. Mer information finns i [Aktivera eller inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).

- Tillåt upp till 30 minuter innan ändringarna börjar gälla.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Steg 1: Använd säkerhets & Compliance Center för att aktivera ATP för SharePoint, OneDrive och Microsoft Teams

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policys** \> **ATP Safe Attachments**och kan välja **globala inställningar**.

2. I de **globala inställningarna** , flyg ut som visas, går du till inställningen **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** . Flytta växlings knappen till höger ![ om ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) du vill aktivera ATP för SharePoint, OneDrive och Microsoft Teams.

   Klicka på **Spara** när du är klar.

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Använda Exchange Online PowerShell för att aktivera ATP för SharePoint, OneDrive och Microsoft Teams

Om du hellre vill använda PowerShell för att aktivera ATP för SharePoint, OneDrive och Microsoft Teams [ansluter du till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Detaljerad information om syntax och parametrar finns i [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Steg 2: (rekommenderas) Använd SharePoint Online PowerShell för att förhindra att användare laddar ned skadliga filer

Som standard kan användare inte öppna, flytta, kopiera eller dela filer som identifieras via ATP. Men de kan ta bort och hämta skadliga filer.

För att förhindra att användare laddar ned skadliga filer, [Anslut till SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) och kör följande kommando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Anmärkningar**:

- Den här inställningen påverkar både användare och administratörer.
- Personer kan fortfarande ta bort skadliga filer.

Detaljerad information om syntax och parametrar finns i [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Steg 3 (rekommenderas) Använd säkerhets & Compliance Center för att skapa en aviserings princip för identifierade filer

Du kan skapa en aviserings policy som meddelar dig och andra administratörer när ATP för SharePoint, OneDrive och Microsoft Teams identifierar en skadlig fil. Om du vill veta mer om aviseringar läser [du skapa aktivitets aviseringar i avsnittet säkerhets & efterlevnad](../../compliance/create-activity-alerts.md).

1. Gå till **aviserings** principer för varningar eller öppna i fönstret [säkerhets & efterlevnad](https://protection.office.com) \> **Alert policies** <https://protection.office.com/alertpolicies> .

2. Klicka på **ny aviserings princip**på sidan **aviserings principer** .

3. Guiden **ny aviserings princip** öppnas när du flyger ut. På sidan **namnge din avisering** konfigurerar du följande inställningar:

   - **Name**: Skriv in ett unikt och beskrivande namn. Till exempel skadliga filer i bibliotek.
   - **Beskrivning**: Skriv en valfri beskrivning. Till exempel meddelar administratörer när skadlig filer identifieras i SharePoint Online, OneDrive eller Microsoft Teams.
   - **Allvarlighets grad**: lämna standardvärdet **lågt** markerat eller Välj **mellan** eller **hög**.
   - **Välj en kategori**: Välj **Threat Management**.

   När du är klar klickar du på **Nästa**.

4. Konfigurera följande inställningar på sidan **skapa aviserings inställningar** :

   - **Vad vill du varna för?: aktiviteten är**: Välj **upptäckt skadlig kod i filen**.
   - **Hur vill du att notifieringen ska utlösas?** lämna standardvärdet **varje gång en aktivitet matchar den valda regeln** .

   När du är klar klickar du på **Nästa**.

5. På sidan **Ange mottagarna** konfigurerar du följande inställningar:

   - **Skicka e-postmeddelanden**: kontrol lera att den här inställningen är markerad. I rutan **e-postmottagare** väljer du en eller flera globala administratörer, säkerhets administratörer eller säkerhets läsare som ska få avisering när en skadlig fil identifieras.
   - **Daglig meddelande gräns**: lämna standardvärdet **ingen gräns** markerat.

   När du är klar klickar du på **Nästa**.

6. På sidan **Granska inställningar** granskar du inställningarna och klickar på **Redigera** i något av avsnitten för att göra ändringar.

   I avsnittet **vill du aktivera policyn direkt? lämnar du** standardvärdet **Ja, sätter det på direkt** markerat.

   När du är klar klickar du på **Slutför**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Använda säkerhets & kompabilitet för att skapa en aviserings princip för identifierade filer

Om du hellre vill använda PowerShell för att skapa samma aviserings princip enligt beskrivningen i föregående avsnitt, [ansluter du till säkerhets & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) och kör följande kommando:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Obs!** standardvärdet för _allvarlighets grad_ är lågt. Om du vill ange medium eller hög inkluderar du _allvarlighets GRADS_ parametern och värdet i kommandot.

Detaljerad information om syntax och parametrar finns i [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

- Så här kontrollerar du att du har aktiverat ATP för SharePoint, OneDrive och Microsoft Teams på något av följande sätt:

  - I [säkerhets & Compliance Center](https://protection.office.com)går du till **hanterings princip för hot Management** \> **Policy** \> **ATP Safe Attachments**, väljer **globala inställningar**och kontrollerar värdet på inställningen för att **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .

  - I Exchange Online PowerShell kör du följande kommando för att kontrol lera inställningen för egenskapen:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).

- Om du vill kontrol lera att du har blockerat personer från att ladda ned skadliga filer öppnar du SharePoint Online PowerShell och kör följande kommando för att verifiera egenskapens värde:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Detaljerad information om syntax och parametrar finns i [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

- Så här kontrollerar du att du har konfigurerat en aviserings princip för identifierade filer:

  - Gå till **aviserings** principer i säkerhets & för säkerhet \> **Alert policies** \> och välj varnings principen och kontrol lera inställningarna.

  - I säkerhets & Compliance Center PowerShell, Ersätt \<AlertPolicyName\> med namnet på aviserings principen, kör följande kommando och verifierar egenskapsvärdena:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Detaljerad information om syntax och parametrar finns i [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).

- Använd [rapporten Threat Protection status](view-email-security-reports.md#threat-protection-status-report) för att visa information om identifierade filer i SharePoint, OneDrive och Microsoft Teams. Specifikt kan du använda **Visa data via: vyn \> skadlig program vara** .
