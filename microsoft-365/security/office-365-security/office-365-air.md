---
title: Automatiserad undersökning och svar (AIR)-komma igång
keywords: LUFT, autoIR, ATP, automatiserad, undersökning, svar, reparation, hot, Avancerat, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Komma igång med automatiska undersökningar och svars funktioner i Office 365 Avancerat skydds plan 2.
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: adee64461d06b46f467682835a493a7eebe89aef
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202657"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Komma igång med automatisk undersökning och svar (AIR) i Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 Avancerat skydd](office-365-atp.md) (Office 365 ATP) plan 2 inkluderar kraftfulla automatiserade undersökningar och svar (Air) som kan spara tid och kraft för arbets uppgifter. När notifieringar utlöses är det upp till din säkerhets åtgärd för att granska, prioritera och svara på dessa aviseringar. Det är lätt att hålla kontakten med volymen av inkommande varningar. Att automatisera vissa av detta kan vara till hjälp. Med flyg kan din säkerhets åtgärds grupp fokusera på aktiviteter med högre prioritet utan att förlora varningar som utlöses.

Den här artikeln innehåller:
- LUFT [flödet](#the-overall-flow-of-air) .
- [Hur man kommer igång](#how-to-get-air); och 
- De [behörigheter som krävs](#required-permissions-to-use-air-capabilities) för att konfigurera eller använda Air-funktioner. 

## <a name="the-overall-flow-of-air"></a>Det allmänna luft flödet

På en hög nivå utlöses en avisering och en säkerhets Playbook påbörjar en automatiserad undersökning som ger resultat och rekommendationer. Här är det allmänna flödet för luft, steg för steg:

1. En automatiserad undersökning initieras på något av följande sätt:

   - En [avisering](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) utlöses av en Office-händelse som skapar en olycka. Beroende på vilken typ av händelse det gäller påbörjar en [Playbook](automated-investigation-response-office.md#security-playbooks) en automatisk undersökning. 

     ---eller---
   
   - En säkerhetsanalytiker [startar en automatisk undersökning](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) när du använder [Threat Explorer](threat-explorer.md).

2. När en automatiserad undersökning körs samlar den in ytterligare information om e-postmeddelandet i fråga och enheter som är relaterade till e-postmeddelandet. Sådana enheter kan innehålla filer, URL: er och mottagare.  Undersökningens omfattning kan öka när nya och relaterade notifieringar utlöses.

3. Under och efter en automatisk undersökning finns [information och resultat](air-view-investigation-results.md) tillgängliga för visning. Resultaten innehåller [rekommenderade åtgärder](air-remediation-actions.md) som kan vidtas för att svara och åtgärda eventuella hot som hittats. Dessutom är en [Playbook-logg](air-view-investigation-results.md#playbook-log) som visar alla undersöknings aktiviteter.

    Om din organisation använder en anpassad rapporterings lösning eller en lösning från tredje part kan du [använda API: t för hanterings aktiviteten för Office 365](air-custom-reporting.md) för att visa information om automatiserade utredningar och hot.

4. Säkerhets åtgärds gruppen granskar [undersöknings resultat och rekommendationer](air-view-investigation-results.md)och [godkänner eller avvisar reparations åtgärder](air-review-approve-pending-completed-actions.md). 

    Eftersom pågående reparations åtgärder är godkända (eller nekade) är den automatiska undersökningen klar.

> [!NOTE]
> I Office 365 ATP vidtas inga reparations åtgärder automatiskt. Reparations åtgärder vidtas endast vid godkännande av organisationens säkerhets team. 

Under och efter en automatiserad gransknings process kan säkerhets teamet göra följande:

- [Visa information om en avisering om en undersökning](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Visa resultat informationen för en undersökning](air-view-investigation-results.md#view-details-of-an-investigation)

- [Granska och godkänna åtgärder som ett resultat av en undersökning](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Mer information finns i [så här fungerar luften](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Så här kommer du till luften

Office 365 AIR-funktioner ingår i [office 365, abonnemang 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2). Men [Office 365 ATP-principer bör konfigureras](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) så att de fungerar som de ska. Dessutom bör du kontrol lera att du har granskat och kanske konfigurerar organisationens [notifieringsregler](https://docs.microsoft.com/microsoft-365/compliance/alert-policies). 

Microsoft 365 innehåller många inbyggda aviserings principer som hjälper dig att identifiera behörigheter för Exchange-administratörer om missbruk, skadlig program vara, potentiella externa och interna hot samt informations hanterings risker. Flera av [standard aviserings principerna](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan utlösa automatiserade utredningar. Bland annat följande:

- En potentiellt skadlig URL-klickning identifieras

- Ett e-postmeddelande rapporteras av en användare som Phish

- E-postmeddelanden med skadlig kod tas bort efter leverans

- E-postmeddelanden som innehåller Phish URL-adresser tas bort efter leverans

- Misstänkta e-postmeddelanden som skickar mönster identifieras

- En användare är begränsad från att skicka e-post

[Lär dig mer om aviseringar och luft](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Nödvändig behörighet för att använda AIR-funktioner

Behörigheter beviljas via vissa roller, till exempel de som beskrivs i följande tabell: 

|Uppgift |Nödvändiga roller |
|--|--|
|Så här ställer du in AIR-funktioner |En av följande roller: <br/>-Global administratör<br/>-Säkerhets administratör <br/>Dessa roller kan tilldelas i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|För att godkänna eller avvisa rekommenderade åtgärder|En av följande roller, tilldelad i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>-Global administratör <br/>-Säkerhets administratör<br/>-Säkerhets läsare <br/>---och---<br/>-Sök och Töm (den här rollen tilldelas endast i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Du kanske måste skapa en ny roll grupp och lägga till rollen Sök och rensa i den nya roll gruppen.

[Office 365 ATP-abonnemang 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) licenser ska tilldelas:
- Säkerhets administratörer (inklusive globala administratörer)
- Organisationens säkerhets åtgärds team (inklusive säkerhets läsare och de som har rollen Sök och rensa)
- Slutanvändare:

Dessutom måste [principer för Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) definieras och användas för att skydd ska kunna användas.

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat från en automatisk undersökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Granska och godkänna pågående åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Relaterade artiklar

- [Automatisk undersökning och reparation i Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatisk undersökning och svar i skydd mot Microsoft Threat](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
