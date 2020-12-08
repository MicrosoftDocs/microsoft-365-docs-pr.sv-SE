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
ms.openlocfilehash: bfd8305d23e0e6d761c629ee3048c6204f702d37
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585334"
---
# <a name="work-with-reports"></a>Arbeta med rapporter

Microsoft Managed Desktop tillhandahåller flera rapporter och instrument paneler som IT-administratörer kan använda för att förstå olika aspekter av populationen av enheter.Du hittar rapporter på två platser: i [Microsoft slut punkts hanteraren](https://endpoint.microsoft.com) och i [administrations centret för Microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporter i Microsoft slut punkts hanteraren

Microsoft Endpoint Manager-konsolen samlar in rapporter från flera produkter på en och samma plats så att du kan övervaka och undersöka problem med konfiguration och enheter för Azure AD Organization ("klient organisation"). Microsoft Managed Desktop har ett avsnitt under **rapporter** i huvud menyn där du kan hitta rapporter som är specifika för Microsoft Managed Desktop Management för de enheter som du har registrerat.

På flera platser i Microsoft slut punkts hanteraren kan du dessutom filtrera rapporter från andra produkt grupper till att omfatta eller utesluta dina enheter som hanteras av Microsoft Managed Desktop. Dessa rapporter har integrerat denna filtrerings funktion:

- **Alla enheter**
- **Kompatibilitet med enheter**
- **Icke-kompatibla enheter**

> [!NOTE]
> Anpassade Microsoft Managed Desktop-roller garanterar endast åtkomst till Microsoft Managed Desktop-rapporter. Om du vill komma åt andra delar av Microsoft slut punkts hanteraren, till exempel **alla enheter**, läser du [rollbaserad åtkomst kontroll med Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Rapporter i administrations Center för Microsoft 365

Du hittar Microsoft Managed Desktop-rapporter genom att öppna [administrations centret för microsoft 365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)och sedan navigera till **rapporter** och välja **Microsoft Managed Desktop**. Du kan också följa den direkta länken till dessa rapporter från **Microsoft Managed Desktop** på Start sidans [Microsoft slut punkts hanterare](https://endpoint.microsoft.com). 

Dessa rapporter innehåller: 

- [Användnings](usage-insights.md) information – den här vyn innehåller användnings mått för Microsoft Managed Station ära datorer.
- [Ökad tillförlitlighet](reliability-insights.md) – med den här vyn får du en översikt över dina hanterade enheter.
- [Batteri insikter](battery-insights.md) – i den här vyn visas information om energi förbrukningen för appar och projektor livs längd för enheter i din miljö.
- [Windows Security Update Insights](security-update-insights.md) – den här vyn visar information om status för säkerhets uppdateringar för Microsoft Managed Station ära datorer.

 ## <a name="inventory-data"></a>Lager data

Utöver de andra rapporterna kan du exportera information om enheter som hanteras av Microsoft Managed Desktop. Använd fliken **Exportera alla** i vyn **Devices** **enheter** i Microsoft slut punkts hanteraren för att [Hämta en detaljerad inventerings rapport](device-inventory-report.md).