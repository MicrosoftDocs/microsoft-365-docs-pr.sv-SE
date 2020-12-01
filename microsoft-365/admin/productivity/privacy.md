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
ms.openlocfilehash: c88886e9d1470bda48d023b77472e7dd296508a0
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519359"
---
# <a name="privacy-controls-for-productivity-score"></a>Integritets inställningar för produktivitets Poäng

Produktivitets Poäng hjälper organisationer att omvandla hur arbete görs med mät värden som hjälper dig att utvärdera och förbättra folk-och teknik upplevelsen. Det hjälper dig att få en överblick över hur organisationen fungerar och ger dig de mått som hjälper dig att fokusera på att aktivera förbättrade funktioner.  Du kan också ansluta måtten till åtgärder för att hjälpa dig att uppdatera färdigheter och system så att alla kan göra sitt bästa arbete. Poängen återspeglar organisationens prestanda och gör det också möjligt för dig att på ett säkert sätt jämföra poängen med andra organisationer som du själv.  Mer information finns i [Översikt över produktivitets Poäng](productivity-score.md).

Din integritet är viktig för oss. Information om hur vi skyddar din integritet finns i [Microsofts sekretess policy](https://privacy.microsoft.com/privacystatement). Produktivitets poäng ger viktig information om hur personer i din organisation samarbetar tillsammans med kontroller för att kontrol lera att informationen är åtgärdad utan att det bevaras i Microsoft.

I området personer kan du använda mått på organisations nivå och ta med alla användare i din Microsoft 365-klient. Det här området visar hur personer använder Microsoft 365 genom att titta på kategorier av innehålls samarbete, mobilitet, möten, samarbete och kommunikation. För att hjälpa dig att öka utbildning och medvetenhet till rätt uppsättning personer som kan behöva support med våra produkter finns det också information på individuell nivå. Även om vi tillhandahåller den här genomskinlighets nivån kan vi också göra det möjligt för dig att möta dina interna integritets policy behov.
Följande kontroller ger dig:

- Flexibla administratörs roller för att kontrol lera vem som kan se informationen i produktivitets poängen.
- Möjlighet att identifiera mått på användar nivå.
- Möjlighet att avanmäla folk upplevelsen.
- Möjligheten att välja bort området personer

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibla administratörs roller för att styra vem som kan se informationen i produktivitets poängen

För att visa hela produktivitets poängen, inklusive uppgifter om klient organisations nivå och per användare, bör din roll vara en av följande administratörs roller:

- Global administratör
- Exchange-administratörer
- SharePoint-administratör
- Skype för företag-administratör
- Teams-administratör
- Global läsare
- Rapport läsare

Koppla rollen rapport läsare till vem som är ansvarig för ändrings hantering och antagande. Den här rollen ger dem till gång till den fullständiga upplevelsen, inklusive nivå mått för klient nivå och uppgifter per användare.

Rapporten personer upplever innehåller aktivitets information per användare för varje kategori detalj sida. Skapa en anpassad roll som kallas användnings översikt rapporter (som är tillgänglig från och med början 29 oktober 2020) för att tillåta åtkomst till personernas samlade mått. Den här rollen måste tilldelas genom PowerShell-cmdletar tills den blir tillgänglig från Microsoft Admin Center senare det här året.

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

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Sidan kommunikation i produktivitets rapporterna.":::

## <a name="de-identification-of-user-level-metrics"></a>Identifiering av mått på användar nivå

Du måste vara global administratör för att data ska samlas in för anonyma rapporter. Den här åtgärden kommer att dölja identifierbar information som användare, grupper och webbplats namn i alla rapporter – inklusive produktivitets Poäng och Microsoft 365-användning.

1. Gå till **Inställningar** i administrations centret   >   **Org Settings** och välj **rapporter** på fliken **tjänster** .
2. Välj  **rapporter** och välj sedan att  **Visa anonyma identifierare för användare, grupper och webbplats namn i produktivitets-och användnings rapporter**. Den här inställningen tillämpas både på användnings rapporterna och i programmet.
3. Välj  **Spara ändringar**.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Gör användar informationen anonym för rapporter.":::

## <a name="capability-to-opt-out-of-people-experiences"></a>Möjlighet att avanmäla folk upplevelsen

När produktivitets poängen är allmänt tillgänglig kan du även välja att gå ur området personer med produktivitets poäng. Om du avmarkerar kan ingen från organisationen Visa dessa mått och din organisation tas bort från alla beräkningar som berör kommunikation, möten, samarbete, innehålls samarbete och mobilitet.

1. Gå till **Inställningar** i administrations centret   >   **Org Settings** och välj **rapporter** på fliken **tjänster** .
2. Välj  **rapporter** och avmarkera sedan kryss rutan  **för att tillåta att Microsoft 365-användnings data används för folk upplevelsen**. Om du vill förstå hur du ändrar inställningar för data delning för slut punkts analys i Intune Configuration Manager klickar du på **Mer information**.
3. Välj  **Spara ändringar**.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Sidan organisations inställningar där du kan välja bort från folk upplevelsen.":::