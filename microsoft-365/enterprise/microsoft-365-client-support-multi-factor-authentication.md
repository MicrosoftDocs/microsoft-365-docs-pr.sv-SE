---
title: 'Microsoft 365 Stöd för klientprogram: Multifaktorautentisering'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: I den här artikeln lär du dig vilka plattformar, klienter och PowerShell-moduler som har stöd för multifaktorautentisering för Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927573"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a>Microsoft 365 Stöd för klientprogram: Multifaktorautentisering

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

För att ge ytterligare säkerhetsnivå för inloggningar kan klienter vara konfigurerade för att använda multifaktorautentisering (MFA), som använder både ett användarlösenord och en annan metod för användarverifiering baserat på:

- En man som äger den är inte lätt duplicerad, till exempel en smartphone.
- Något som användaren har unikt och korrekt, till exempel fingeravtryck, ansikte eller annat biometriskt attribut

Läs mer om [multifaktorautentisering](/azure/active-directory/authentication/multi-factor-authentication).

## <a name="supported-clients--platforms"></a>Klienter som stöds & plattformar

De senaste versionerna av följande klienter och plattformar har stöd för multifaktorautentisering. Mer information om plattformsstöd i Microsoft 365 finns i [Systemkrav för Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)