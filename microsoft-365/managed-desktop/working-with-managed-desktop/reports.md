---
title: Arbeta med rapporter
description: De olika rapporterna som är tillgängliga i Microsoft Hanterat skrivbord
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771891"
---
# <a name="work-with-reports"></a>Arbeta med rapporter

Microsoft Hanterat skrivbord flera rapporter och instrumentpaneler som IT-administratörer i organisationen kan använda för att förstå olika aspekter av populationen av enheter. 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporter i Microsoft Endpoint Manager

I Microsoft Endpoint Manager-konsolen samlas rapportering från flera produkter på en enda plats så att du kan övervaka och undersöka problem med din konfiguration och enheter med Azure AD-organisationen ("klientorganisation"). Microsoft Managed Desktop har ett **avsnitt** under Rapporter i huvudmenyn där du kan hitta rapporter som är Microsoft Hanterat skrivbord för hantering av enheter som du har registrerat.

De här rapporterna omfattar:
- **Hanterade enheter**  >  **Funktionsuppdateringar:** Den här vyn visar den övergripande statusen för funktionsuppdateringar på alla Microsoft Hanterat skrivbord enheter.
- **Hanterade enheter**  >  **Office uppdateringar:** I den här vyn visas den övergripande statusen Office uppdateringar på alla Microsoft Hanterat skrivbord enheter.

På flera platser i hela Microsoft Endpoint Manager kan du dessutom filtrera rapporter från andra produktgrupper för att specifikt inkludera eller exkludera dina enheter som hanteras av Microsoft Hanterat skrivbord. Dessa rapporter har integrerat den här filtreringsfunktionerna:

- [Alla enheter](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Enhetsefterlevnad](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Enheter som inte är kompatibla](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Anpassade Microsoft Hanterat skrivbord-roller garanterar att du bara har Microsoft Hanterat skrivbord åtkomst till rapporterna. Information om hur du kommer Microsoft Endpoint Manager, **till** exempel Alla enheter, finns i [Rollbaserad åtkomstkontroll med Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control) 

## <a name="endpoint-analytics"></a>Slutpunktsanalyser
Microsoft Hanterat skrivbord är nu integrerat med [Slutpunktsanalys.](/mem/analytics/overview) De här rapporterna ger dig insikter som mäter hur organisationen arbetar och kvaliteten på den upplevelse du levererat till användarna. Slutpunktsanalys finns i **menyn** Rapporter i [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Om du vill pivotera ett poängresultat för att endast inkludera enheter som hanteras av Microsoft Hanterat skrivbord går du till en rapport, väljer listrutan **Filter** och väljer **sedan Microsoft Hanterat skrivbord enheter**.

Om Slutpunktsanalyser inte konfigurerades automatiskt för din Azure AD-organisation ("klientorganisation") under registreringen kan du göra det själv. Mer information finns i Introduktion [i Portalen för slutpunktsanalys](/mem/analytics/enroll-intune#bkmk_onboard). Du kan registrera alla dina enheter eller, om du bara vill inkludera Microsoft Hanterat skrivbord enheter, välja grupperna för **moderna** enheter på arbetsplatsen för Test, Första, Snabb och Bred. De här rapporterna kan kräva olika behörigheter. Mer information finns i Behörigheter [för](/mem/analytics/overview#permissions) att säkerställa att du har roller som tilldelats på rätt sätt.

> [!NOTE]
> För att bättre respektera sekretess för användarnas sekretess måste det finnas fler än 10 Microsoft Hanterat skrivbord enheter som är registrerade med Slutpunktsanalys för att använda det här filtret.

 ## <a name="inventory-data"></a>Lagerdata

Förutom de andra rapporterna kan du exportera information om de enheter som hanteras av Microsoft Hanterat skrivbord. I vyn **Enheter** i området **Enheter i** Microsoft Endpoint Manager använder du fliken **Exportera alla** för att hämta en [detaljerad lagerrapport](device-inventory-report.md).
