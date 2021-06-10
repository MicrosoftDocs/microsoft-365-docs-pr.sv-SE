---
title: Microsoft 365 isolationskontroller
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lär dig hur avgränsningskontroller fungerar inom Microsoft 365, så att tjänster kan överse med varandra eller vara fristående vid behov.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918948"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 isolationskontroller 

Microsoft arbetar kontinuerligt för att säkerställa att arkitekturen för flera innehavare i Microsoft 365 har stöd för säkerhet på företagsnivå, konfidentialitet, sekretess, integritet, lokala, internationella och [tillgänglighetsstandarder.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) Omfattning och omfattning för tjänster som tillhandahålls av Microsoft gör det svårt och icke-ekonomiskt att hantera Microsoft 365 med betydande mänsklig interaktion. Microsoft 365 tjänster tillhandahålls via flera globalt distribuerade datacenter, var och en automatiserad i hög grad med få åtgärder som kräver ett mänskligt tryck eller åtkomst till kundinnehåll. Vår personal stödjer dessa tjänster och datacenter med automatiska verktyg och mycket säker fjärråtkomst. 

Microsoft 365 består av flera tjänster som ger viktiga affärsfunktioner och bidrar till hela Microsoft 365 upplevelsen. Var och en av dessa tjänster är fristående och utformade för att integreras med varandra.

Microsoft 365 är utformat med följande principer:

 - **[Tjänstorienterad arkitektur](/previous-versions/aa480021(v=msdn.10)): utforma** och utveckla programvara i form av interoperabla tjänster som ger väldefinierade affärsfunktioner.
 - **[Operational Security Assurance:](https://www.microsoft.com/download/details.aspx?id=40872)** ett ramverk som införlivar de kunskaper som har fåtts med olika funktioner som är unika för Microsoft, inklusive Microsoft [Security Development Lifecycle,](https://www.microsoft.com/sdl/default.aspx) [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)och djup förståelse för hotbilden för cyberhot.

Microsoft 365 tjänster samarbetar med varandra, men är utformade och implementerade så att de kan användas och drivs som autonoma tjänster, oberoende av varandra. Microsoft överger uppgifter och ansvarsområden för Microsoft 365 för att minska möjligheter för obehöriga eller oavsiktliga ändringar eller missbruk av organisationens tillgångar. Microsoft 365 grupper har definierat roller som en del av en omfattande rollbaserad mekanism för åtkomstkontroll.

## <a name="customer-content-isolation"></a>Avgränsning av kundinnehåll

Allt kundinnehåll i en klientorganisation isoleras från andra klientorganisationar och från verksamhets- och systemdata som används för hantering av Microsoft 365. Flera olika former av skydd implementeras Microsoft 365 hela tiden för att minimera risken för att en Microsoft 365 tjänst eller program går ur. Flera olika former av skydd förhindrar också obehörig åtkomst till information från klientorganisationen eller Microsoft 365 system.

Information om hur Microsoft implementerar logisk avgränsning av klientdata i Microsoft 365 finns i [Innehavarisolering i Microsoft 365](microsoft-365-tenant-isolation-overview.md).