---
title: Aktivera säkra bilagor för SharePoint, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Administratörer kan lära sig hur de aktiverar Valv-filer för SharePoint, OneDrive och Microsoft Teams, inklusive hur du ställer in aviseringar för identifierade filer.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083098"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivera säkra bilagor för SharePoint, OneDrive och Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams skyddar organisationen från att oavsiktligt dela skadliga filer. Mer information finns i Bifoga [Valv för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md).

Den här artikeln innehåller anvisningar för hur du aktiverar och konfigurerar Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>. Gå direkt till sidan **Valv genom** att öppna <https://security.microsoft.com/safeattachmentv2> .

- Om du Valv aktivera bifogade filer för SharePoint, OneDrive och Microsoft Teams måste du vara medlem i  rollgrupperna  Organisationshantering eller Säkerhetsadministratör i Microsoft 365 Defender portalen. Mer information finns under [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).

- Om du vill använda SharePoint Online PowerShell för att förhindra att användare [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) laddar ned skadliga filer måste du vara medlem i den globala administratören eller [administratörsrollen SharePoint](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) i Azure AD.

- Kontrollera att granskningsloggning är aktiverat för organisationen. Du kan läsa mer i [Aktivera och inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).

- Det kan ta upp till 30 minuter innan inställningarna verkställs.

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Steg 1: Använd Microsoft 365 Defender-portalen för att aktivera Valv för SharePoint, OneDrive och Microsoft Teams

1. I Microsoft 365 Defender-portalen går du till **Principer & Principer** för \>  \> **hotregler Valv** \> **Bifogade filer.**

2. På sidan **Valv bifogade** filer klickar du på **Globala inställningar.**

3. I den globala inställningsfällan som visas går du till avsnittet Skydda filer i **SharePoint, OneDrive och Microsoft Teams.** 

   Flytta **växlingsknappen** Aktivera Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams till höger aktivera växlingsknappen för att aktivera ![ ](../../media/scc-toggle-on.png) Valv-bilagor för SharePoint, OneDrive och Microsoft Teams.

   Klicka på **Spara** när du är klar.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Använd Exchange Online PowerShell för att aktivera Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams

