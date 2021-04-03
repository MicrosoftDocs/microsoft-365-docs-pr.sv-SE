---
title: Microsoft Productivity Score – sekretess
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
description: Hur sekretess skyddas med Produktivitetsresultatet.
ms.openlocfilehash: 5b5997532ddcd1fdf43b4124f8e2d8183bb3d89e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579176"
---
# <a name="privacy-controls-for-productivity-score"></a>Sekretesskontroller för Produktivitetsresultat

Produktivitetsresultatet ger insikter om organisationens digitala omvandlingsresa genom användningen av Microsoft 365 och de teknikupplevelser som stöder det.  Organisationens resultat återspeglar mätvärden för personer och teknikupplevelse och kan jämföras med riktmärken från organisationer som påminner om din. Mer information finns i [översikten över Produktivitetsresultat.](productivity-score.md)

Din sekretess är viktig för Microsoft. Mer information om hur vi skyddar din integritet [finns i Microsofts sekretesspolicy.](https://privacy.microsoft.com/privacystatement) Produktivitetsresultatet ger dig som din organisations IT-administratör tillgång till sekretessinställningar så att du kan se till att den Produktivitetsresultatinformation du visar kan användas, samtidigt som du inte komprometterar betrodda platser i din organisation med Microsoft.

Inom området för personers upplevelser finns mätvärden endast tillgängliga på organisationsnivå. I det här området visas hur microsoft 365 används genom att titta på kategorier av innehållssamarbete, rörlighet, möten, samarbete och kommunikation. Vi ger dig flera nivåer av kontroller som hjälper dig att uppfylla dina interna sekretesspolicybehov.
Kontrollerna ger dig:

- Flexibla administratörsroller för att styra vem som kan se informationen i Produktivitetsresultatet.
- Möjligheten att välja bort upplevelseområdet för personer.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibla administratörsroller för att styra vem som kan se informationen i Produktivitetsresultatet

För att kunna se hela Produktivitetsresultatet behöver du vara en av följande administratörsroller:

- Global administratör
- Exchange-administratörer
- SharePoint-administratör
- Skype för företag-administratör
- Teams-administratör
- Global läsare
- Rapportläsare
- Sammanfattningsrapporter för användning

Tilldela rollen Rapportläsare eller Sammanfattningsrapporter för användning till alla som ansvarar för ändringshantering och införande, men inte nödvändigtvis en IT-administratör. Den här rollen ger dem tillgång till hela Produktivitetsresultatet i administrationscentret för Microsoft 365.

Rollen Läsare för sammanfattningsrapporter för användning måste tilldelas via PowerShell-cmdlets tills den blir tilldelningsbar från administrationscentret för Microsoft 365 senare under 2020.

Så här tilldelar du rollen Sammanfattningsrapporter för användning med PowerShell:

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Möjlighet att avanmäla sig från användarupplevelser

Du kan också välja att inte delta i området Produktivitetsresultat. Om du väljer bort detta kan ingen i organisationen visa måtten och organisationen tas bort från alla beräkningar som inbegriper kommunikation, möten, samarbete, innehållssamarbete och rörlighet. Du måste vara global administratör för att kunna välja bort personernas upplevelser i rapporter.

Så här gör du för att avanmäla:

1. I administrationscentret går du till **Inställningar Org**   >   **Settings Productivity**  >  **Score**.
2. Avmarkera kryssrutan tillåt att **Microsoft 365-användningsdata används för personer med insikter om användningen.** Om du vill veta hur du ändrar inställningarna för datadelning för Slutpunktsanalys i Intune-konfigurationshanteraren väljer **du Läs mer.**
3. Välj  **Spara**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Sidan Organisationsinställningar där du kan avanmäla dig från personliga upplevelser.":::
