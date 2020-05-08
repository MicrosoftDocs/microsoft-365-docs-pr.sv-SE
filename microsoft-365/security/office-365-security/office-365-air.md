---
title: Automatiserad undersökning och respons (AIR) - Komma igång
keywords: AIR, autoIR, ATP, automatiserad, utredning, svar, sanering, hot, avancerad, hot, skydd
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
description: Kom igång med automatiska funktioner för undersökningar och svar i Office 365 Advanced Threat Protection Plan 2.
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 4e36e0fa07f825d3259ef9e42b802c81ae929470
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159413"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Komma igång med automatisk undersökning och svar (AIR) i Office 365

[Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) Plan 2 innehåller kraftfulla funktioner för automatisk undersökning och svar (AIR) som kan spara tid och ansträngning för säkerhetsoperationer. När aviseringar utlöses är det upp till säkerhetsoperationsteamet att granska, prioritera och svara på dessa aviseringar. Att hålla jämna steg med volymen av inkommande aviseringar kan vara överväldigande. Automatisera en del av detta kan hjälpa. Med AIR kan ditt säkerhetsteam fokusera på uppgifter med högre prioritet utan att förlora aviseringar som utlöses ur sikte.

I den här artikeln beskrivs det [övergripande flödet](#the-overall-flow-of-air) av AIR, hur [du skaffar AIR](#how-to-get-air)och de [behörigheter som krävs](#required-permissions-to-use-air-capabilities) för att konfigurera eller använda AIR-funktioner. 

## <a name="the-overall-flow-of-air"></a>Det totala flödet av AIR

På en hög nivå utlöses en avisering och en säkerhetsspelbok startar och automatiserad undersökning, vilket resulterar i resultat och rekommendationer. Här är det totala flödet av AIR, steg för steg:

1. En automatiserad undersökning inleds på något av följande sätt:

   - En [avisering](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) utlöses av en Office-händelse som skapar en incident. Beroende på typen av incident startar en [säkerhetsuppspelningsbok](automated-investigation-response-office.md#security-playbooks) en automatisk undersökning. 

     --- eller ---
   
   - En säkerhetsanalytiker [startar en automatisk undersökning](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) när [hotutforskaren](threat-explorer.md)använder .

2. Medan en automatiserad undersökning körs samlar den in ytterligare data om e-postmeddelandet i fråga och enheter relaterade till e-postmeddelandet. Sådana entiteter kan innehålla filer, webbadresser och mottagare.  Utredningens omfattning kan öka när nya och relaterade aviseringar utlöses.

3. Under och efter en automatiserad undersökning finns [information och resultat](air-view-investigation-results.md) tillgängliga för visning. Resultaten inkluderar [rekommenderade åtgärder](air-remediation-actions.md) som kan vidtas för att svara och åtgärda eventuella hot som hittades. Dessutom finns en [spelbokslogg](air-view-investigation-results.md#playbook-log) tillgänglig som spårar all undersökningsaktivitet.

    Om din organisation använder en anpassad rapporteringslösning eller en tredjepartslösning kan du [använda API:et för hanteringsaktivitet för Office 365](air-custom-reporting.md) för att visa information om automatiska undersökningar och hot.

4. Säkerhetsoperationsgruppen granskar [undersökningsresultaten och rekommendationerna](air-view-investigation-results.md)och [godkänner eller avvisar åtgärder för reparation](air-review-approve-pending-completed-actions.md). 

    I takt med att pågående saneringsåtgärder godkänns (eller avvisas) slutförs den automatiska undersökningen.

> [!NOTE]
> I Office 365 ATP vidtas inga åtgärder för reparation automatiskt. Reparationsåtgärder vidtas endast efter godkännande av organisationens säkerhetsteam. 

Under och efter en automatiserad undersökningsprocess kan säkerhetsteamet göra följande:

- [Visa information om en avisering som är relaterad till en undersökning](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Visa resultatinformation om en undersökning](air-view-investigation-results.md#view-details-of-an-investigation)

- [Granska och godkänna åtgärder till följd av en undersökning](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Mer information finns i [Hur AIR fungerar](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Hur får man AIR

Office 365 AIR-funktionerna ingår i [Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2). [Dina Office 365 ATP-principer bör](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) dock konfigureras för att AIR ska fungera som förväntat. Dessutom, se till att granska och eventuellt konfigurera organisationens [aviseringsprinciper](https://docs.microsoft.com/microsoft-365/compliance/alert-policies). 

Microsoft 365 innehåller många inbyggda varningsprinciper som hjälper dig att identifiera missbruk av Exchange-administratörsbehörigheter, aktivitet med skadlig programvara, potentiella externa och interna hot och risker för informationsstyrning. Flera av [standardvarningsprinciperna](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan utlösa automatiska undersökningar. Dessa inkluderar följande:

- Ett potentiellt skadligt URL-klick identifieras

- Ett e-postmeddelande rapporteras av en användare som phish

- E-postmeddelanden som innehåller skadlig kod tas bort efter leverans

- E-postmeddelanden som innehåller phish webbadresser tas bort efter leverans

- Misstänkta e-postutskicksmönster upptäcks

- En användare är begränsad från att skicka e-post

[Läs mer om aviseringar och AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Nödvändiga behörigheter för att använda AIR-funktioner

Behörigheter beviljas via vissa roller, till exempel de som beskrivs i följande tabell: 

|Uppgift |Roll(er) krävs |
|--|--|
|Så här konfigurerar du AIR-funktioner |En av följande roller: <br/>- Global administratör<br/>- Säkerhetsadministratör <br/>Dessa roller kan tilldelas i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i Security & Compliance [Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Så här godkänner eller avvisar du rekommenderade åtgärder|En av följande roller, som tilldelats i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i Security & Compliance [Center):](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)<br/>- Global administratör <br/>- Säkerhetsadministratör<br/>- Säkerhetsläsare <br/>--- och ---<br/>- Sök och rensa (den här rollen tilldelas endast i [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Du kanske måste skapa en ny rollgrupp där och lägga till rollen Sök och rensa i den nya rollgruppen.)

[Office 365 ATP-abonnemang 2-licenser](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) ska tilldelas:
- Säkerhetsadministratörer (inklusive globala administratörer)
- Organisationens säkerhetsoperationsteam (inklusive säkerhetsläsare och personer med rollen Sök och rensa)
- Slutanvändare

Dessutom måste [Office 365 ATP-principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) definieras och tillämpas för att skyddet ska vara på plats.

## <a name="next-steps"></a>Nästa steg

- [Se information och resultat av en automatiserad undersökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Granska och godkänna väntande åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Relaterade artiklar

- [Automatiserad undersökning och reparation i Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatiserad undersökning och svar i Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
