---
title: ATP säkra bilagor
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om funktionen BETRODDa bifogade filer för Office 365 och hur du skaffar funktionen för din prenumeration.
ms.openlocfilehash: 75b047c1761a936f1fb0e08c65d9c270a136a953
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588306"
---
# <a name="atp-safe-attachments"></a>ATP säkra bilagor

## <a name="overview-of-office-365-atp-safe-attachments"></a>Översikt över office 365 ATP-säkra bilagor

ATP Safe Attachments (tillsammans med [ATP Safe Links)](atp-safe-links.md)är en del av [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). Funktionen Betrodda bifogade filer i ATP kontrollerar om e-postbilagor är skadliga och vidtar sedan åtgärder för att skydda din organisation. Funktionen BETRODDa bifogade filer för ATP skyddar din organisation enligt [ATP:s principer för säkra bilagor](set-up-atp-safe-attachments-policies.md) som anges av dina globala administratörer eller säkerhetsadministratörer.

ATP-skydd kan också utökas till filer i SharePoint Online, OneDrive för företag och Microsoft Teams. Mer information finns i [Det avancerade skydd mot Office 365 för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="how-to-get-atp-safe-attachments"></a>Så här får du ATP Säkra bilagor

Kontrollera först att din prenumeration innehåller [avancerat skydd mot hot](office-365-atp.md). ATP ingår i prenumerationer, till exempel [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business Premium,](https://www.microsoft.com/microsoft-365/business)Office 365 E5, Office 365 A5 osv. Om din organisation har en Microsoft 365-prenumeration som inte innehåller Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i [Office 365 Advanced Threat Protection-abonnemang och priser](https://products.office.com/exchange/advance-threat-protection) och beskrivningen av Office [365 Advanced Threat Protection Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Kontrollera sedan att principerna för betrodda bilagor för ATP har definierats. (Se Konfigurera principer för [betrodda bilagor i Office 365 )](set-up-atp-safe-attachments-policies.md) ATP-funktioner för säkra bilagor är aktiva när:

- ATP Principer för säkra bifogade filer har ställts in. (Se Konfigurera principer för [betrodda bifogade filer i Office 365](set-up-atp-safe-attachments-policies.md).)

- Användare har loggat in med sitt arbets- eller skolkonto. (Se [Logga in på Office eller Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)

Om du vill definiera (eller redigera) ATP-principer måste du tilldelas en lämplig roll. Några exempel beskrivs i följande tabell:

|Roll|Var/hur tilldelas|
|---------|---------|
|global administratör|Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Läs [mer om Microsoft 365-administratörsroller.)](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Säkerhetsadministratör|Administrationscenter för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Hantering av Exchange Online-organisation|Administrationscenter för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Hur man vet om ATP Säkra bilagor skydd är på plats

När du har [definierat (eller granskat) dina ATP-principer för säkra bilagor](set-up-atp-safe-attachments-policies.md)är ett bra sätt att se hur tjänsten fungerar genom att [visa rapporter för avancerat skydd mot hot](view-reports-for-atp.md).

I följande tabell beskrivs några exempelscenarier. I alla dessa fall antar vi att organisationen har en Microsoft 365-prenumeration som innehåller avancerat skydd mot hot.

|**Exempel scenario**|**Gäller atp-skydd för säkra bilagor i det här fallet?**|
|:-----|:-----|
|Pats organisation har Office 365 E5, men ingen har definierat några principer för ATP Safe Attachments ännu.|Nej. Även om funktionen är tillgänglig måste minst en ATP-princip för säkra bilagor definieras för att ATP-skydd för säkra bilagor ska vara på plats.|
|Lee är anställd på försäljningsavdelningen på Contoso. Lees organisation har en ATP Safe Attachments-policy som endast gäller ekonomianställda.|Nej. I det här fallet skulle ekonomianställda ha ATP Safe Attachments skydd, men andra anställda, inklusive försäljningsavdelningen, skulle inte förrän principer som innehåller dessa grupper har definierats.|
|Igår, en administratör på Jean organisation inrätta en ATP säkra bilagor princip som gäller för alla anställda. Tidigare idag fick Jean ett e-postmeddelande som innehåller en bifogad fil.|Ja. I det här exemplet har Jean en licens för avancerat skydd mot hot och en ATP-princip för säkra bilagor som innehåller Jean har definierats. Det tar vanligtvis cirka 30 minuter innan en ny princip börjar gälla över datacenter. eftersom en dag har gått i detta fall bör politiken vara i kraft.|
|Chris organisation har Office 365 E5 med ATP Safe Attachments-principer för alla i organisationen. Chris får ett e-postmeddelande som har en bifogad fil och vidarebefordrar meddelandet till andra som befinner sig utanför organisationen.|ATP-skydd för säkra bilagor finns på plats för meddelanden som Chris tar emot. Om mottagarnas organisationer också har ATP-principer för säkra bilagor på plats, kommer meddelandet att Chris vidarebefordrar att omfattas av dessa principer när det vidarebefordrade meddelandet anländer.|
|Jamies organisation har ATP-principer för säkra bifogade filer på plats och [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) har aktiverats. Janne förutsätter att alla filer i SharePoint Online har skannats och är säker att öppna eller ladda ned.|ATP-skydd för säkra bilagor finns på plats enligt de principer som har definierats. Detta innebär dock inte att varenda fil i SharePoint Online, OneDrive för företag eller Microsoft Teams genomsöks. (Mer information finns i [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).)|

## <a name="submitting-files-for-malware-analysis"></a>Skicka filer för analys av skadlig kod

- Om du får en fil som du vill be Microsoft att analysera besöker du [Skicka en fil för analys av skadlig kod](https://aka.ms/wdsi/submit).

- Om du får ett e-postmeddelande (med eller utan en bifogad fil) som du vill skicka till Microsoft för analys läser du [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).
