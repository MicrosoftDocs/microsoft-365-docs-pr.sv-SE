---
title: Gå till åtgärdscenter om du vill visa och godkänna en automatiserad undersökning och åtgärder
description: Använda Åtgärdscenter för att visa information om automatisk undersökning och godkänna väntande åtgärder
keywords: Åtgärdscenter, skydd mot hot, undersökning, avisering, väntande, automatiserad, identifiering
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 45e02e4ce7d5d813cc8215a1f27ed9c415707cb1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930432"
---
# <a name="the-action-center"></a>Åtgärdscentret

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Använd Åtgärdscenter ( ) för att se resultaten från aktuella och tidigare undersökningar [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) över organisationens enheter och postlådor. Beroende på typen av hot och resulterande bedömning [kan](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) åtgärder vidtas automatiskt eller vid godkännande av organisationens säkerhetsteam. Alla åtgärder, oavsett om de väntar på godkännande eller redan har godkänts, konsolideras i Åtgärdscenter. 

![Åtgärdscenter](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>En "enda fönsterruta"

Åtgärdscenter ger en "enda fönsterruta" för aktiviteter, till exempel:
- Godkänna väntande åtgärder
- Visa en granskningslogg över redan godkända åtgärdsåtgärder. och
- Granska slutförda åtgärder.

Ditt säkerhetsteam kan arbeta effektivare och effektivare eftersom åtgärdscentret ger en omfattande vy av Microsoft 365 Defender på jobbet.

## <a name="go-to-the-action-center"></a>Gå till Åtgärdscenter

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. Välj Åtgärdscenter i **navigeringsfönstret.** 

3. I Åtgärdscenter visas två flikar: **Väntande** och **Historik.**

    - På **fliken Väntande** listor finns undersökningar som kräver granskning och godkännande av någon i din säkerhetsgrupp för att fortsätta. Granska och vidta åtgärder för väntande objekt som visas här.

    - På **fliken** Historik visas tidigare undersökningar och åtgärder som har vidtagits automatiskt. Du kan visa data för den senaste dagen, veckan, månaden eller sex månaderna.

4. Om du bara vill visa de kolumner du vill se väljer du **Anpassa kolumner.**<br/>![Åtgärdscenter i Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Välj ett objekt i listan om du vill visa mer information om en undersökning. Vyn med undersökningsinformation öppnas.<br/>![Undersökningsinformation](../../media/mtp-air-investdetails.png)

    - Om undersökningen gäller e-postinnehåll (t.ex. om entiteten är en postlåda), öppnas undersökningsinformation i säkerhets- & Center för efterlevnad [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) (). 

    - Om undersökningen involverar en enhet öppnas undersökningsinformation i säkerhetscentret [https://security.microsoft.com](https://security.microsoft.com) (). 

> [!TIP]
> Om du tror att något har missats eller identifierats felaktigt av en automatiserad undersökning och svarsfunktioner i Microsoft 365 Defender, berätta det för oss! Se hur du rapporterar falska positiva eller negativa resultat i automatisk undersökning och [svarsfunktioner (AIR) i Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

## <a name="available-actions"></a>Tillgängliga åtgärder

När åtgärder vidtas visas de på fliken **Historik** i Åtgärdscenter. Sådana åtgärder omfattar följande:

- Samla in undersökningspaket 
- Isolera enhet (den här åtgärden kan ångras) 
- Offboard-dator 
- Körning av släppkod 
- Släpp från karantän 
- Exempel på förfrågan 
- Begränsa körning av kod (den här åtgärden kan ångras) 
- Kör antivirussökning 
- Stoppa och sätta i karantän 

> [!NOTE]
> Förutom åtgärder som vidtas automatiskt kan teamet för säkerhetsåtgärder vidta manuella åtgärder för att hantera identifierade hot. Mer information om automatiska och manuella åtgärder finns [i Åtgärder.](mtp-remediation-actions.md)

## <a name="action-source"></a>Åtgärdskälla

(**NYHET!**) Som du vet samlar Microsoft 365 Defender automatisk undersökning och svarsfunktioner i flera tjänster, till exempel [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Slutpunkt och Microsoft Defender för [Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Det nya och förbättrade åtgärdscentret innehåller nu **kolumnen Åtgärdskälla** som visar var varje åtgärdsåtgärd kom. 

I följande tabell beskrivs möjliga värden **för åtgärdskällor:**

| Värdet för åtgärdskälla | Beskrivning |
|:-----|:---|
| **Åtgärd för manuell enhet** | En manuell åtgärd som vidtas på en enhet. Några exempel är [enhetsisolering eller](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) [karantän för filer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **Manuell e-poståtgärd** | En manuell åtgärd för e-post. Ett exempel omfattar mjuk borttagning av e-postmeddelanden [eller åtgärdar ett e-postmeddelande.](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365) |
| **Automatiserad enhetsåtgärd** | En automatiserad åtgärd som vidtas på en enhet, till exempel en fil eller en process. Exempel på automatiserade åtgärder är att skicka en fil till karantän, stoppa en process och ta bort en registernyckel. (Se [åtgärder för åtgärder i Microsoft Defender för slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions).) |
| **Automatiserad e-poståtgärd** | En automatiserad åtgärd för e-postinnehåll, till exempel ett e-postmeddelande, en bifogad fil eller en URL. Exempel på automatiserade åtgärder är mjuk borttagning av e-postmeddelanden, blockering av URL:er och inaktiverar vidarebefordran av extern e-post. (Se [åtgärder för åtgärder i Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions).) |
| **Avancerad sökåtgärd** | Åtgärder som vidtas på enheter eller e-post [med avancerad sökning.](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview) |
| **Explorer-åtgärd** | Åtgärder som vidtas på e-postinnehåll med [Utforskaren.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) |
| **Manuell svarsåtgärd** | Åtgärder som vidtas på en enhet med [live-svar.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) Några exempel är att ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet. |
| **Live response-åtgärd** | Åtgärder som vidtas på en enhet med [Microsoft Defender för slutpunkts-API:er.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) Exempel på åtgärder är att isolera en enhet, köra en antivirussökning och hämta information om en fil. |

## <a name="required-permissions-for-action-center-tasks"></a>Behörigheter som krävs för uppgifter i Åtgärdscenter

Om du vill godkänna eller avvisa väntande åtgärder i Åtgärdscenter måste du ha de behörigheter som anges i följande tabell:

|Åtgärdsåtgärd |Obligatoriska roller och behörigheter |
|--|----|
|Åtgärd för Microsoft Defender för slutpunkt (enheter) |Säkerhetsadministratörsroll som tilldelats i antingen Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) eller Administrationscenter för Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- eller ---<br/>Rollen Aktiva åtgärdsåtgärder tilldelad i Microsoft Defender för Slutpunkt <br/> <br/> Mer information finns i följande resurser: <br/>- [Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Skapa och hantera roller för rollbaserad åtkomstkontroll (Microsoft Defender för slutpunkt)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Åtgärd för Microsoft Defender för Office 365 (Office-innehåll och e-post)  |Säkerhetsadministratörsroll som tilldelats i antingen Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) eller Administrationscenter för Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- och --- <br/>Rollen Sök och rensning har tilldelats Säkerhets- & Efterlevnadscenter [https://protection.office.com](https://protection.office.com) () <br/><br/>**VIKTIGT:** Om du bara har tilldelats rollen säkerhetsadministratör i Säkerhets- & och efterlevnadscenter kan du inte komma åt funktionerna i Åtgärdscenter eller Microsoft 365 Defender. Du måste ha rollen Säkerhetsadministratör tilldelad i Azure Active Directory eller administrationscentret för Microsoft 365. <br/><br/>Mer information finns i följande resurser: <br/>- [Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Behörigheter i Säkerhets- & Efterlevnadscenter](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Användare som har rollen Global administratör tilldelad i Azure Active Directory kan godkänna eller avvisa eventuella väntande åtgärder i Åtgärdscenter. En god metod är dock att organisationen bör begränsa antalet personer som har tilldelats rollen global administratör. Vi rekommenderar att du använder säkerhetsadministratören, aktiva åtgärdsåtgärder och sök- och rensningsroller som anges ovan för behörigheter i Åtgärdscenter.

## <a name="next-steps"></a>Nästa steg 

- [Godkänna eller avvisa väntande åtgärder efter en automatiserad undersökning](mtp-autoir-actions.md)
- [Visa resultatet av en automatiserad undersökning](mtp-autoir-results.md)

