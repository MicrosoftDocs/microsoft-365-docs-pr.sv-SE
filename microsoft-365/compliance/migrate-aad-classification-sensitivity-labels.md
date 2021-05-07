---
title: Azure Active Directory klassificerings- och känslighetsetiketter för Microsoft 365 grupper
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: I den här artikeln beskrivs Azure Active Directory för klassificering och känslighetsetiketter.
ms.openlocfilehash: 07bc09afb3e490961a8cc5a88857ec49dd962856
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162460"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Azure Active Directory klassificerings- och känslighetsetiketter för Microsoft 365 grupper

I den här artikeln beskrivs Azure Active Directory för klassificering och känslighetsetiketter.

Känslighetsetiketter stöds av [dessa tjänster.](./sensitivity-labels-teams-groups-sites.md)

Fullständig information om känslighetsetiketter finns i [Läs mer om känslighetsetiketter.](sensitivity-labels.md)

Mer information om känslighetsetiketter och deras beteende för webbplatser och Microsoft 365-grupper finns i Använda känslighetsetiketter för att skydda innehåll i [Microsoft Teams, Microsoft 365 grupper](sensitivity-labels-teams-groups-sites.md)och SharePoint webbplatser.

Se följande scenarier för metodtips när du migrerar från klassisk AAD-klassificering till känslighetsetiketter.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Scenario 1: Klientorganisationen använde aldrig klassiska AAD-klassificeringar eller känslighetsetiketter för dokument och e-postmeddelanden

