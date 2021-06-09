---
title: Bli en Microsoft Defender för Endpoint-partner
ms.reviewer: ''
description: Läs om stegen och kraven för att integrera din lösning med Microsoft Defender för Endpoint och bli partner
keywords: partner, integrering, lösningsvalidering, certifiering, krav, medlem, fela, programportal
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 35ba1fe85fa9b62770142636d46303b37534b976
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893323"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Bli en Microsoft Defender för Endpoint-partner

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Om du vill bli defender för slutpunktslösningspartner måste du följa och slutföra följande steg.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>Steg 1: Prenumerera på en Microsoft Defender för slutpunktsutvecklarelicens
Prenumerera på [Microsoft Defender för slutpunktsutvecklarelicensen](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9). När du prenumererar kan du använda en Microsoft Defender för slutpunktsklientorganisation med upp till 10 enheter för att utveckla lösningar som kan integreras med Microsoft Defender för Slutpunkt. 

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Steg 2: Uppfylla kraven för lösningsverifiering och certifiering
Det bästa sättet för teknikpartner att intyga att deras integration fungerar är att få en gemensam kund att godkänna den föreslagna integrationsdesignen (kunden kan använda alternativet Rekommendera **en partner** på sidan [Partnerprogram](https://securitycenter.microsoft.com/interoperability/partners) i Microsoft Defender Säkerhetscenter) och få den testad och nedgraderad till Microsoft Defender för Slutpunkt-teamet.

När Microsoft Defender för Endpoint-teamet har granskat och godkänt integreringen dirigerar vi dig till att tas med som partner på Microsoft Intelligent Security Association.

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>Steg 3: Bli medlem i Microsoft Intelligent Security Association
[Microsoft Intelligent Security Association](https://www.microsoft.com/security/partnerships/intelligent-security-association) är ett program särskilt för Microsofts säkerhetspartner som hjälper dig att utveckla dina säkerhetsprodukter och göra dina integrationer med Microsofts säkerhetsprodukter mer upptäckbar.

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Steg 4: Få listan i Microsoft Defender för slutpunktspartnerprogramportalen
Microsoft Defender för Endpoint stöder identifiering och integrering av program från tredje part med hjälp av sidan för [produktpartner](partner-applications.md) som är inbäddad i Microsoft Defender för slutpunktshanteringsportalen. 

För att ditt företag ska visas som partner på sidan för produktpartner måste du ange följande information:

1. En fyrkantig logotyp (SVG).
2. Namnet på den produkt som ska presenteras.
3. Ange en produktbeskrivning på 15 ord.
4. Länka till startsidan för kunden för att slutföra integreringen eller blogginlägget med tillräcklig information för kunderna. Alla pressmeddelanden, inklusive Microsoft Defender för Endpoint-produktens namn, bör granskas av marknadsförings- och teknikteamen. Vänta i minst 10 dagar på att granskningsprocessen ska vara klar.
5.  Om du använder Azure AD-metoden med flera innehavare behöver vi Azure AD-programmets namn för att kunna spåra användningen av programmet.
6. Ta med User-Agent i varje API-anrop som görs i Microsoft Defender för offentlig uppsättning slutpunkts-API:er eller Graph-säkerhets-API:er. Det används i statistiska syften, felsökning och partnerigenkänning. Det här steget är dessutom ett krav för medlemskap i Microsoft Intelligent Security Association (MISA).

    Gör så här:
    
    - Ställ in User-Agent i respektive HTTP-begärans sidhuvud till formatet nedan.

    - `MdePartner-{CompanyName}-{ProductName}/{Version}`
    
    - Till exempel användaragent: `MdePartner-Contoso-ContosoCognito/1.0.0`
    
    - Mer information finns i [AVSNITTET RFC 2616-14.43.](https://tools.ietf.org/html/rfc2616#section-14.43)

Samarbeten med Microsoft Defender för Endpoint hjälper våra gemensamma kunder att ytterligare effektivisera, integrera och skydda skydd. Vi är glada att du har valt att bli Microsoft Defender för Endpoint-partner och att nå vårt gemensamma mål att effektivt skydda kunder och deras tillgångar genom att förhindra och svara på moderna hot tillsammans.

## <a name="related-topics"></a>Relaterade ämnen
- [Möjligheter för tekniska partner](partner-integration.md)
