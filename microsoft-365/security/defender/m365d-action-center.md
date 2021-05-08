---
title: Gå till Åtgärdscenter för att visa och godkänna dina uppgifter för automatisk undersökning och åtgärder
description: Använda Åtgärdscenter för att visa information om automatisk undersökning och godkänna väntande åtgärder
keywords: Åtgärdscenter, skydd mot hot, undersökning, avisering, väntande, automatiserad, identifiering
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7bea9a1632e7a9ed9d394c2c411123d0601a9397
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274586"
---
# <a name="the-action-center"></a>Åtgärdscentret

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Åtgärdscenter ger en "enda fönsterruta" för incidenter och aviseringsuppgifter som:

- Godkänna väntande åtgärder.
- Visa en granskningslogg över redan godkända åtgärdsåtgärder.
- Granska slutförda åtgärder.

Eftersom Åtgärdscenter ger en omfattande vy av Microsoft 365 Defender på jobbet, kan ditt säkerhetsåtgärdsteam arbeta effektivare.

## <a name="the-unified-action-center"></a>Det enhetliga åtgärdscentret

I det enhetliga åtgärdscentret () visas väntande och slutförda åtgärdsåtgärder för dina enheter, e-& och samarbetsinnehåll och [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) identiteter på en plats.

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Enhetligt åtgärdscenter i Microsoft 365 Defender":::

Till exempel: 

