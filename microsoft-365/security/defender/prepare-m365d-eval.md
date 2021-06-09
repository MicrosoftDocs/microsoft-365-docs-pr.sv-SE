---
title: Förbereda din Microsoft 365 Defender testlabbmiljö
description: Förbereda godkännanden från intressenter, tidslinjer, miljööverväganden och införandeordningen när du beställer en Microsoft 365 Defender-testlabb eller pilotmiljö
keywords: Microsoft 365 Provförberedelser för Defender, Microsoft 365 Defender-pilotförberedelser, förbereda för att köra ett Microsoft 365 Defender-pilotprojekt, köra ett pilotprojekt i Microsoft 365 Defender-projekt, distribuera, förbereda, intressenter, tidslinje, miljö, slutpunkt, server, hantering och införande
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7ebb7074b0e06eda96d21142044bd8b9997e094b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841660"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Förbereda din Microsoft 365 Defender-testlabb eller pilotmiljö

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Att skapa Microsoft 365 Defender-testlabb eller testmiljö och distribuera den är en process i tre steg:

|![Fas 1: Förbereda](../../media/phase-diagrams/prepare.png)<br/>Fas 1: Förbereda |[![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fas 2: Konfigurera](setup-m365deval.md) |[![Fas 3: Introduktion](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Fas 3: Introduktion](config-m365d-eval.md) | [![Tillbaka till pilottestning](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Tillbaka till pilotspelboken](m365d-pilot.md) |
|--|--|--|--|
|*Du är här!* | || |

Du befinner dig för närvarande i förberedelsefasen.


Förberedelse är avgörande för en lyckad distribution. Det här avsnittet vägleder dig genom vad du behöver tänka på när du förbereder för att skapa ett testlabb eller pilotmiljö för din Microsoft 365 Defender-distribution.

## <a name="prerequisites"></a>Förutsättningar
Läs mer om licens-, maskinvaru- och programvarukraven och andra konfigurationsinställningar för att tillhandahålla och använda Microsoft 365 Defender. Se minimikraven för [Microsoft 365 Defender](/microsoft-365/security/defender/prerequisites), Microsoft Defender för [slutpunkt](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), Microsoft Defender för [Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), Microsoft Defender för [identitet](/azure-advanced-threat-protection/atp-prerequisites) [och Microsoft Cloud App Security](/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Intressenter och av inloggning
Identifiera alla intressenter som är inblandade i projektet och vem som kan behöva signera, granska eller hålla sig informerad, oavsett om det gäller utvärdering eller ett pilotprojekt.

>[!NOTE]
>Det är inte alla organisationer som har förfallodagen för säkerhetsorganisationen som har sådana roller. Om så är fallet bör du rådgöra med din ledning om konto för granskning och godkännande.

Lägg till intressenter i tabellen nedan efter behov för din organisation.

-   SO = Sign-off på det här projektet

-   R = Granska det här projektet och ge input

-   I = Informeras om projektet

| Namn                 | Roll                                                                                                                                                                                                          | Åtgärd |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Ange namn och e-postadress | **CISO (Chief Information Security Officer)** En chef som fungerar som *sponsor inom organisationen för den nya teknikdistributionen.*                                                  | SO     |
| Ange namn och e-postadress | **Chef för Cyber Defense Operations Center (CDOC)** En representant från *CDOC-teamet* som ansvarar för att definiera hur ändringen justeras mot processerna i kundens säkerhetsoperationsteam.       | SO     |
| Ange namn och e-postadress | **Säkerhetsarkitekt** En representant för säkerhetsgruppen som ansvarar för att definiera hur ändringen överensstämmer med organisationens *kärnarkitektur inom säkerhet.*                         | R      |
| Ange namn och e-postadress | **Arbetsplatsarkitekt** *En representant för IT-teamet* som ansvarar för att definiera hur förändringen är i linje med organisationens kärnarkitektur på arbetsplatsen.                             | R      |
| Ange namn och e-postadress | **Säkerhetsanalytiker En** representant för CDOC-teamet som kan ge feedback om identifieringsfunktioner, användarupplevelse och hur användbar den här ändringen är ur ett *säkerhetsperspektiv.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Förbered Azure Active Directory
Hoppa över det här steget om du redan har aktiverat synkronisering mellan Active Directory och Azure Active Directory lokalt. Gå igenom dokumentationen för befintliga metodtips från Azure Active Directory. Följande steg är optimerade för att utvärdera eller köra ett Microsoft 365 Defender-projekt.

1. Gå till [Azure Active Directory-portalen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > Azure **AD Anslut**. 
![Bild på Azure Active Directory portalsida](../../media/mtp-eval-1.png) <br> 

2. Klicka **på** Ladda **Microsoft Azure Active Directory Anslut** ladda ned från och överför den till din domänkontrollant.
![Bild på nedladdningssidan i Azure Active Directoru Anslut Active Directoru](../../media/mtp-eval-2.png) <br>

3. Följ domänkontrollanten på domänkontrollanten Azure Active Directory Anslut domänkontrollanten. Läs licensvillkoren och sekretesspolicyn och markera kryssrutan om du samtycker. Klicka på **Fortsätt**.
![Bild av välkomstsidan för Azure AD Anslut ad-Anslut](../../media/mtp-eval-3.png) <br>

4. Navigera till **Express-Inställningar**.
![Bild på Express Inställningar sida](../../media/mtp-eval-4.png) <br>

5. Ange dina autentiseringsuppgifter som global administratör. Klicka på **Nästa**.
![Bild av Anslut till Azure AD-sida där du ska ange dina autentiseringsuppgifter som global administratör](../../media/mtp-eval-5.png) <br>

6. Ange dina autentiseringsuppgifter som företagsadministratör för Active Directory Domain Services. Klicka på **Nästa**.
![Bild på Anslut till AD DS-sidan där du bör ange dina autentiseringsuppgifter](../../media/mtp-eval-6.png) <br>

7. Bekräfta **konfigurationen genom** att klicka på Installera.
![Bild på bekräftelsesidan för konfiguration](../../media/mtp-eval-7.png) <br>

8. Grattis! Du har konfigurerat Azure Active Directory Anslut.
![Bild av en Azure Active Directory Anslut konfiguration](../../media/mtp-eval-8.png) <br>

Nu kan du [lägga till användare och grupper i Active Directory och](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) konfigurera en [SAM-R-princip.](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Konfigurationsordning
I följande tabell visas den ordning som Microsoft rekommenderar för konfigurering av Microsoft 365 Defender-komponenter för testlabb- eller pilotmiljödistributionen.

| Komponent                               | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rangordning för konfigurationsordning |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender för Office 365|Microsoft Defender för Office 365 skyddar din organisation mot skadliga hot från e-postmeddelanden, länkar (URL: er) och samarbetsverktyg. <br> [Lära sig mer.](/microsoft-365/security/office-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender för identitet använder Active Directory-signaler för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga Insider-åtgärder riktade till organisationen. <br> [Mer information](/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security är en CASB (Cloud Access Security Broker) som fungerar i flera moln. Det ger full insyn, kontroll över data färdas och avancerad analys för att identifiera och bekämpa cyberhot i alla dina molntjänster. <br> [Mer information](/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender för Endpoint | Microsoft Defender för Endpointslutpunktsidentifiering och svarsfunktioner tillhandahåller avancerad identifiering av attacker som finns i närheten och kan vidtas. Säkerhetsanalytiker kan effektivt prioritera varningar, få synlighet över helheten av ett intrång och vidta åtgärder för att åtgärda hot. <br> [Lära sig mer.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Nästa steg
|![Fas 2: Installation](../../media/setup.png) <br>[Fas 2: Installation](setup-m365deval.md) | Konfigurera din testlabb eller pilotmiljö i Microsoft 365 Defender
|:-------|:-----|
