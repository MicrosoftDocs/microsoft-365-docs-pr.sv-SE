---
title: Kontrollera att dina enheter är korrekt konfigurerade
description: Konfigurera enheter på rätt sätt för att öka den totala motståndskraften mot hot och förbättra din förmåga att identifiera och reagera på attacker.
keywords: onboard, Intune-hantering, MDATP, WDATP, Microsoft Defender, Windows Defender, avancerat skydd mot hot, minska attackytan, ASR, säkerhetsbaslinje
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7b00ceafc2761f42c316f434a27acf7c551e7cf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163369"
---
# <a name="ensure-your-devices-are-configured-properly"></a>Kontrollera att dina enheter är korrekt konfigurerade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Med korrekt konfigurerade enheter kan du öka den totala motståndskraft mot hot och förbättra din förmåga att identifiera och reagera på attacker. Med hjälp av säkerhetskonfigurationshantering kan du säkerställa att dina enheter:

- Gå till Microsoft Defender för Slutpunkt
- Möt eller överskrider konfiguration av säkerhetsbaslinje för Defender för slutpunkt
- Gör åtgärder för strategiska attackytor på plats

Klicka **på Konfigurationshantering** i navigeringsmenyn för att öppna sidan Hantering av enhetskonfiguration.

![Sida för hantering av säkerhetskonfiguration](images/secconmgmt_main.png)<br>
*Sida för hantering av enhetskonfiguration*

Du kan spåra konfigurationsstatus på organisationsnivå och snabbt vidta åtgärder som svar på dålig täckning under onboarding, efterlevnadsproblem och dåligt optimerade minskningar av attackytan genom direkta, djupa länkar till sidor för enhetshantering på Microsoft Intune och Microsoft 365 säkerhetscenter.

När du gör det har du nytta av följande:
- Omfattande synlighet för händelser på dina enheter
- Robust information om hot och kraftfulla enhetsinlärningstekniker för bearbetning av rådata och identifiering av intrångsaktivitet och hotindikatorer
- En komplett hög med säkerhetsfunktioner som är konfigurerade för att effektivt stoppa installationen av skadliga program, kapning av systemfiler och systemfiler, datainfiltrering och andra hotaktiviteter
- Optimerade minskningar av attackytor, maximera strategiska skydd mot hotaktivitet samtidigt som påverkan på produktiviteten minimeras

## <a name="enroll-devices-to-intune-management"></a>Registrera enheter till Intune-hantering

Hantering av enhetskonfigurationer fungerar nära med intune enhetshantering för att upprätta inventeringen av enheterna i din organisation och den grundläggande säkerhetskonfigurationen. Du kommer att kunna spåra och hantera konfigurationsproblem på Intune-hanterade Windows 10-enheter.

Innan du kan se till att dina enheter har konfigurerats korrekt bör du registrera dem i Intune-hantering. Intune-registrering är robust och har flera registreringsalternativ för Windows 10-enheter. Mer information om intune-registreringsalternativ finns i Om hur du [ställer in registrering för Windows-enheter.](https://docs.microsoft.com/intune/windows-enroll)

>[!NOTE]
>För att registrera Windows-enheter till Intune måste administratörer redan ha tilldelats licenser. [Läs om hur du tilldelar licenser för enhetsregistrering](https://docs.microsoft.com/intune/licenses-assign).

>[!TIP] 
>Om du vill optimera enhetshantering via Intune [ansluter du Intune till Defender för Slutpunkt](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).

## <a name="obtain-required-permissions"></a>Skaffa behörighet som krävs
Som standard kan endast användare som har tilldelats rollen Global administratör eller Intune-tjänstadministratör i Azure AD hantera och tilldela de enhetskonfigurationsprofiler som behövs för registrering av enheter och distribuera säkerhetsbaslinjen.

Om du har tilldelats andra roller bör du kontrollera att du har rätt behörighet:

- Fullständig behörighet till enhetskonfigurationer
- Fullständig behörighet till säkerhetsbaslinjer
- Läs behörigheter till principer för enhetsefterlevnad
- Läsbehörigheter för organisationen

![Behörighet som krävs för intune](images/secconmgmt_intune_permissions.png)<br>
*Behörigheter för enhetskonfiguration i Intune*

>[!TIP] 
>Mer information om hur du tilldelar behörigheter för Intune finns [i Skapa anpassade roller.](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role)

## <a name="in-this-section"></a>I det här avsnittet
Ämne | Beskrivning
:---|:---
[Få enheter onboarded till Defender för Endpoint](configure-machines-onboarding.md)| Spåra onboardingstatus för Intune-hanterade enheter och registrera fler enheter via Intune. 
[Öka efterlevnad för Defender för slutpunktens säkerhetsbaslinje](configure-machines-security-baseline.md) | Spåra grundläggande efterlevnad och icke-efterlevnad. Distribuera säkerhetsbaslinjen till fler Intune-hanterade enheter.
[Optimera ASR-regeldistribution och identifiering](configure-machines-asr.md) | Granska regeldistribution och justera identifieringar med hjälp av effektanalysverktyg i Säkerhetscenter i Microsoft 365.

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
