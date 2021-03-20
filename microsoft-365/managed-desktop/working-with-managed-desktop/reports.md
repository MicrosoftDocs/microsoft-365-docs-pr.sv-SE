---
title: Arbeta med rapporter
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917688"
---
# <a name="work-with-reports"></a>Arbeta med rapporter

Microsoft Managed Desktop innehåller flera rapporter och instrumentpaneler som IT-administratörer i organisationen kan använda för att förstå olika aspekter av populationen av enheter.Du hittar rapporter på två platser: i [Microsoft Endpoint Manager och](https://endpoint.microsoft.com) i administrationscentret för Microsoft [365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporter i Microsoft Endpoint Manager

I Microsoft Endpoint Manager-konsolen samlas rapportering från flera produkter på en och samma plats så att du kan övervaka och undersöka problem med konfiguration och enheter med Azure AD-organisationen ("klientorganisation"). Microsoft Managed Desktop har ett **avsnitt** under Rapporter i huvudmenyn där du kan hitta rapporter som är specifika för hanteringen av de enheter som du har registrerat för Microsoft Managed Desktop.

De här rapporterna omfattar:
- **Hanterade enheter**  >  **Funktionsuppdateringar:** Den här vyn visar den övergripande statusen för funktionsuppdateringar för alla dina Microsoft Managed Desktop-enheter.
- **Hanterade enheter**  >  **Office-uppdateringar:** Den här vyn visar den övergripande statusen för Office-uppdateringar för alla dina Microsoft Managed Desktop-enheter.

På flera platser i Microsoft Endpoint Manager kan du dessutom filtrera rapporter från andra produktgrupper för att specifikt inkludera eller exkludera dina enheter som hanteras av Microsoft Managed Desktop. Dessa rapporter har integrerat den här filtreringsfunktionerna:

- [Alla enheter](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Enhetsefterlevnad](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Enheter som inte är kompatibla](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Anpassade Microsoft-hanterade skrivbordsroller garanterar endast åtkomst till rapporterna från Hanterade Microsoft. Information om hur du kommer åt andra delar av Microsoft Endpoint Manager, till exempel Alla **enheter,** finns i [Rollbaserad åtkomstkontroll med Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>Rapporter i Administrationscenter för Microsoft 365

Du kan hitta Microsoft Hanterade skrivbordsinsikter genom att öppna [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)och sedan navigera till Rapporter och välja Microsoft Managed **Desktop.**  Du kan också följa direktlänken till de här rapporterna från fliken **Microsoft Hanterat skrivbord** på startsidan [Microsoft Endpoint Manager.](https://endpoint.microsoft.com) 

De här rapporterna omfattar: 

- [Användningsinformation](usage-insights.md) – Den här vyn innehåller användningsmått för dina Microsoft Managed Desktop-enheter.
- [Insikter om tillförlitlighet](reliability-insights.md) – den här vyn ger dig en hälsosammanfattning av dina hanterade enheter.
- [Batteriinsikter](battery-insights.md) – I den här vyn visas information om energiförbrukningen i appar och den projekterade batteritiden för enheter i din miljö.
- [Insikter om Windows-säkerhetsuppdateringar](security-update-insights.md) – I den här vyn visas information om status för säkerhetsuppdateringar för dina Microsoft Managed Desktop-enheter.

 ## <a name="inventory-data"></a>Lagerdata

Förutom de andra rapporterna kan du exportera information om de enheter som hanteras av Microsoft Managed Desktop. I vyn **Enheter** i området **Enheter i** Microsoft  Endpoint Manager använder du fliken Exportera alla för att hämta en [detaljerad lagerrapport](device-inventory-report.md).