---
title: Office 365 ATP-säkra bilagor
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
description: Funktionen Säkra bilagor ger tidsklicka verifiering av e-postbilagor. Använd säkra bilagor för att skydda din organisation från skadliga filer som personer skickar eller tar emot via e-post.
ms.openlocfilehash: c95287b3dd05cce28bad6761ca7e69ce9cc2f914
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806803"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 ATP-säkra bilagor

## <a name="overview-of-office-365-atp-safe-attachments"></a>Översikt över Office 365 ATP-säkra bilagor

ATP-säkra bilagor (tillsammans med [ATP-säkra länkar)](atp-safe-links.md)är en del av [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). Funktionen BETRODDa bifogade filer i ATP kontrollerar om e-postbilagor är skadliga och vidtar sedan åtgärder för att skydda din organisation. Funktionen BETRODDA BIFOGADE FILER i ATP skyddar din organisation enligt [ATP-principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md) som har angetts av dina Globala Office 365-administratörer eller säkerhetsadministratörer.

ATP-skydd kan också utökas till filer i SharePoint Online, OneDrive för företag och Microsoft Teams. Mer information finns i [Office 365 Advanced Threat Protection for SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="how-to-get-atp-safe-attachments"></a>Så här får du ATP Safe Attachments

Kontrollera först att din prenumeration innehåller [avancerat hotskydd](office-365-atp.md). ATP ingår i prenumerationer, till exempel [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 A5, etc. Om din organisation har en Office 365-prenumeration som inte inkluderar Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i [Office 365 Advanced Threat Protection-abonnemang och priser](https://products.office.com/exchange/advance-threat-protection) och beskrivningen av office [365 Advanced Threat Protection Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Kontrollera sedan att dina principer för betrodda bifogade filer för ATP har definierats. (Se [Konfigurera principer för betrodda bifogade filer i Office 365](set-up-atp-safe-attachments-policies.md)) FUNKTIONERNA FÖR BETRODDA TILLBEHÖR är aktiva när:

- Principer för betrodda bifogade filer för ATP har konfigurerats. (Se [Konfigurera principer för betrodda bifogade filer i ATP i Office 365](set-up-atp-safe-attachments-policies.md).)

- Användare har loggat in på Office 365 med sitt arbets- eller skolkonto. (Se [Logga in på Office eller Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)

Om du vill definiera (eller redigera) ATP-principer måste du tilldelas en lämplig roll. Några exempel beskrivs i följande tabell:

|Roll|Var/hur tilldelad|
|---------|---------|
|Global administratör för Office 365|Personen som registrerar sig för att köpa Office 365 är som standard en global administratör. (Se [Om Office 365-administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) att lära sig mer.)|
|Säkerhetsadministratör|Administrationscenter för[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory ( )|
|Exchange Online Organisation Management|Administrationscenter[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)för Exchange ( ) <br>eller <br>  PowerShell-cmdlets (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Så här vet du om ATP Safe Attachments skydd är på plats

När du har [definierat (eller granskat) dina ATP Safe Attachments-principer](set-up-atp-safe-attachments-policies.md)kan du se hur tjänsten fungerar genom att [visa rapporter för avancerat hotskydd](view-reports-for-atp.md).

I följande tabell beskrivs några exempelscenarier. I alla dessa fall antar vi att organisationen har en Office 365-prenumeration som innehåller avancerat hotskydd.

|**Exempel på scenario**|**Gäller SKYDD FÖR ATP Safe Attachments i det här fallet?**|
|:-----|:-----|
|Pats organisation har Office 365 E5, men ingen har definierat några principer för ATP-säkra bilagor ännu.|Nej. Även om funktionen är tillgänglig måste minst en ATP-princip för säkra bilagor definieras för att ATP Safe Attachments-skyddet ska vara på plats.|
|Lee är anställd på försäljningsavdelningen på Contoso. Lees organisation har en ATP Safe Attachments-policy på plats som endast gäller för att finansiera anställda.|Nej. I det här fallet skulle ekonomianställda ha SKYDD FÖR ATP Safe Attachments, men andra anställda, inklusive försäljningsavdelningen, skulle inte förrän principer som inkluderar dessa grupper har definierats.|
|Igår, en Office 365-administratör på Jean organisation inrätta en ATP Safe Attachments princip som gäller för alla anställda. Tidigare idag fick Jean ett e-postmeddelande som innehåller en bifogad fil.|Ja. I det här exemplet har Jean en licens för avancerat hotskydd och en ATP Safe Attachments-princip som innehåller Jean har definierats. Det tar vanligtvis ungefär 30 minuter innan en ny princip börjar gälla mellan datacenter. eftersom det har gått en dag i detta fall bör politiken gälla.|
|Chris organisation har Office 365 E5 med ATP Safe Attachments principer på plats för alla i organisationen. Chris får ett e-postmeddelande som har en bifogad fil och vidarebefordrar meddelandet till andra som står utanför organisationen.|ATP Safe Attachments skydd är på plats för meddelanden som Chris får. Om mottagarnas organisationer också har principer för ATP-säkra bifogade filer, ska meddelandet om att Chris vidarebefordrar omfattas av dessa principer när det vidarebefordrade meddelandet anländer.|
|Jamies organisation har atp-principer för säkra bifogade filer på plats och [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) har aktiverats. Jamie förutsätter att varje fil i SharePoint Online har skannats och är säker att öppna eller ladda ner.|ATP Safe Attachments-skyddet finns enligt de principer som har definierats. Detta betyder dock inte att varenda fil i SharePoint Online, OneDrive för företag eller Microsoft Teams genomsöks. (Mer information finns i [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).)|

## <a name="submitting-files-for-malware-analysis"></a>Skicka filer för analys av skadlig kod

- Om du får en fil som du vill be Microsoft att analysera besöker du [Skicka en fil för analys av skadlig kod](https://aka.ms/wdsi/submit).

- Om du får ett [e-postmeddelande](enable-the-report-message-add-in.md)(med eller utan en bifogad fil) som du vill skicka till Microsoft för analys använder du tillägget Rapportmeddelande .
