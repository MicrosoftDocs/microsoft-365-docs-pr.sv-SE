---
title: 'Microsoft 365-klientprogram: certifikatbaserad identifiering'
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
description: I den här artikeln hittar du information om support för Microsoft 365-klient för certifikatbaserad identifiering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57ced47c268f4d0515acb26aa8f705fa6e9ae0f9
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999390"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365-klientprogram: certifikatbaserad identifiering

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Modern autentisering är en parasoll för en kombination av autentiserings-och auktoriseringsregler. De omfattar:

- **Autentiseringsmetoder** : multifaktorautentisering; Klient certifikat-baserad verifikation.
- **Auktoriseringsregler** : Microsofts implementering av Open Authorization (OAuth).

Modern lösenordsautentisering aktive ras via användning av ett autentiseringspaket, till exempel Active Directory-autentiseringspaket (ADAL) eller Microsoft-autentiseringspaket (MSAL). Modern autentisering är vilka klienter som använder för att autentisera och auktorisera åtkomst till Microsoft 365-resurser. Modern autentisering utnyttjar OAuth och ger en säker mekanism för klienter att få åtkomst till Microsoft 365-tjänster utan att behöva åtkomst till användarautentiseringsuppgifter. Vid inloggning verifierar användaren direkt med Azure Active Directory och får ett par för Access/Refresh-token i Return. Åtkomsttoken beviljar klienten åtkomst till lämpliga resurser i Microsoft 365-klient organisationen. En uppdateringstoken används för att få ett nytt Access-eller Refresh-token när den aktuella åtkomsttoken upphör.

Modern auktorisering har stöd för olika autentiseringsmekanismer, till exempel certifikatbaserad verifikation. Klienter på Windows-, Android-eller iOS-enheter kan använda certifikatbaserad autentisering (CBA) för att autentisera till Azure Active Directory med ett klient certifikat på enheten. I stället för ett typiskt användar namn/lösen ord används certifikatet för att hämta ett par för åtkomst-och uppdateringstoken från Azure Active Directory.

Lär dig mer om [certifikatbaserad identifiering](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Klienter som stöds & plattformar

De senaste versionerna av följande klienter och plattformar har stöd för certifikatbaserad inloggningsautentisering när du loggar in i Azure Active Directory-konton på klienten (till exempel när du lägger till ett konto i appen). Mer information om plattforms stöd i Microsoft 365 finns i [system krav för microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Förvirra | Android | iOS | Mac| Windows 10 <br> Moderna appar| Windows 10 <br> Datorer |
|:---|:---:|:---:|:---:|:---:|:---:|
| Azure Active Directory-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Åtkomst | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Azure-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Företags Portal | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas |
| Cortana | Disponera | Disponera | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Delve | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Kant<sup>1</sup> | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Excel | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Exchange Online-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Formulär | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office 365-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |  |
| Kaizala | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office Lens| ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Office Mobile | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Office-Portal | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| OneDrive | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Disponera | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| OneNote | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Outlook | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Planner | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Power Apps | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Automatisk strömförsörjning | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Power BI | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| PowerPoint | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Project | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Publisher | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Skype för företag | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | ![Stöds](../media/check-mark.png) |
| Skype för Business-administratör | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| SharePoint | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| SharePoint Online-administratör | Disponera | Disponera | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Fästisar | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Strömma | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Sway | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) | Saknas |
| Teams | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas | Disponera |
| Att göra | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Saknas |
| Visio | Saknas | ![Stöds](../media/check-mark.png) | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | ![Stöds](../media/check-mark.png) |
| Whiteboard | Disponera | Disponera | Saknas | ![Stöds](../media/check-mark.png) | Saknas |
| Word | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) |
| Företags analys | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT | EJ TILLÄMPLIGT |
| Yammer | ![Stöds](../media/check-mark.png) | ![Stöds](../media/check-mark.png) | Disponera | Saknas | Disponera |

>[!NOTE]
><sup>1</sup> Edge för iOS och Android har stöd för certifikatbaserad äkthet under konto att lägga till flöden. Edge för iOS och Android stöder inte certifikatbaserad autentisering när autentisering utförs på webbplatser, som vanligt vis är intranäts webbplatser. <br><br>  I det här scenariot navigerar en användare till en webbplats (vanligt vis i intranätet) där användaren behöver verifiera via ett certifikat. Detta inbegriper inte modern lösenordsautentisering alls och påverkar inte ett Microsoft-autentiseringspaket. Detta beror på en begränsning med iOS: iOS hindrar tredjepartsprogram från att komma åt systemets nyckel Ring där certifikaten lagras (endast Apple-appar och en Safari- [webvisare](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) kan komma åt systemets nyckel Ring). <br><br> När Edge är beroende av webkit kan inte Edge komma åt systemets nyckel Ring och Visa användaren med ett certifikat val. Det här är en avsiktlig konstruktion på grund av appletens arkitektur.

## <a name="supported-powershell-modules"></a>PowerShell-moduler som stöds

- [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

