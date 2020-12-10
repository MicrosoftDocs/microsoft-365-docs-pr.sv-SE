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
description: Lär dig hur du påskyndar processen att upptäcka och rikta in användar konton med automatiserade undersökningar och svars funktioner i Microsoft Defender för Office 365 abonnemang 2.
ms.openlocfilehash: 19c9bad33263178f92c6fe523b44497cf38ebd53
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616743"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Lösa användar konton med automatisk undersökning och svar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender för Office 365 abonnemang 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) inkluderar kraftfulla [automatiserade undersökningar och svar](office-365-air.md) (Air). Sådana funktioner kan spara din säkerhets åtgärds grupp mycket tid och ansträngning för att hantera hot. Microsoft fortsätter att förbättra säkerhets funktionerna. De senaste lösningarna har förbättrats för att omfatta Playbook (för närvarande för hands version). Läs den här artikeln om du vill ha mer information om säkerhets Playbook. Och se hur det går [snabbare att upptäcka och reagera på användarnas kompromisser och begränsa eventuella överträdelser med Microsoft Defender för Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) .

![Automatiserad undersökning av en användare med kompromiss](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Användarens säkerhets Playbook gör att organisationens säkerhets team kan:

- Snabb identifiering av obehöriga användar konton;

- Begränsa omfattningen av en överträdelse när ett konto äventyras; och

- Reagera på äventyrade användare effektivt och effektivt.

## <a name="compromised-user-alerts"></a>Obehöriga användar aviseringar

När ett användar konto är skadat uppstår atypical eller avvikande beteende. Till exempel kan nätfiske och skräp post skickas internt från ett betrott användar konto. Defender för Office 365 kan upptäcka sådana avvikelser i e-postmönster och samarbets aktivitet i Office 365. När detta inträffar utlöses notifieringar och hotets minsknings processen påbörjas.

Här är en avisering som utlöstes på grund av misstänkt e-post:

![Avisering utlöses på grund av misstänkt e-post](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Här är ett exempel på en avisering som utlöstes när en användares skickade gräns nåddes:

![Avisering utlöst för att skicka gräns har uppnåtts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Undersöka och svara på en användare med kompromiss

När ett användar konto är skadat utlöses notifieringarna. I vissa fall blockeras användar kontot och förhindras från att skicka fler e-postmeddelanden förrän problemet löses av organisationens säkerhets åtgärds team. I andra fall börjar en automatisk undersökning som kan resultera i rekommenderade åtgärder som din säkerhets grupp bör vidta.

- [Visa och undersöka begränsade användare](#view-and-investigate-restricted-users)

- [Visa information om automatiserade utredningar](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Du måste ha nödvändig behörighet för att utföra följande uppgifter. Se vilka [behörigheter som krävs för att använda Air-funktioner](office-365-air.md#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Visa och undersöka begränsade användare

Det finns några olika alternativ för att gå till en lista över begränsade användare. I säkerhets & Compliance Center kan du till exempel gå till **Threat Management** \> **Granska** \> **begränsade användare**. I följande procedur beskrivs navigering med instrument panelen **aviseringar** , som är ett bra sätt att se olika typer av aviseringar som kan ha utlösts.

1. Gå till <https://protection.office.com> och logga in.

2. Välj instrument panel för **aviseringar** i navigerings fönstret \> .

3. I widgeten **andra varningar** väljer **du begränsade användare**.

   ![Widgeten andra varningar](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Listan med begränsade användare öppnas.

   ![Begränsade användare i Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Välj ett användar konto i listan för att visa information och vidta åtgärder, till exempel [att släppa den begränsade användaren](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="view-details-about-automated-investigations"></a>Visa information om automatiserade utredningar

När en automatiserad undersökning har påbörjats kan du se dess information och resultaten i säkerhets & Compliance Center. Gå till **Threat Management** \> **utredningar** och välj sedan en undersökning för att visa dess uppgifter.

Mer information finns i [Visa information om en undersökning](air-view-investigation-results.md).

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande saker

- **Håll koll på dina aviseringar**. Som du vet är det längre en kompromiss som försvinner, desto större potential och kostnad för din organisation, kunder och partners. Tidiga identifieringar och svars tiden är kritiska för att minska risken för hot, särskilt när en användares konto äventyras.

- **Automatisering hjälper, men ersätter inte, din säkerhets åtgärd**. Automatiserade undersökningar och svars funktioner kan upptäcka en användare som är utsatt för tidigt, men din säkerhets åtgärd är antagligen tvungen att delta och göra vissa undersökningar och ny hjälp. Behöver du hjälp med det här? Se [Granska och godkänna åtgärder](air-review-approve-pending-completed-actions.md).

- **Använd inte en misstänkt inloggnings avisering som indikator**. Det kan hända att det inte går att utlösa en varning om misstänkt inloggning när ett användar konto är skadat. Ibland är det en serie aktiviteter som inträffar efter att ett konto har blivit utsatt för en avisering. Vill du veta mer om aviseringar? Se [aviserings principer](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Nästa steg

- [Granska de behörigheter som krävs för att använda AIR-funktioner](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Hitta och undersöka skadlig e-post i Office 365](investigate-malicious-email-that-was-delivered.md)

- [Lär dig mer om AIR i Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besök Microsoft 365-översikten för att se vad som kommer snart och lanseras](https://www.microsoft.com/microsoft-365/roadmap?filters=)