- Innehavaradministratören aktiverar känslighetsetiketter för grupper genom att ange "EnableMIPLabels" (aktiveraMIPLabels) till True via AAD powershell-cmdleten.
- Innehavaradministratören skapar känslighetsetiketter i [Microsoft 365 kompatibilitetscenter.](https://compliance.microsoft.com)
    - Innehavaradministratören kan välja fil- och e-postrelaterade åtgärder som kryptering och vattenstämplar.
    - Innehavaradministratören kan välja Microsoft 365 grupper och SharePoint webbplatsrelaterade åtgärder för onlinewebbplatsrelaterade åtgärder för känslighetsetiketterna.
- Innehavaradministratören publicerar principen.
- **Kompatibla arbetsbelastningar** visar känslighetsetiketter. Använd känslighetsetiketter för att skapa grupper. Kompatibla arbetsbelastningar är de tjänster som stöder känslighetsetiketter.
- **Icke-kompatibla arbetsbelastningar** är de tjänster som ännu inte stöder känslighetsetiketter. Det går dock att skapa grupper som inte associeras med känslighetsetiketten via icke-kompatibla arbetsbelastningar. Om du vill associera sådana grupper med känslighetsetiketter kan innehavaradministratörer köra PowerShell-cmdlets.

Tabell 1. Beteende för kompatibla och icke-kompatibla arbetsbelastningar – skapa, redigera eller ta bort grupper

|Arbetsbelastning|Vilken etikettlista visas i gruppfönstret?|Skapa ny grupp |Redigera grupp |Ta bort grupp |
|:-------|:-------|:--------|:--------|:--------|   
|Kompatibel   |känslighetsetiketter. |Inga ändringar i beteendet. |Inga ändringar i beteendet. |Inga ändringar i beteendet. |
|Icke-kompatibel |Inga känslighetsetiketter visas. |Användaren kan skapa en grupp utan att markera känslighetsetikett. <br><br> Observera att administratören kan köra cmdlets för att använda känslighetsetiketter i bakgrunden. |**Case 1**: No sensitivity label previously selected. Användaren kan redigera en grupp.<br><br> **Case 2:** sensitivity label applied previously in the background using cmdlet. Användaren kan redigera en grupp utan att det är fallet där användaren väljer en ogiltig kombination av sekretessinställningar för etiketten. |Inga ändringar i beteendet.|

> [!NOTE]
> När administratören aktiverar känslighetsetiketter för Outlook-skrivbordsklienten (Win 32) och användaren använder en äldre version av Outlook-skrivbordsklienten (Win 32):
>
> - Användaren ser känslighetsetiketter visas på den äldre versionen av Outlook datorklienten.
> - Men när användaren redigerar en grupp och sparar gruppen med en känslighetsetikett åsidosätts den valda sekretessinställningen av sekretessinställningen för den tillämpade känslighetsetiketten.
>
> Vi rekommenderar att användarna med en gammal version av Outlook uppgraderar till den nyare versionen.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Scenario 2: Klientorganisationen använder redan klassiska [AAD-klassificeringar](../enterprise/manage-microsoft-365-groups-with-powershell.md)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Case A: Tenant never used sensitivity labels for documents and email

1. I Microsoft 365 [rekommenderar vi att](https://compliance.microsoft.com)du skapar känslighetsetiketter med samma namn som de befintliga klassiska Azure AD-etiketterna.
2. Använd PowerShell-cmdleten för att använda dessa känslighetsetiketter på befintliga Microsoft 365 och webbplatser SharePoint med namnmappning.
3. Administratören kan välja att ta bort de klassiska Azure AD-etiketterna:
    - Kompatibla arbetsbelastningar visar känslighetsetiketter och grupper skapas med dem.
    - Icke-kompatibla arbetsbelastningar fungerar när grupper skapas, men ingen känslighetsetikett är kopplad till dem.
4. Administratörer kan köra PowerShell-cmdlets för att använda känslighetsetiketter i de här grupperna utan etiketter.
    - En administratör kan också välja att behålla de klassiska Azure AD-etiketterna:
        - Kompatibla arbetsbelastningar visar känslighetsetiketter och grupper skapas med dem. Kompatibla arbetsbelastningar är de tjänster som stöder känslighetsetiketter.
        - Icke-kompatibla arbetsbelastningar fungerar när du skapar grupper och visar klassiska Azure AD-etiketter. De här klassiska Azure AD-etiketterna kopplas till dessa grupper som skapats med icke-kompatibla arbetsbelastningar.
5. Vi rekommenderar att administratörer kör PowerShell-cmdlets för att tillämpa känslighetsetiketter på de här grupperna med klassiska Azure AD-etiketter.

Tabell 2. Beteende för kompatibla och icke-kompatibla arbetsbelastningar – skapa, redigera eller ta bort grupper

|Arbetsbelastning|Vilken etikettlista visas i gruppfönstret?|Skapa ny grupp |Redigera grupp |Ta bort grupp |
|:-------|:-------|:--------|:--------|:--------|   
|Kompatibel   |känslighetsetiketter. |Inga ändringar i beteendet. |Inga ändringar i beteendet. |Inga ändringar i beteendet. |
|Icke-kompatibel |Gamla klassiska AAD-etiketter. |Användaren kan skapa en grupp med den klassiska Azure AD-etiketten markerad. <br><br>Observera att administratören kan köra cmdlets för att använda känslighetsetiketter i bakgrunden. |**Case 1**: No sensitivity label previously selected. Användaren kan redigera en grupp.<br><br> **Case 2:** Classic AAD labels previously selected. Användaren kan redigera en grupp.<br><br> **Case 3:** sensitivity label previously applied in the background using cmdlet. Användaren ska kunna redigera en grupp, förutom ett fall där användaren väljer en ogiltig kombination av sekretessinställningar för etiketten. |Användaren kan ta bort en grupp. |

> [!NOTE]
> När administratören aktiverar känslighetsetiketter för Outlook-skrivbordsklienten (Win 32) och användaren använder en äldre version av Outlook-skrivbordsklienten (Win 32):
>
> - Användaren ser känslighetsetiketter visas på den äldre versionen av Outlook datorklienten.
> - Men när användaren redigerar en grupp och sparar gruppen med en känslighetsetikett åsidosätts den valda sekretessinställningen av sekretessinställningen för den tillämpade känslighetsetiketten.
>
> Vi rekommenderar att användarna med en gammal version av Outlook uppgraderar till den nyare versionen.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Case B: Klientorganisationen använde känslighetsetiketter för dokument och e-postmeddelanden

1. När administratören aktiverar känslighetsetikett-funktionen på klientorganisationen genom att ställa in klientflaggan EnableMIPLabels till True visas känslighetsetiketter för dokument och e-post i dialogrutorna för att skapa och redigera grupp/webbplats/grupp.
2. En administratör kan använda samma känslighetsetiketter för dokument och e-post för att tillämpa sekretess och extern användaråtkomst på gruppen/webbplatsen/gruppen genom att ange relaterade gruppinställningar:
    1. I Microsoft 365 [väljer](https://compliance.microsoft.com)du fliken **Webbplatser och** grupper.
    2. Redigera ett dokument eller en känslighetsetikett för e-post.

## <a name="sample-script"></a>Exempelskript

Ett exempelskript för att migrera grupper med klassiska AAD-etiketter till känslighetsetiketter finns i [Klassisk Azure AD-gruppklassificering.](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification)