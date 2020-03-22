---
title: Vad kommer i Microsoft Secure Score?
description: I artikeln beskrivs Microsoft Secure Score i säkerhetscentret Microsoft 365, hur information beräknas och vilka säkerhetsadministratörer som kan förvänta sig.
keywords: säkerhet, malware, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
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
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895447"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Vad kommer i Microsoft Secure Score?

För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition och förbättra användbarheten gör vi vissa ändringar inom en snar framtid. Din poäng och högsta möjliga poäng kommer att förändras. Detta innebär dock inte en förändring i din säkerhetsposition.

Mer information om de senaste ändringarna finns [i Vad är nytt i Microsoft Secure Score?](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>21 april 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Ta bort förbättringsåtgärder som inte uppfyller förväntningarna för tillförlitlig mätning eller inte ger en användbar representation av säkerhetshållning

För att säkerställa att Microsoft Secure Score är meningsfull och att varje förbättringsåtgärd är mätbar och tillförlitlig tar vi bort följande förbättringsåtgärder.

- Ta bort/blockera konton som inte använts under de senaste 30 dagarna
- Utse färre än 5 globala administratörer
- Använda IRM-skydd på dokument
- Tillämpa principer för förebyggande av dataförlust

### <a name="adding-additional-control-support-in-the-preview-version"></a>Lägga till ytterligare kontrollstöd i förhandsversionen
- Tillåt inte användare att bevilja samtycke till ohanterada program (finns för närvarande i släppt version)

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a>Stöd för ytterligare åtgärder för förbättring av Microsoft Cloud App Security
- Inaktivera tjänsten Utskriftshanteraren på domänkontrollanter
- Ändra osäkra Kerberos-delegationer för att förhindra personifiering
- Skydda och hantera lokala administratörslösenord med Microsoft LAPS
- Minska risken för lateral rörelsebana för känsliga enheter
- Ta bort vilande konton från känsliga grupper
- Ta bort oskyddade SID-historikattribut från entiteter
- Lösa oskyddade kontoattribut
- Stoppa exponering för rensa textuppgifter
- Stoppa äldre protokollkommunikation
- Stoppa svag chifferanvändning

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>Stöd för säkerhetsrekommendationer för Microsoft Defender ATP Threat & Vulnerability Management (TVM)
- Alla utgivna säkerhetsrekommendationer från TVM kommer nu också att finnas tillgängliga i Microsoft Secure Score
