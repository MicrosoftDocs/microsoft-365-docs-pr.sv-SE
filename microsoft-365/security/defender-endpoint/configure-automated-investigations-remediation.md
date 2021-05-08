---
title: Konfigurera funktioner för automatisk undersökning och åtgärder
description: Konfigurera automatisk undersökning och åtgärder i Microsoft Defender för Endpoint.
keywords: konfigurera, konfigurera, automatiserad, undersökning, identifiering, aviseringar, åtgärd, svar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 23d6c8c87a6cbcc7b8060440ba2c0cae6182767d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274550"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Konfigurera funktioner för automatisk undersökning och åtgärder i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Om din organisation använder [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/) för Slutpunkt (Defender för [Slutpunkt)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) kan automatiska undersöknings- och åtgärdsfunktioner spara din tid och ditt arbete med säkerhetsåtgärder. Som beskrivs i [det här blogginlägget](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)efterliknar de här funktionerna de idealiska steg som en säkerhetsanalytiker tar för att undersöka och åtgärda hot. [Läs mer om automatiserad undersökning och åtgärd.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) 

Om du vill konfigurera automatisk undersökning och åtgärd
1. [Aktivera funktionerna](#turn-on-automated-investigation-and-remediation). och 
2. [Konfigurera enhetsgrupper](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>Aktivera automatisk undersökning och åtgärd

1. Som global administratör eller säkerhetsadministratör går du till Microsoft Defender Säkerhetscenter [https://securitycenter.windows.com](https://securitycenter.windows.com) () och loggar in.
2. Välj Inställningar i **navigeringsfönstret.**
3. I avsnittet **Allmänt** väljer du **Avancerade funktioner.**
4. Aktivera både automatisk **undersökning och** matcha **aviseringar automatiskt.**

## <a name="set-up-device-groups"></a>Konfigurera enhetsgrupper

1. I Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ), på **sidan Inställningar,** under **Behörigheter** väljer du **Enhetsgrupper**.
2. Välj **+ Lägg till enhetsgrupp.**
3. Skapa minst en enhetsgrupp enligt följande:
   - Ange ett namn och en beskrivning för enhetsgruppen.
   - I listan **Automationsnivå** väljer du en nivå, till exempel Fullständigt – åtgärda **hot automatiskt.** Automationsnivån avgör om åtgärder vidtas automatiskt eller bara efter godkännande. Mer information finns i [Automatiseringsnivåer i automatiserad undersökning och åtgärd.](automation-levels.md)
   - I avsnittet **Medlemmar** använder du ett eller flera villkor för att identifiera och inkludera enheter.
   - På fliken **Användaråtkomst** väljer du de [Azure Active Directory-grupper](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) som ska ha åtkomst till enhetsgruppen som du skapar.
4. Välj **Klar** när du är klar med att konfigurera enhetsgruppen.

## <a name="next-steps"></a>Nästa steg

- [Gå till Åtgärdscenter om du vill visa väntande och slutförda åtgärdsåtgärder](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Granska och godkänna väntande åtgärder](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Se även

- [Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint](defender-endpoint-false-positives-negatives.md)
