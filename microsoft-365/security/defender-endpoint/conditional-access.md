---
title: Aktivera villkorsstyrd åtkomst för att bättre skydda användare, enheter och data
description: Aktivera villkorsstyrd åtkomst för att förhindra att program körs om en enhet anses vara riskabel och ett program bedöms vara icke-kompatibelt.
keywords: villkorlig åtkomst, blockera program, säkerhetsnivå, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166203"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>Aktivera villkorsstyrd åtkomst för att bättre skydda användare, enheter och data 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

Villkorsstyrd åtkomst är en funktion som hjälper dig att bättre skydda dina användare och företagsinformation genom att se till att endast säkra enheter har åtkomst till program.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

Med villkorsstyrd åtkomst kan du styra åtkomsten till företagsinformation utifrån enhetens risknivå. Det här håller betrodda användare på betrodda enheter med hjälp av betrodda program.

Du kan definiera säkerhetsvillkor för vilka enheter och program som kan köra och komma åt information från nätverket genom att tillämpa principer för att stoppa program från att köras tills en enhet återgår till ett kompatibelt tillstånd. 

Implementeringen av villkorsstyrd åtkomst i Defender för Endpoint baseras på efterlevnadsprinciper för enheter Microsoft Intune (Intune) och villkorsstyrda åtkomstprinciper för Azure Active Directory (Azure AD). 

Efterlevnadsprincipen används med villkorsstyrd åtkomst för att endast enheter som uppfyller en eller flera policyregler för enhetsefterlevnad ska kunna komma åt program. 

## <a name="understand-the-conditional-access-flow"></a>Förstå flödet för villkorsstyrd åtkomst
Villkorsstyrd åtkomst sätts på plats så att åtkomst till känsligt innehåll blockeras när ett hot visas på en enhet tills hoten har åtgärdats. 

Flödet börjar med enheter som ser ut att ha en låg, medelstor eller hög risk. Dessa riskbestämningar skickas sedan till Intune. 

Beroende på hur du konfigurerar principer i Intune kan villkorsstyrd åtkomst konfigureras så att principen tillämpas när vissa villkor uppfylls.

Du kan till exempel konfigurera Intune att använda villkorsstyrd åtkomst på enheter som innebär hög risk.

I Intune används en princip för enhetsefterlevnad tillsammans med villkorlig åtkomst i Azure AD för att blockera åtkomst till program. Parallellt startas en automatiserad undersökning och åtgärdsprocess.

 En användare kan fortfarande använda enheten medan automatisk undersökning och åtgärd pågår, men åtkomsten till företagsdata blockeras tills hoten har åtgärdats helt. 

Om du vill lösa risken som finns på en enhet måste du returnera enheten till ett kompatibelt tillstånd. En enhet återgår till ett kompatibelt tillstånd när den saknar risk. 

Det finns tre sätt att hantera en risk:
1. Använd manuell eller automatiserad åtgärd.
2. Lös aktiva aviseringar på enheten. Då tas risken bort från enheten.
3. Du kan ta bort enheten från de aktiva principerna och därför kommer villkorsstyrd åtkomst inte att tillämpas på enheten. 

Manuell åtgärd kräver en sekops-administratör för att undersöka en avisering och ta itu med risken som visas på enheten. Den automatiska korrigeringen konfigureras via konfigurationsinställningarna i följande avsnitt, [Konfigurera villkorsstyrd åtkomst.](configure-conditional-access.md)

När risken tas bort via manuell eller automatisk åtgärd återgår enheten till en kompatibel status och åtkomst till program beviljas.

I följande exempelsekvens av händelser förklaras villkorsstyrd åtkomst i praktiken:

1. En användare öppnar en skadlig fil och Defender för Endpoint flaggar enheten som högrisk.
2. Utvärderingen med hög risk överförs till Intune. Parallellt initieras en automatiserad undersökning för att åtgärda det identifierade hotet. En manuell åtgärd kan också utföras för att åtgärda det identifierade hotet.
3. Baserat på principen som skapats i Intune markeras enheten som inte kompatibel. Utvärderingen meddelas sedan till Azure AD genom intune-principen för villkorsstyrd åtkomst. I Azure AD används motsvarande princip för att blockera åtkomst till program.
4. Den manuella eller automatiserade undersökningen och korrigeringen slutförs och hot tas bort. Defender för Endpoint ser att det inte finns någon risk på enheten och Intune bedömer enheten som kompatibel. Azure AD tillämpar principen som ger åtkomst till program.
5. Användare kan nu komma åt program.

 
## <a name="related-topic"></a>Relaterat ämne
- [Konfigurera villkorsstyrd åtkomst i Microsoft Defender för Slutpunkt](configure-conditional-access.md)
