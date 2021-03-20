---
title: 'Microsoft 365 Client App-support: Certifikatbaserad autentisering'
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
description: I den här artikeln hittar du information om stöd för Microsoft 365 Client App för certifikatbaserad autentisering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904997"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 Client App-support: Certifikatbaserad autentisering

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Modern autentisering är en övergripande term för en kombination av autentiserings- och auktoriseringsmetoder. Dessa metoder omfattar:

- **Autentiseringsmetoder:** Flerfaktorautentisering Certifikatbaserad autentisering för klient.
- **Auktoriseringsmetoder:** Microsofts implementering av Open Authorization (OAuth).

Modern autentisering aktiveras med hjälp av ett autentiseringsbibliotek som Active Directory Authentication Library (ADAL) eller Microsoft Authentication Library (MSAL). Modern autentisering är det som klienter använder för att autentisera och auktorisera åtkomst till Microsoft 365-resurser. Modern autentisering använder OAuth och ger en säker mekanism för klienter för åtkomst till Microsoft 365-tjänster, utan åtkomst till användarautentiseringsuppgifter. Vid inloggning autentiserar användaren direkt med Azure Active Directory och får ett tokenpar för åtkomst/uppdatering vid returnering. Åtkomsttoken beviljar klientåtkomst till lämpliga resurser i Microsoft 365-klientorganisationen. En uppdateringstoken används för att erhålla ett nytt åtkomst- eller uppdateringstokenpar när den aktuella åtkomsttoken upphör att gälla.

Modern autentisering har stöd för olika autentiseringsmetoder, till exempel certifikatbaserad autentisering. Klienter på Windows-, Android- eller iOS-enheter kan använda certifikatbaserad autentisering (CBA) för att autentisera till Azure Active Directory med hjälp av ett klientcertifikat på enheten. I stället för ett vanligt användarnamn/lösenord används certifikatet för att hämta ett åtkomst-/uppdatera tokenpar från Azure Active Directory.

Läs mer om [certifikatbaserad autentisering.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Klienter som stöds & plattformar

De senaste versionerna av följande klienter och plattformar har stöd för certifikatbaserad autentisering när du loggar in på Azure Active Directory-konton inom klienten (till exempel när du lägger till ett konto i appen). Mer information om plattformsstöd i Microsoft 365 finns i [Systemkrav för Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
>Edge för iOS och Android har stöd för certifikatbaserad autentisering vid konto lägg till flöden. Edge för iOS och Android stöder inte certifikatbaserad autentisering när autentisering utförs mot webbplatser, som normalt är intranätwebbplatser. <br><br>  I det här scenariot navigerar användaren till en webbplats (vanligtvis i intranätet) där webbplatsen kräver att användaren autentiserar via ett certifikat. Det här innebär inte modern autentisering alls och utnyttjar inte något autentiseringsbibliotek från Microsoft. Det här beror på en begränsning i iOS: iOS förhindrar åtkomst till systemnyckelringen där certifikaten lagras (endast Apple-appar och [webbvykontrollen i Safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) kan komma åt systemnyckelringen). <br><br> När Edge använder [WebKit Framework](https://developer.apple.com/documentation/webkit) för rendering av webbplatser kan Edge inte komma åt systemnyckelringen och ge användaren ett certifikatval. Det här är dessvärre på grund av Apples arkitektur.

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

