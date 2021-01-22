---
title: Arbeta med rapporter
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921356"
---
# <a name="work-with-reports"></a>Arbeta med rapporter

Microsoft Managed Desktop tillhandahåller flera rapporter och instrumentpaneler som IT-administratörer i organisationen kan använda för att förstå olika aspekter av populationen av enheter.Du hittar rapporter på två platser: i [Microsoft Endpoint Manager och](https://endpoint.microsoft.com) i administrationscentret för Microsoft [365.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporter i Microsoft Endpoint Manager

I Microsoft Endpoint Manager-konsolen samlas rapportering från flera produkter på en enda plats så att du kan övervaka och undersöka problem med konfigurationen och enheterna i Azure AD-organisationen ("klientorganisationen"). Microsoft Managed Desktop har ett **avsnitt** under Rapporter i huvudmenyn där du kan hitta rapporter som är specifika för Microsoft Managed Desktop-hantering av enheter som du har registrerat.

Dessa rapporter omfattar:
- **Hanterade enheter**  >  **Funktionsuppdateringar:** Den här vyn visar den övergripande statusen för funktionsuppdateringar för alla microsoft-enheter som hanteras av datorn.
- **Hanterade enheter**  >  **Office-uppdateringar:** Den här vyn visar den övergripande statusen för Office-uppdateringar för alla dina Microsoft Managed Desktop-enheter.

På flera platser i Microsoft Endpoint Manager kan du dessutom filtrera rapporter från andra produktgrupper för att specifikt inkludera eller exkludera dina enheter som hanteras av Microsoft Managed Desktop. Dessa rapporter har integrerat den här filtreringsfunktionerna:

- [Alla enheter](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Enhetsefterlevnad](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Enheter som inte är kompatibla](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Anpassade Microsoft-hanterade skrivbordsroller garanterar endast åtkomst till Rapporter om Hanterade Microsoft-datorer. Information om hur du kommer åt andra delar av Microsoft Endpoint Manager, till exempel **Alla** enheter, finns i Rollbaserad [åtkomstkontroll med Microsoft Intune.](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>Rapporter i administrationscentret för Microsoft 365

Du hittar rapporter om Microsoft Hanterade skrivbord genom att öppna Administrationscenter  för [Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)och sedan navigera till Rapporter och välja **Microsoft Hanterat skrivbord.** Du kan också följa direktlänken till de här rapporterna från fliken **Microsoft Hanterad** dator på startsidan [Microsoft Endpoint Manager.](https://endpoint.microsoft.com) 

Dessa rapporter omfattar: 

- [Användningsinformation](usage-insights.md) – den här vyn ger användningsmått för Microsoft Hanterade skrivbordsenheter.
- [Insikter om tillförlitlighet](reliability-insights.md) – den här vyn ger dig en hälsosammanfattning av dina hanterade enheter.
- [Batteriinsikter](battery-insights.md) – Den här vyn visar information om energianvändningen för appar och den projicerade batteritiden för enheter i din miljö.
- [Information om Windows-säkerhetsuppdateringar](security-update-insights.md) – Den här vyn visar information om säkerhetsuppdateringarna för dina Microsoft Managed Desktop-enheter.

 ## <a name="inventory-data"></a>Lagerdata

Förutom de andra rapporterna kan du exportera information om de enheter som hanteras av Microsoft Managed Desktop. I vyn **Enheter** i området **Enheter i** Microsoft Endpoint Manager använder du fliken Exportera **alla** för att ladda ned en [detaljerad lagerrapport.](device-inventory-report.md)
