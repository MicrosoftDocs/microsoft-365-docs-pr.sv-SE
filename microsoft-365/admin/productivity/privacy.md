---
title: Microsoft produktivitets Poäng – integritet
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Hur integritet skyddas med produktivitets poängen.
ms.openlocfilehash: db123042761b07ed64dd2dd94e783d65205e1460
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561520"
---
# <a name="privacy-controls-for-productivity-score"></a>Integritets inställningar för produktivitets Poäng

Produktivitets Poäng tillhandahåller insikter i organisationens digitala Transformation-resa via dess användning av Microsoft 365 och de teknik funktioner som stöder det.  Din organisations Poäng återspeglar funktionerna för folk-och teknik upplevelse och kan jämföras med benchmarks från organisationer som liknar ditt. Mer information finns i [Översikt över produktivitets poängen](productivity-score.md).

Din integritet är viktig för Microsoft. Information om hur vi skyddar din integritet finns i [Microsofts sekretess policy](https://privacy.microsoft.com/privacystatement). Produktivitets poäng ger dig, som organisationens IT-administratör, åtkomst till integritets inställningar som hjälper dig att se till att Poäng informationen du visar är åtgärdbar, men inte äventyrar förtroendet för organisationen i Microsoft.

I området personer kan du använda måtten endast på organisations nivå. Det här området visar hur personer använder Microsoft 365 genom att titta på kategorier av innehålls samarbete, mobilitet, möten, samarbete och kommunikation. Vi gör det möjligt för dig att möta dina interna integritets policy behov.
Kontrollerna ger dig:

- Flexibla administratörs roller för att kontrol lera vem som kan se informationen i produktivitets poängen.
- Möjligheten att välja bort området personer.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibla administratörs roller för att styra vem som kan se informationen i produktivitets poängen

Om du vill visa hela produktivitets poängen måste du ha någon av följande administratörs roller:

- Global administratör
- Exchange-administratörer
- SharePoint-administratör
- Skype för företag-administratör
- Teams-administratör
- Global läsare
- Rapport läsare
- Översikt över användnings sammanfattnings rapporter

Tilldela rapport läsaren en rapport läsare och rollen användnings översikt till alla som har ansvar för ändrings hantering och antagande, men inte nödvändigt vis en IT-administratör. Den här rollen ger dem till gång till den kompletta produktivitets upplevelsen i Microsoft 365 Admin Center.

Rollen rapport läsare för användnings översikt måste tilldelas via PowerShell-cmdletar tills den blir tillgänglig från Microsoft 365 Admin Center senare i 2020.

Så här tilldelar du rollen användnings översikts rapporter med PowerShell:

- Kör följande PowerShell:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>Möjlighet att avanmäla folk upplevelsen

Du kan också säga av området personer som är produktivt. Om du avmarkerar det här kan du inte se något från din organisation, och organisationen tas bort från alla beräkningar som rör kommunikation, möten, samarbete, innehålls samarbete och mobilitet.

Så här väljer du:

1. Gå till **Inställningar** i administrations centret   >   **Org Settings** och välj **rapporter** på fliken **tjänster** .
2. Avmarkera kryss rutan för att visa att  **Microsoft 365-användnings data ska användas för folk upplevelsen**. Om du vill förstå hur du ändrar inställningar för data delning för slut punkts analys i Intune-konfigurationsverktyget väljer du **Läs mer**.
3. Välj  **Spara**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Sidan organisations inställningar där du kan välja bort från folk upplevelsen.":::