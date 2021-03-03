---
title: Microsoft Productivity Score – sekretess
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
description: Hur sekretess skyddas med Productivity Score.
ms.openlocfilehash: b522c40cba746f3a4ede2404cf671607d62a3282
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406566"
---
# <a name="privacy-controls-for-productivity-score"></a>Sekretesskontroller för Produktivitetsresultat

Produktivitetsresultatet ger insikter om organisationens digitala omvandlingsresa genom användningen av Microsoft 365 och de teknikupplevelser som stöder den.  Organisationens resultat återspeglar mätvärden för personer och teknikupplevelse och kan jämföras med riktvärden från organisationer som påminner om dig. Mer information finns i [översikten över Produktivitetsresultat.](productivity-score.md)

Din sekretess är viktig för Microsoft. Mer information om hur vi skyddar din integritet [finns i Microsofts sekretesspolicy.](https://privacy.microsoft.com/privacystatement) Med Productivity Score får du, som är din organisations IT-administratör, tillgång till sekretessinställningar så att du kan se till att all produktivitetsresultatinformation som du visar kan vidtas, samtidigt som det inte komprometterar det förtroende din organisation placerar i Microsoft.

Inom området för personers upplevelser finns mätvärden endast på organisationsnivå. I det här området ser vi hur personer använder Microsoft 365 genom att titta på kategorierna för innehållssamarbete, rörlighet, möten, samarbete och kommunikation. Vi ger dig flera nivåer av kontroller som hjälper dig att uppfylla dina interna sekretesspolicybehov.
Kontrollerna ger dig:

- Flexibla administratörsroller för att styra vem som kan se informationen i Produktivitetsresultatet.
- Möjligheten att avanmäla sig från området för upplevelser i personer.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibla administratörsroller för att styra vem som kan se informationen i Produktivitetsresultatet

Om du vill visa hela Produktivitetsresultatet behöver du en av följande administratörsroller:

- Global administratör
- Exchange-administratörer
- SharePoint-administratör
- Skype för företag-administratör
- Teams-administratör
- Global läsare
- Rapportläsare
- Sammanfattningsrapporter för användning

Tilldela rollen Rapportläsare eller Sammanfattningsrapporter för användning till alla som ansvarar för ändringshantering och införande, men inte nödvändigtvis en IT-administratör. Den här rollen ger dem tillgång till hela Produktivitetsresultatet i administrationscentret för Microsoft 365.

Rollen Läsare för sammanfattningsrapporter för användning måste tilldelas via PowerShell-cmdlets tills den tilldelas från administrationscentret för Microsoft 365 senare under 2020.

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Möjlighet att välja bort användarupplevelser

Du kan också välja bort att delta i området för produktivitetsresultat. Om du väljer bort detta kan ingen i organisationen visa dessa mått och organisationen tas bort från alla beräkningar som inbegriper kommunikation, möten, samarbete, innehållssamarbete och rörlighet. Du måste vara global administratör för att kunna välja bort din organisation från rapporterna om personers upplevelser.

Så här avanmäler du dig:

1. Gå till Inställningar för produktivitetsresultat **för**   >   **organisation i**  >  **administrationscentret.**
2. Avmarkera kryssrutan där det står Tillåt **att Microsoft 365-användningsdata används för insikter om användarupplevelser.** Om du vill veta mer om hur du ändrar inställningarna för datadelning för Endpoint Analytics i Intune-konfigurationshanteraren väljer **du Läs mer.**
3. Välj **Spara.**

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Sidan Organisationsinställningar där du kan avanmäla dig från användarupplevelser.":::
