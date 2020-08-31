---
title: Säkra ATP-länkar
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: I den här artikeln får du lära dig hur du använder säkra Länkar för att skydda din organisation från nätfiske och andra attacker.
ms.openlocfilehash: d9b3c981cb282c286a5b6edcea367c8c57ffd4d3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307643"
---
# <a name="atp-safe-links"></a>Säkra ATP-länkar

## <a name="overview-of-office-365-atp-safe-links"></a>Översikt över Office 365 säkerhets Länkar för ATP

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du använder Outlook.com, Microsoft 365 eller Microsoft 365 personal och du letar efter information om säkra länkar i Outlook kan du läsa mer i [avancerad Outlook.com-säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 ATP-säkra länkar (ingår i [Office 365 Avancerat skydd](office-365-atp.md)) kan skydda din organisation genom att ange inloggnings kontroll för webb adresser (URL: er) i [e-postmeddelanden](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) och [Office-dokument](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents). Skydd definieras genom [principer för säkra länkar i ATP](set-up-atp-safe-links-policies.md) som anges av din Microsoft 365-säkerhetsgrupp.

När du har gjort dina principer för säkra anslutningar för ATP kan du [Visa rapporter för avancerat skydd](view-reports-for-atp.md). Informationen i dessa rapporter kan hjälpa din säkerhets grupp att vidta ytterligare åtgärder för att skydda din organisation eller Research om säkerhets tillbud.

När [nya funktioner läggs till i ATP](office-365-atp.md#new-features-in-office-365-atp)kan din Microsoft 365-säkerhetsgrupp lägga till eller redigera organisationens [principer för Safet ATP-länkar](set-up-atp-safe-links-policies.md). Dessutom kan du lägga till ändringar och förbättringar, till exempel våra nyligen reviderade [varnings sidor](atp-safe-links-warning-pages.md) och automatisk rendering av inbyggda länkar i Outlook (som introduceras i Microsoft 365-appar för enterprise version 1809).

## <a name="how-to-get-atp-safe-links-protection"></a>Så här får du säkerhet för säkerhet för ATP

**Först kontrollerar du att ditt abonnemang innehåller [Office 365 Avancerat skydd](office-365-atp.md) ** Abonnemang 1 eller abonnemang 2. Office 365 ATP ingår i abonnemang, till exempel [Microsoft 365 Enterprise, E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise, E5, Office 365 Education A5, etc. Om din organisation har en Microsoft 365-prenumeration som inte innehåller Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i följande resurser: 

- [Office 365-abonnemang och priser för avancerat skydd](https://products.office.com/exchange/advance-threat-protection)

- [Beskrivning av Office 365 Avancerat skydds tjänst](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

**Kontrol lera sedan att dina principer för Safet ATP-länkar är definierade**. (Se [Konfigurera Office 365-principer för säkra Länkar för ATP](set-up-atp-safe-links-policies.md).) Funktioner för Safet ATP-länkar är aktiva när:

- Principer för Safet ATP-länkar är inställda för e-post och för Office-dokument. (Mer information finns i [Konfigurera policys för säkra Länkar för ATP](set-up-atp-safe-links-policies.md).)

- Microsoft 365-klientprogram är konfigurerade att använda modern (Detta gäller för säkra anslutningar för säkerhets säkerhet i Office-dokument). (Se [modern verifikation för Office 2016](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).)

- Användare har loggat in med sitt arbets-eller skol konto. (Mer information finns i [Logga in på Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).)

- Din organisations e-postadress passerar genom Exchange Online Protection.

**Kontrol lera också att du har nödvändig behörighet**. Om du vill definiera (eller redigera) ATP-principer måste du ha en lämplig roll. Några exempel beskrivs i följande tabell:

****

|Roll|Där/hur kopplat|
|---|---|
|global administratör|Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Säkerhets administratör|Azure Active Directory-administratörs Center ( <https://aad.portal.azure.com> )|
|Organisations hantering i Exchange Online|Administrations Center för Exchange ( <https://outlook.office365.com/ecp> ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Så här kontrollerar du att skydda säkerhets Länkar för ATP

Som global administratör eller säkerhets administratör är det viktigt att granska dina [principer för säkerhet per ATP](set-up-atp-safe-links-policies.md) regelbundet. Principer för Safet ATP-länkar avgör om skydd gäller endast för hyperlänkar i e-postmeddelanden eller till URL: er i Office-dokument.

Efter att principer för säkra Länkar för ATP är på plats kan din organisations säkerhets team se hur skydd mot ATP Safe Links fungerar för din organisation genom att [Visa rapporter för avancerat skydd](view-reports-for-atp.md).

## <a name="example-scenarios"></a>Exempel scenarier

I följande tabell beskrivs några exempel scenarier där säkra Länkar för ATP kan vara på plats. (I alla de här fallen antar vi att organisationen har Office 365 Enterprise, E5.)

****

|Exempel på scenario|Gäller det säkraste säkerhets problemet i ATP?|
|---|---|
|Jean är en medlem i en grupp med principer för Safet ATP-länkar som omfattar URL-adresser i e-post och Office-dokument. Jean öppnar en PowerPoint-presentation som någon har skickat och klickar sedan på en URL i presentationen.|Ja. De principer för Safet ATP-länkar som är definierade för Jean grupp, Jean och Word-, Excel-, PowerPoint-eller Visio-dokument som Jean öppnas, så länge Jean är inloggat och använder Microsoft 365-appar för företag på Windows-, iOS-eller Android-enheter.|
|I Chris organisation har inga globala eller säkerhets administratörer några principer för Safet ATP-länkar ännu. Chris får ett e-postmeddelande som innehåller en URL till en illasinnad webbplats. Chris är inte på att webb adressen är skadlig och klickar på länken.|Nej. Standard principen som täcker URL: er för alla i organisationen måste definieras för att skydd ska kunna användas.|
|I Pat organisation har ingen global eller säkerhets administratör definierat eller redigerat några principer för Safet ATP-länkar än. Pat öppnar ett Word-dokument och klickar på en URL i filen.|Nej. En princip som innehåller Office-dokument måste definieras för att skydd ska kunna användas. Se [Konfigurera principer för säkra säkerhets Länkar för ATP i Office 365](set-up-atp-safe-links-policies.md).|
|Aaron Lee organisation har en policy för Safet ATP-länkar som har en `https://tailspintoys.com` lista över blockerade webbplatser. Aaron Lee får ett e-postmeddelande som innehåller en URL till `https://tailspintoys.com/aboutus/trythispage` . Aaron Lee klickar på URL-adressen.|Det beror på om hela webbplatsen och alla dess under sidor ingår i listan med blockerade URL: er. Se [Konfigurera en anpassad lista över blockerade URL-adresser med säkerhet för ATP](set-up-a-custom-blocked-urls-list-atp.md).|
|Janne, Jean ' s kollega, skickar ett e-postmeddelande till Jean, och vet inte att e-postmeddelandet innehåller en skadlig URL.|Det beror på om principer för Safet ATP-länkar är definierade för e-post som skickas inom organisationen. Se [Konfigurera principer för säkra säkerhets Länkar för ATP i Office 365](set-up-atp-safe-links-policies.md).|
|
