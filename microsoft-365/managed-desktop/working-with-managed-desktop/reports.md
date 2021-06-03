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
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729974"
---
# <a name="work-with-reports"></a>Arbeta med rapporter

Microsoft Hanterat skrivbord flera rapporter och instrumentpaneler som IT-administratörer i organisationen kan använda för att förstå olika aspekter av populationen av enheter.Du hittar rapporter på två platser: i Microsoft Endpoint Manager [och](https://endpoint.microsoft.com) i [Microsoft 365 Administrationscenter](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

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


 ## <a name="inventory-data"></a>Lagerdata

Förutom de andra rapporterna kan du exportera information om de enheter som hanteras av Microsoft Hanterat skrivbord. I vyn **Enheter** i området **Enheter i** Microsoft Endpoint Manager använder du fliken **Exportera alla** för att hämta en [detaljerad lagerrapport](device-inventory-report.md).