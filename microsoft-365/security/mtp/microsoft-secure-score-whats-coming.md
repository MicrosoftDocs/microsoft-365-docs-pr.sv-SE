---
title: Vad kommer i Microsoft Secure Score?
description: I artikeln beskrivs Microsoft Secure Score i Microsoft 365-säkerhetscentret, hur information beräknas och vilka säkerhetsadministratörer som kan förvänta sig.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807253"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Vad kommer i Microsoft Secure Score?

För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition och förbättra användbarheten gör vi vissa ändringar inom en snar framtid. Din poäng och högsta möjliga poäng kommer att förändras. Detta innebär dock inte en förändring i din säkerhet hållning.

Mer information om de senaste ändringarna finns [i Nyheter i Microsoft Secure Score?](microsoft-secure-score.md#whats-new)

## <a name="march-16th-2020"></a>16 mars 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Ta bort förbättringsåtgärder som inte uppfyller förväntningarna på tillförlitlig mätning eller inte ger en användbar representation av säkerhetshållning

För att säkerställa att Microsoft Secure Score är meningsfull och att varje förbättringsåtgärd är mätbar och tillförlitlig tar vi bort följande förbättringsåtgärder.

- Lagra användardokument i OneDrive för företag
- Konfigurera principer för säker bifogad fil i Office 365
- Konfigurera Office 365-säkra länkar för att verifiera webbadresser
- Tillåt inte postlådedelegering
- Tillåt anonyma gästdelningslänkar för webbplatser och dokument
- Aktivera säkerhetskonsolen för molnappar
- Konfigurera förfallotid för externa delningslänkar

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Stöd för säkerhetsstandardvärden för Azure AD-förbättringsåtgärder

Microsoft Secure Score uppdaterar förbättringsåtgärder för att stödja [säkerhetsstandardvärden i Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), vilket gör det enklare att skydda din organisation med förkonfigurerade säkerhetsinställningar för vanliga attacker.

Det kommer att påverka följande förbättringsåtgärder:

- Se till att alla användare kan slutföra multifaktorautentisering för säker åtkomst
- Kräv MFA för administrativa roller
- Aktivera princip för att blockera äldre autentisering
