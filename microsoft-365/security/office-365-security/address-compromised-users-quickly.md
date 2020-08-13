---
title: Lösa användar konton med automatisk undersökning och svar
keywords: LUFT, autoIR, ATP, automatiserad, undersökning, svar, reparation, hot, Avancerat, hot, skydd, kompromissad
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
ms.date: 02/25/2020
description: Lär dig hur du påskyndar processen att upptäcka och rikta in användar konton med automatiserade undersökningar och svars funktioner i Office 365 Avancerat skydds abonnemang 2.
ms.openlocfilehash: 5a1dd64a0b30bb230af0d96432ae9542ce0370d8
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656915"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Lösa användar konton med automatisk undersökning och svar

[Office 365 Avancerat skydds plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) inkluderar kraftfulla [automatiserade undersökningar och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air). Sådana funktioner kan spara din säkerhets åtgärds grupp mycket tid och ansträngning för att hantera hot. Microsoft fortsätter att förbättra säkerhets funktionerna. De senaste lösningarna har förbättrats för att omfatta Playbook (för närvarande för hands version). Läs den här artikeln om du vill ha mer information om säkerhets Playbook. Och se hur det går [fortare att upptäcka och reagera på användarens kompromisser och begränsa omfattningen av intrång till Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) .

![Automatiserad undersökning av en användare med kompromiss](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Användarens säkerhets Playbook gör att organisationens säkerhets team kan:

- Snabb identifiering av obehöriga användar konton;

- Begränsa omfattningen av en överträdelse när ett konto äventyras; och

- Reagera på äventyrade användare effektivt och effektivt.

## <a name="compromised-user-alerts"></a>Obehöriga användar aviseringar

När ett användar konto är skadat uppstår atypical eller avvikande beteende. Till exempel kan nätfiske och skräp post skickas internt från ett betrott användar konto. Office 365 Avancerat skydd kan upptäcka sådana avvikelser i e-postmönster och samarbets aktivitet i Office 365. När detta inträffar utlöses notifieringar och hotets minsknings processen påbörjas.

Här är en avisering som utlöstes på grund av misstänkt e-post:

![Avisering utlöses på grund av misstänkt e-post](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Här är ett exempel på en avisering som utlöstes när en användares skickade gräns nåddes:

![Avisering utlöst för att skicka gräns har uppnåtts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Undersöka och svara på en användare med kompromiss

När ett användar konto är skadat utlöses notifieringarna. I vissa fall blockeras användar kontot och förhindras från att skicka fler e-postmeddelanden förrän problemet löses av organisationens säkerhets åtgärds team. I andra fall börjar en automatisk undersökning som kan resultera i rekommenderade åtgärder som din säkerhets grupp bör vidta.

- [Visa och undersöka begränsade användare](#view-and-investigate-restricted-users)

- [Visa information om automatiserade utredningar](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Du måste ha nödvändig behörighet för att utföra följande uppgifter. Se vilka [behörigheter som krävs för att använda Air-funktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Visa och undersöka begränsade användare

Det finns några olika alternativ för att gå till en lista över begränsade användare. I säkerhets & Compliance Center kan du till exempel gå till **Threat Management**  >  **Granska**  >  **begränsade användare**. I följande procedur beskrivs navigering med instrument panelen **aviseringar** , som är ett bra sätt att se olika typer av aviseringar som kan ha utlösts.

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in.

2. Välj instrument panel för **aviseringar**i navigerings fönstret  >  **Dashboard**.

3. I widgeten **andra varningar** väljer **du begränsade användare**.

   ![Widgeten andra varningar](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Listan med begränsade användare öppnas.<br/>![Begränsade användare i Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Välj ett användar konto i listan för att visa information och vidta åtgärder, till exempel [att släppa den begränsade användaren](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).

### <a name="view-details-about-automated-investigations"></a>Visa information om automatiserade utredningar

När en automatiserad undersökning har påbörjats kan du se dess information och resultaten i säkerhets & Compliance Center. Gå till **Threat Management**  >  **utredningar**och välj sedan en undersökning för att visa dess uppgifter.

Mer information finns i [Visa information om en undersökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande saker

- **Håll koll på dina aviseringar**. Som du vet är det längre en kompromiss som försvinner, desto större potential och kostnad för din organisation, kunder och partners. Tidiga identifieringar och svars tiden är kritiska för att minska risken för hot, särskilt när en användares konto äventyras.

- **Automatisering hjälper, men ersätter inte, din säkerhets åtgärd**. Automatiserade undersökningar och svars funktioner kan upptäcka en användare som är utsatt för tidigt, men din säkerhets åtgärd är antagligen tvungen att delta och göra vissa undersökningar och ny hjälp. Behöver du hjälp med det här? Se [Granska och godkänna åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **Använd inte en misstänkt inloggnings avisering som indikator**. Det kan hända att det inte går att utlösa en varning om misstänkt inloggning när ett användar konto är skadat. Ibland är det en serie aktiviteter som inträffar efter att ett konto har blivit utsatt för en avisering. Vill du veta mer om aviseringar? Se [aviserings principer](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Nästa steg

- [Granska de behörigheter som krävs för att använda AIR-funktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Hitta och undersöka skadlig e-post i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Lär dig mer om AIR i Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besök Microsoft 365-översikten för att se vad som kommer snart och lanseras](https://www.microsoft.com/microsoft-365/roadmap?filters=)

