---
title: Komma igång med automatisk undersökning och svar i Microsoft Defender för Office 365
keywords: LUFT, autoIR, ATP, automatiserad, undersökning, svar, reparation, hot, Avancerat, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Komma igång med automatiska undersökningar och svars funktioner i Microsoft Defender för Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925610"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Komma igång med automatisk undersökning och svar (AIR) i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender för Office 365](office-365-atp.md) inkluderar kraftfulla automatiserade undersökningar och svars funktioner som kan spara tid och ansträngning för arbets uppgifter. När notifieringar utlöses är det upp till din säkerhets åtgärd för att granska, prioritera och svara på dessa aviseringar. Det är lätt att hålla kontakten med volymen av inkommande varningar. Att automatisera vissa av dessa uppgifter kan hjälpa dig. Med flyg kan din säkerhets åtgärds grupp fokusera på aktiviteter med högre prioritet utan att förlora viktiga larm som utlöses.

I den här artikeln beskrivs:
- [Luft flödet](#the-overall-flow-of-air).
- [Hur man kommer igång](#how-to-get-air); och 
- De [behörigheter som krävs](#required-permissions-to-use-air-capabilities) för att konfigurera eller använda Air-funktioner. 

## <a name="the-overall-flow-of-air"></a>Det allmänna luft flödet

En notifiering utlöses och en säkerhets Playbook påbörjar en automatiserad undersökning, vilket resulterar i resultat och rekommenderade åtgärder. Här är det allmänna flödet för luft, steg för steg:

1. En automatiserad undersökning initieras på något av följande sätt:

   - En [avisering](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) utlöses av något misstänkt i e-post (till exempel ett meddelande, en bilaga eller en URL). En incident skapas. Beroende på vilken typ av tillbud det är, en [säkerhets Playbook](automated-investigation-response-office.md#security-playbooks) körs och en automatisk undersökning påbörjas. 

     ---eller---
   
   - En säkerhetsanalytiker [startar en automatisk undersökning](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) när du använder [Threat Explorer](threat-explorer.md).

2. När en automatiserad undersökning körs samlar den in ytterligare information om e-postmeddelandet i fråga och enheter som är relaterade till e-postmeddelandet. Sådana enheter kan innehålla filer, URL: er och mottagare.  Undersökningens omfattning kan öka när nya och relaterade notifieringar utlöses.

3. Under och efter en automatisk undersökning finns [information och resultat](air-view-investigation-results.md) tillgängliga för visning. Resultaten innehåller [rekommenderade åtgärder](air-remediation-actions.md) som kan vidtas för att svara på och åtgärda eventuella hot som hittats. Dessutom är en [Playbook-logg](air-view-investigation-results.md#playbook-log) som visar alla undersöknings aktiviteter.


4. Säkerhets åtgärds gruppen granskar [undersöknings resultat och rekommendationer](air-view-investigation-results.md)och [godkänner eller avvisar reparations åtgärder](air-review-approve-pending-completed-actions.md). 

5. Eftersom pågående reparations åtgärder är godkända (eller nekade) är den automatiska undersökningen klar.

> [!IMPORTANT]
> I Microsoft Defender för Office 365 vidtas ingen reparations åtgärd automatiskt. Reparations åtgärder vidtas endast vid godkännande av organisationens säkerhets team. AIR-kapacitet sparar emellertid dina arbets tid för säkerhets åtgärder genom att identifiera åtgärder och tillhandahålla de uppgifter som behövs för att fatta ett välgrundat beslut.

Under och efter varje automatiserad undersökning kan säkerhets åtgärds teamet:

- [Visa information om en avisering om en undersökning](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Visa resultat informationen för en undersökning](air-view-investigation-results.md#view-details-of-an-investigation)

- [Granska och godkänna åtgärder som ett resultat av en undersökning](air-review-approve-pending-completed-actions.md)

> [!TIP]
> En mer detaljerad översikt över [hur Air fungerar](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Så här kommer du till luften

AIR-funktioner ingår i [Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), förutsatt att dina principer och aviseringar är konfigurerade. Om du vill ha hjälp med det här följer du anvisningarna i [skydda mot hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) för att konfigurera eller konfigurera följande skydds inställningar: 

1. [Gransknings loggning](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (ska vara aktive rad)

2. [Principer för antispionprogram](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [Skydd mot nätfiske](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. [Antispam skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).
   
5. [Säkra länkar och säkra bifogade filer](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).
   
6. [Säkra bilagor för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).
   
7. [Rensa tom timme för e-post](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).

Dessutom bör du se till att [Granska organisationens notifieringsregler](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), särskilt [standard principerna i kategorin Threat Management](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies). 

## <a name="which-alert-policies-trigger-automated-investigations"></a>Vilka notifieringsregler utlöser automatiserade utredningar?

Microsoft 365 innehåller många inbyggda aviserings principer som hjälper dig att identifiera behörigheter för Exchange-administratörer om missbruk, skadlig program vara, potentiella externa och interna hot samt informations hanterings risker. Flera av [standard aviserings principerna](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan utlösa automatiserade utredningar. Bland annat följande:

- En potentiellt skadlig URL-klickning identifieras
- Ett e-postmeddelande rapporteras av en användare som Phish
- E-postmeddelanden med skadlig kod tas bort efter leverans
- E-postmeddelanden som innehåller Phish URL-adresser tas bort efter leverans
- Misstänkta e-postmeddelanden som skickar mönster identifieras
- En användare är begränsad från att skicka e-post

## <a name="required-permissions-to-use-air-capabilities"></a>Nödvändig behörighet för att använda AIR-funktioner

Behörigheter beviljas via vissa roller, till exempel de som beskrivs i följande tabell: 

|Uppgift |Nödvändiga roller |
|--|--|
|Så här ställer du in AIR-funktioner |En av följande roller: <br/>-Global administratör<br/>-Säkerhets administratör <br/>Dessa roller kan tilldelas i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|För att godkänna eller avvisa rekommenderade åtgärder|En av följande roller, tilldelad i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>-Global administratör <br/>-Säkerhets administratör<br/>-Säkerhets läsare <br/>---och---<br/>-Sök och Töm (den här rollen tilldelas endast i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Du kanske måste skapa en ny roll grupp och lägga till rollen Sök och rensa i den nya roll gruppen.

## <a name="required-licenses"></a>Nödvändiga licenser

Licenser [för Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) ska tilldelas:
- Säkerhets administratörer (inklusive globala administratörer)
- Organisationens säkerhets åtgärds team (inklusive säkerhets läsare och de som har rollen Sök och rensa)
- Slutanvändare:


## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat från en automatisk undersökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Granska och godkänna pågående åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Relaterade artiklar

- [Automatisk undersökning och reparation i Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatisk undersökning och svar i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
