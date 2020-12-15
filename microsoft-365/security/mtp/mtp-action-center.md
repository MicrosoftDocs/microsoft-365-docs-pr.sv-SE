---
title: Gå till åtgärds centret för att visa och godkänna den automatiska undersökningen och reparations uppgifter
description: Använd åtgärds centret för att visa information om automatiserad undersökning och godkännande av väntande åtgärder
keywords: Åtgärds Center, Hot skydd, undersökning, avisering, pågående, automatisk, identifiering
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: aa9f433bc60949aa625d9346421b025121347a2c
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683325"
---
# <a name="the-action-center"></a>Åtgärdscentret

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Använd åtgärds Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) för att visa resultaten av aktuella och tidigare undersökningar i organisationens enheter och post lådor. Beroende på vilken typ av hot och resulterande Verdict kan [reparations åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) ske automatiskt eller vid godkännande av organisationens säkerhets åtgärds team. Alla reparations åtgärder, oavsett om de väntar på godkännande eller redan har godkänts, konsol IDE ras i åtgärds centret. 

![Åtgärds Center](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>En enda glas panel

I åtgärds centret finns ett "fönster ruta med glas"-funktioner för uppgifter, till exempel:
- Godkännande av väntande reparations åtgärder;
- Visa en Gransknings logg med redan godkända reparations åtgärder; och
- Granska slutförda reparations åtgärder.

Din säkerhets åtgärd kan fungera effektivare och effektivt eftersom åtgärds Center ger en omfattande översikt över Microsoft 365 Defender på jobbet.

## <a name="go-to-the-action-center"></a>Gå till åtgärds Center

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. I navigerings fönstret väljer du **Åtgärds Center**. 

3. I åtgärds Center visas två flikar: **förestående** och **Historik**.

    - På fliken **förestående** visas de undersökningar som kräver granskning och godkännande av någon i din team för säkerhets åtgärder för att fortsätta. Se till att granska och vidta åtgärder för pågående objekt som du ser här.

    - På fliken **Historik** visas tidigare undersökningar och reparations åtgärder som har gjorts automatiskt. Du kan visa data för föregående dag, vecka, månad eller sex månader.

4. Om du bara vill visa de kolumner som du vill visa väljer du **Anpassa kolumner**.<br/>![Åtgärds Center i Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Välj ett objekt i listan för att visa mer information om en undersökning. Vyn granska detaljer öppnas.<br/>![Gransknings uppgifter](../../media/mtp-air-investdetails.png)

    - Om undersökningen gäller för e-postinnehåll (till exempel att enheten är en post låda) öppnas undersöknings information i säkerhets & Compliance Center ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Om undersökningen handlar om en enhet kan du gå till undersöknings informationen i säkerhets Center ( [https://security.microsoft.com](https://security.microsoft.com) ). 

> [!TIP]
> Om du tror att något har missats eller upptäckts felaktigt av automatiserade undersökningar och svars funktioner i Microsoft 365 Defender kan du tala om det för oss! Lär dig [hur du rapporterar falskta positiva eller negativa negativ i en automatiserad undersökning och svar (Air) i Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).

## <a name="available-actions"></a>Tillgängliga åtgärder

Eftersom reparations åtgärder vidtas visas de på fliken **Historik** i åtgärds centret. Det här är bland annat följande:

- Samla in undersöknings paket 
- Isolera enhet (den här åtgärden kan ångras) 
- Ta bort dator 
- Utgivning av kod körning 
- Släpp från karantän 
- Exempel på begäran 
- Begränsa kod körning (denna åtgärd kan ångras) 
- Kör antivirus-genomsökning 
- Stoppa och karantän 

> [!NOTE]
> Förutom reparations åtgärder som vidtas automatiskt kan säkerhets åtgärds gruppen vidta manuella åtgärder för att åtgärda upptäckta hot. Mer information om automatiska och manuella reparations åtgärder finns i [reparations åtgärder](mtp-remediation-actions.md).

## <a name="action-source"></a>Åtgärds källa

(**Ny!**) Som du vet samlar Microsoft 365 Defender samman automatiserade undersökningar och svars funktioner i flera tjänster, till exempel [Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) och [Microsoft defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). Det nya och förbättrade åtgärds centret innehåller nu en kolumn i en **Åtgärds källa** som visar var varje åtgärd för reparation kom ifrån. 

I följande tabell beskrivs möjliga **käll** värden för åtgärder:

| Källans värde | Beskrivning |
|:-----|:---|
| **Manuell enhets åtgärd** | En manuell åtgärd som utförs på en enhet. Exemplen inkluderar [enhets isolering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) eller [fil karantän](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files). |
| **Manuell e-poståtgärd** | En manuell åtgärd som utförs via e-post. Ett exempel inkluderar mjuk borttagning av e-postmeddelanden eller [åtgärdar ett e-postmeddelande](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365). |
| **Automatisk enhets åtgärd** | En automatiserad åtgärd som utförs på en enhet, till exempel en fil eller process. Exempel på automatiska åtgärder är att skicka en fil till karantän, stoppa en process och ta bort en register nyckel. (Se [reparations åtgärder i Microsoft Defender för slut punkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions).) |
| **Automatisk e-poståtgärd** | En automatiserad åtgärd som utförs via e-post, till exempel ett e-postmeddelande, en bifogad fil eller en URL. Exempel på automatiska åtgärder är att ta bort e-postmeddelanden, blockera URL-adresser och stänga av extern e-postvidarekoppling. (Se [reparations åtgärder i Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions).) |
| **Avancerad jakt åtgärd** | Åtgärder som utförs på enheter eller e-post med [Avancerad jakt](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview). |
| **Explorer-åtgärd** | Åtgärder som vidtas för e-postinnehåll med [Utforskaren](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer). |
| **Manuell Live-responstid** | Åtgärder som utförs på en enhet med [Live respons](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response). Exempel: ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet. |
| **Live Response-åtgärd** | Åtgärder som utförs på en enhet med [Microsoft Defender för slut punkts-API: er](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis). Exempel på åtgärder är att isolera en enhet, köra en Antivirus sökning och få information om en fil. |

## <a name="required-permissions-for-action-center-tasks"></a>Nödvändiga behörigheter för åtgärds Center-uppgifter

För att godkänna eller avvisa väntande åtgärder i åtgärds centret måste du ha behörighet som tilldelats enligt följande tabell:

|Reparations åtgärd |Nödvändiga roller och behörigheter |
|--|----|
|Microsoft Defender för slut punkts reparation (enheter) |Säkerhets administratörs rollen tilldelad i antingen Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) eller Microsoft 365 Admin Center ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>---eller---<br/>Rollen aktiva åtgärds åtgärder som tilldelats i Microsoft Defender för slut punkten <br/> <br/> Mer information finns i följande resurser: <br/>- [Administratörs behörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Skapa och hantera roller för rollbaserad åtkomst kontroll (Microsoft Defender för slut punkt)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Microsoft Defender för Office 365-reparation (Office-innehåll och e-postadress)  |Säkerhets administratörs rollen tilldelad i antingen Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) eller Microsoft 365 Admin Center ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>---och--- <br/>Roll för Sök och rensa som tilldelats säkerhets & kompatibilitetskontrollen ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**Viktigt**! om du har rollen som säkerhets administratör tilldelad i säkerhets & Compliance Center kan du inte komma åt åtgärds centret eller Microsoft 365 Defender-funktionerna. Du måste ha rollen som säkerhets administratör tilldelad i Azure Active Directory eller i administrations centret för Microsoft 365. <br/><br/>Mer information finns i följande resurser: <br/>- [Administratörs behörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Behörigheter i Center för säkerhets &](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Användare som har rollen global administratör tilldelat i Azure Active Directory kan godkänna eller avvisa eventuella pågående åtgärder i åtgärds centret. Av säkerhets skäl bör din organisation begränsa antalet personer som har rollen som global administratör. Vi rekommenderar att du använder säkerhets administratören, aktiva reparations åtgärder och Sök och rensa roller ovan för åtgärds Center behörigheter.

## <a name="next-steps"></a>Nästa steg 

- [Godkänna eller avvisa väntande åtgärder efter en automatisk undersökning](mtp-autoir-actions.md)
- [Visa resultatet av en automatisk undersökning](mtp-autoir-results.md)