Om du hellre vill använda PowerShell för att aktivera Valv-bilagor för SharePoint, OneDrive och Microsoft Teams ansluter du [till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) och kör följande kommando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Detaljerad information om syntax och parametrar finns i [Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Steg 2: (Rekommenderas) Använd SharePoint Online PowerShell för att hindra användare från att hämta skadliga filer

Som standard kan användare inte öppna, flytta, kopiera eller dela skadliga filer som identifieras av <sup>\*</sup> Valv-bilagor för SharePoint, OneDrive och Microsoft Teams. Däremot kan de ta bort och ladda ned skadliga filer.

<sup>\*</sup> Om användarna går **till Hantera åtkomst** är **alternativet** Dela fortfarande tillgängligt.

För att hindra användare från att hämta skadliga filer [ansluter du till SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) och kör följande kommando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Anmärkningar**:

- Den här inställningen påverkar både användare och administratörer.
- Användare kan fortfarande ta bort skadliga filer.

Detaljerad information om syntax och parametrar finns [i Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>Steg 3 (rekommenderas) Använd Microsoft 365 Defender-portalen för att skapa en aviseringsprincip för identifierade filer

Du kan skapa en aviseringsprincip som meddelar dig och andra administratörer när Valv-bilagor för SharePoint, OneDrive och Microsoft Teams upptäcker en skadlig fil. Mer information om aviseringar finns i [Skapa aktivitetsaviseringar i Microsoft 365 Defender portalen.](../../compliance/create-activity-alerts.md)

1. I Microsoft 365 Defender går du till Principer **för &** \> **Principavisering eller** öppnar <https://security.microsoft.com/alertpolicies> .

2. Klicka på **Ny aviseringsprincip** **på sidan Aviseringsprincip.**

3. Guiden **Ny aviseringsprincip** öppnas i en flyg ut. På sidan **Namnge din avisering** konfigurerar du följande inställningar:
   - **Namn**: Ange ett unikt och beskrivande namn. Till exempel Skadliga filer i bibliotek.
   - **Beskrivning**: Ange en valfri beskrivning. Meddelar till exempel administratörer när skadliga filer identifieras i SharePoint Online, OneDrive eller Microsoft Teams.
   - **Allvarlighetsgrad**: **Välj Låg,** **Medel** eller **Hög** i listrutan.
   - **Kategori:** **Välj Hothantering** i listrutan.

   Klicka på **Nästa** när du är klar.

4. Konfigurera **följande inställningar på** sidan Skapa aviseringsinställningar:
   - **Vad vill du avisering om?** avsnitt \> **Aktivitet är** \> Välj Skadlig programvara i **filen** i listrutan.
   - **Hur vill du att aviseringen ska utlösas?** avsnitt: Lämna standardvärdet **Varje gång en aktivitet matchar den valda** regeln.

   Klicka på **Nästa** när du är klar.

5. På sidan **Ange mottagare** konfigurerar du följande inställningar:
   - Kontrollera **att Skicka e-postaviseringar** är markerat. I rutan **E-postmottagare** markerar du en eller flera globala administratörer, säkerhetsadministratörer eller säkerhetsläsare som ska få ett meddelande när en skadlig fil identifieras.
   - **Daglig meddelandegräns:** Lämna standardvärdet **Ingen gräns** markerat.

   Klicka på **Nästa** när du är klar.

6. Granska **inställningarna på sidan** Granska dina inställningar. Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.

   I avsnittet Vill du aktivera principen **direkt?** låter du standardvärdet Vara **Ja, aktivera det direkt markerat.**

   Klicka på Slutför när du är **klar.**

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Använd Security & Compliance PowerShell för att skapa en aviseringsprincip för identifierade filer

Om du hellre vill använda PowerShell för att skapa samma aviseringsprincip som beskrivs i föregående avsnitt kan du ansluta till [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) och köra följande kommando:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Obs!** Standardvärdet _för allvarlighetsgrad_ är Låg. Om du vill ange Medel eller Hög tar du _med parametern Allvarlighetsgrad_ och värdet i kommandot.

Detaljerad information om syntax och parametrar finns [i New-ActivityAlert](/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

- Kontrollera att du har aktiverat Valv för SharePoint, OneDrive och Microsoft Teams genom att göra något av följande:

  - I Microsoft 365 Defender-portalen går du till **Policies & rules** Threat \>  \> **Policies** \> **(regler** för hotprinciper) Valv  Bifogade filer , väljer Globala inställningar och verifierar värdet för inställningen Aktivera Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams.

  - I Exchange Online PowerShell kör du följande kommando för att verifiera egenskapsinställningen:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)

- Kontrollera att du har blockerat användare från att hämta skadliga filer genom att öppna SharePoint Online PowerShell och köra följande kommando för att verifiera egenskapsvärdet:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Detaljerad information om syntax och parametrar finns i [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

- Verifiera att du har konfigurerat en aviseringsprincip för identifierade filer genom att göra något av följande:
  - I Microsoft 365 Defender går du till Principer **& princip** för avisering \>  \> markerar aviseringsprincipen och kontrollerar inställningarna.
  - I Microsoft 365 Defender-portalen Ersätter du med namnet på aviseringsprincipen, kör följande kommando \<AlertPolicyName\> och verifierar egenskapsvärdena:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Detaljerad information om syntax och parametrar finns i [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).

- Använd rapporten [status för skydd mot](view-email-security-reports.md#threat-protection-status-report) hot om du vill visa information om identifierade filer i SharePoint, OneDrive och Microsoft Teams. Specifikt kan du använda vyn Visa **data efter: Vyn \> Skadlig** programvara för innehåll.
