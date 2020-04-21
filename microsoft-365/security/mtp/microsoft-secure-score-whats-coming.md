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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583721"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Vad kommer i Microsoft Secure Score?

För att göra [Microsoft Secure Score](microsoft-secure-score.md) till en bättre representant för din säkerhetsposition och förbättra användbarheten gör vi vissa ändringar inom en snar framtid. Din poäng och högsta möjliga poäng kommer att förändras. Detta innebär dock inte en förändring i din säkerhetsposition.

Mer information om de senaste ändringarna finns [i Vad är nytt i Microsoft Secure Score?](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>21 april 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Ta bort förbättringsåtgärder som inte uppfyller förväntningarna för tillförlitlig mätning eller inte ger en användbar representation av säkerhetshållning

För att säkerställa att Microsoft Secure Score är meningsfull och att varje förbättringsåtgärd är mätbar och tillförlitlig tar vi bort följande förbättringsåtgärder.

- Använda IRM-skydd på dokument
- Tillämpa principer för förebyggande av dataförlust

### <a name="adding-azure-ad-improvement-action-to-preview"></a>Lägga till Azure AD-förbättringsåtgärd i förhandsversionen

Lägga till följande förbättringsåtgärd för Azure Active Directory i [förhandsversionen av Microsoft Secure Score:](microsoft-secure-score-preview.md)

- Tillåt inte användare att bevilja samtycke till ohanterada program (finns för närvarande i släppt version)

### <a name="adding-azure-atp-improvement-actions-to-preview"></a>Lägga till Azure ATP-förbättringsåtgärder i förhandsversionen

Lägga till följande azure advanced threat protection improvement actions i [förhandsversionen av Microsoft Secure Score:](microsoft-secure-score-preview.md)

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

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a>Stöd för säkerhetsrekommendationer för Microsoft Defender ATP Threat & Vulnerability Management (TVM) i förhandsversionen

Alla utgivna säkerhetsrekommendationer som tillhandahålls av TVM kommer nu också att vara tillgängliga [förhandsgranskningsversionen av Microsoft Secure Score](microsoft-secure-score-preview.md).