- Om du tidigare har använt Säkerhets- och efterlevnadscenter för Office 365 & ( ) kan du prova det enhetliga åtgärdscentret i [https://protection.office.com](https://protection.office.com) Microsoft 365 säkerhetscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Om du använder Åtgärdscenter i Microsoft Defender Säkerhetscenter () kan du prova det enhetliga åtgärdscentret i Säkerhetscenter för [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) Microsoft 365 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ().
- Om du redan använder Microsoft 365 Säkerhetscenter ( ) ser du [https://security.microsoft.com](https://security.microsoft.com) flera förbättringar i Åtgärdscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).

I det enhetliga åtgärdscentret samlas åtgärdsåtgärder i Defender för Endpoint och Defender för Office 365. Den definierar ett gemensamt språk för alla åtgärder och ger en enhetlig undersökningsupplevelse. Ditt säkerhetsteam har en "enda fönsterruta av glas" för att visa och hantera åtgärder.  

Du kan använda det enhetliga åtgärdscentret om du har rätt behörigheter och en eller flera av följande prenumerationer:

- [Defender för Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> Mer information finns i [Krav](./prerequisites.md).

## <a name="using-the-action-center"></a>Använda Åtgärdscenter

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 
2. Välj Åtgärdscenter i **navigeringsfönstret.** 

När du besöker Åtgärdscenter visas två flikar: **Väntande åtgärder** och **Historik.** I följande tabell sammanfattas det du ser på varje flik:

|Tabb  |Beskrivning  |
|---------|---------|
|**Väntande**     | Visar en lista över åtgärder som kräver uppmärksamhet. Du kan godkänna eller avvisa åtgärder en i taget eller markera flera åtgärder om de har samma typ av åtgärd (till exempel karantänfil). <p>**TIPS:** Se till att granska och godkänna (eller avvisa) väntande åtgärder så snart som möjligt så att automatiserade undersökningar kan slutföras i tid.       |
|**Historik**     | Fungerar som en granskningslogg för åtgärder som har vidtagits, till exempel: <br/>- Åtgärdsåtgärder som har vidtagits genom automatiska undersökningar <br/>– Åtgärdsåtgärder som har vidtas på misstänkta eller skadliga e-postmeddelanden, filer eller URL-adresser<br/>- Åtgärdsåtgärder som har godkänts av teamet för säkerhetsåtgärder <br/>- Kommandon som körts och åtgärdsåtgärder som tillämpats under Live Response-sessioner<br/>- Åtgärdsåtgärder som har vidtagits av ditt antivirusprogram <p>Gör det enkelt att ångra vissa åtgärder (se [Ångra slutförda åtgärder).](m365d-autoir-actions.md#undo-completed-actions)        |

Du kan anpassa, sortera, filtrera och exportera data i Åtgärdscenter.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="Med Åtgärdscenter kan du sortera, filtrera och anpassa listan med åtgärder":::

- Välj en kolumnrubrik om du vill sortera posterna i stigande eller fallande ordning.
- Använd filtret för tidsperiod för att visa data för den senaste dagen, veckan, 30 dagar eller 6 månader.
- Välj de kolumner som du vill visa.
- Ange hur många objekt som ska ingå på varje sida med data.
- Använd filter för att visa endast de objekt som du vill se.
- Välj **Exportera** om du vill exportera resultaten till en .csv fil.

## <a name="actions-tracked-in-the-action-center"></a>Åtgärder spårade i Åtgärdscenter

Alla åtgärder, oavsett om de väntar på godkännande eller redan har vidtagit, spåras i Åtgärdscenter. Bland de tillgängliga åtgärderna finns följande:

- Samla in undersökningspaket 
- Isolera enhet (den här åtgärden kan ångras) 
- Avregistrera maskin 
- Körning av släppkod 
- Släpp från karantän 
- Exempel på förfrågan 
- Begränsa körning av kod (den här åtgärden kan ångras) 
- Kör antivirusgenomsökning 
- Stoppa och sätta i karantän 

Förutom åtgärder som vidtas automatiskt som ett resultat [](m365d-autoir.md)av automatiska undersökningar följer åtgärdscentret även åtgärder som säkerhetsgruppen har vidtagit för att hantera identifierade hot och åtgärder som har vidtagits som ett resultat av skyddsfunktioner för hot i Microsoft 365 Defender. Mer information om automatiska och manuella åtgärdsåtgärder finns [i Åtgärder.](m365d-remediation-actions.md)

## <a name="viewing-action-source-details"></a>Visa information om åtgärdskälla

(**NYTT!**) Det förbättrade åtgärdscentret innehåller nu kolumnen **Åtgärdskälla** som visar var varje åtgärd kom från. I följande tabell beskrivs möjliga värden **i åtgärdskällor:**

| Värdet för åtgärdskälla | Beskrivning |
|:-----|:---|
| **Manuell enhetsåtgärd** | En manuell åtgärd som vidtas på en enhet. Exempel är [enhetsisolering eller](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) [karantänen för filer.](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files) |
| **Manuell e-poståtgärd** | En manuell åtgärd för e-post. Ett exempel omfattar mjuk borttagning av e-postmeddelanden [eller åtgärdar ett e-postmeddelande.](../office-365-security/remediate-malicious-email-delivered-office-365.md) |
| **Automatiserad enhetsåtgärd** | En automatiserad åtgärd som vidtas på en enhet, till exempel en fil eller en process. Exempel på automatiserade åtgärder är att skicka en fil till karantän, stoppa en process och ta bort en registernyckel. (Se [Åtgärder för åtgärder i Microsoft Defender för Slutpunkt](../defender-endpoint/manage-auto-investigation.md#remediation-actions).) |
| **Automatiserad e-poståtgärd** | En automatiserad åtgärd för e-postinnehåll, till exempel ett e-postmeddelande, en bifogad fil eller en URL. Exempel på automatiserade åtgärder är mjuk borttagning av e-postmeddelanden, blockering av URL-adresser och inaktiverar vidarebefordran av extern e-post. (Se [Åtgärder för åtgärder i Microsoft Defender för Office 365](../office-365-security/air-remediation-actions.md).) |
| **Avancerad sökåtgärd** | Åtgärder som vidtas på enheter eller e-post [med avancerad sökning](./advanced-hunting-overview.md). |
| **Åtgärden Utforskaren** | Åtgärder som vidtas på e-postinnehåll med [Utforskaren](../office-365-security/threat-explorer.md). |
| **Manuell svarsåtgärd** | Åtgärder som vidtas på en enhet med [live-svar](../defender-endpoint/live-response.md). Några exempel är att ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet. |
| **Live response-åtgärd** | Åtgärder som vidtas på en enhet med [Microsoft Defender för slutpunktS-API:er](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis). Exempel på åtgärder är att isolera en enhet, köra en antivirussökning och hämta information om en fil. |

## <a name="required-permissions-for-action-center-tasks"></a>Behörighet som krävs för uppgifter i Åtgärdscenter

Om du vill utföra uppgifter, till exempel godkänna eller avvisa väntande åtgärder i Åtgärdscenter, måste du ha tilldelats behörigheter enligt följande tabell:

|Åtgärdsåtgärd |Roller och behörigheter som krävs |
|--|----|
|Microsoft Defender för åtgärd av slutpunkt (enheter) |**Säkerhetsadministratörsroll** som tilldelats i antingen Azure Active Directory (Azure AD) ( ) eller administrationscentret för [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- eller ---<br/>**Rollen Aktiva åtgärdsåtgärder som** tilldelats i Microsoft Defender för Slutpunkt <br/> <br/> Mer information finns i följande resurser: <br/>- [Administratörsrollbehörigheter i Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Skapa och hantera roller för rollbaserad åtkomstkontroll (Microsoft Defender för slutpunkt)](../defender-endpoint/user-roles.md)  |
|Åtgärder i Microsoft Defender för Office 365 (Office-innehåll och e-post)  |**Säkerhetsadministratörsroll** som har tilldelats i antingen Azure AD ( [https://portal.azure.com](https://portal.azure.com) ) eller administrationscentret för Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- och --- <br/>**Rollen Sök och rensning** i Säkerhets- och & [https://protection.office.com](https://protection.office.com) () <br/><br/>**VIKTIGT:** Om du  bara har tilldelats rollen Säkerhetsadministratör i Efterlevnadscenter för Office 365 & ( ) kan du inte komma åt åtgärdscenter eller [https://protection.office.com](https://protection.office.com) Microsoft 365 Defender-funktioner. Du måste ha rollen **Säkerhetsadministratör** tilldelad i Azure AD eller administrationscentret för Microsoft 365. <br/><br/>Mer information finns i följande resurser: <br/>- [Administratörsrollbehörigheter i Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Behörigheter i Säkerhets- & Säkerhets- och efterlevnadscenter](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Användare som har rollen **Global administratör** tilldelad i Azure AD kan godkänna eller avvisa eventuella väntande åtgärder i Åtgärdscenter. Men det bästa är att organisationen bör begränsa antalet personer som har tilldelats **rollen global** administratör. Vi rekommenderar att du **använder rollerna**  **Säkerhetsadministratör,** Aktiva åtgärder och Sök och rensning som visas i föregående tabell för behörigheter i Åtgärdscenter.

## <a name="next-step"></a>Nästa steg 

- [Visa och hantera åtgärdsåtgärder](m365d-autoir-actions.md)
