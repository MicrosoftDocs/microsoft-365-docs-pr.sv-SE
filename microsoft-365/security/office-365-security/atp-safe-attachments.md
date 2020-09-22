---
title: Säkra filer för ATP
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
description: I den här artikeln får du lära dig mer om funktionen för säker åtkomst för varje ATP för Office 365 och hur du får till gång till prenumerationen.
ms.openlocfilehash: 1ff7021f1c9fa64d3f04cbcac7231733399ad2b8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198781"
---
# <a name="atp-safe-attachments"></a>Säkra filer för ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="overview-of-office-365-atp-safe-attachments"></a>Översikt över Office 365 ATP-säkra bifogade filer

ATP-säkra bifogade filer (tillsammans med [säkra anslutningar för ATP](atp-safe-links.md)) är en del av [Office 365 Avancerat skydd](office-365-atp.md) (ATP). Det säkraste alternativet för att se om e-postbilagor är skadliga och vidtar åtgärder för att skydda din organisation. Det säkraste alternativet för att skydda via säkerhets meddelanden skyddar din organisation enligt [principer för säkert bifogade filer för ATP](set-up-atp-safe-attachments-policies.md) som anges av din globala eller dina administratörer.

ATP-skydd kan även utökas till filer i SharePoint Online, OneDrive för företag och Microsoft Teams. Mer information finns i [Office 365 Avancerat skydd för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="how-to-get-atp-safe-attachments"></a>Skaffa säkra filer för ATP

Kontrol lera först att ditt abonnemang inkluderar [Avancerat skydd](office-365-atp.md). ATP ingår i abonnemang, till exempel [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 A5, etc. Om din organisation har en Microsoft 365-prenumeration som inte innehåller Office 365 ATP kan du eventuellt köpa ATP som ett tillägg. Mer information finns i Office 365-prenumerationer [och priser för avancerade hot skydd](https://products.office.com/exchange/advance-threat-protection) samt [Office 365-beskrivningen för avancerat skydd för hotet](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Se sedan till att dina principer för säkerhet via ATP har definierats. (Se [Konfigurera Office 365-principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md)) De säkraste bilage funktionerna är aktiva när:

- Principer för säker säkerhet för ATP är inställda. (Mer information finns i [Konfigurera principer för säkra bifogade säkerhets meddelanden i Office 365](set-up-atp-safe-attachments-policies.md).)

- Användare har loggat in med sitt arbets-eller skol konto. (Mer information finns i [Logga in på Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).)

Om du vill definiera (eller redigera) ATP-principer måste du ha en lämplig roll. Några exempel beskrivs i följande tabell:

|Roll|Där/hur kopplat|
|---|---|
|global administratör|Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Säkerhets administratör|Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Organisations hantering i Exchange Online|Administrations Center för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Så här vet du om säkerhet för säkerhet för säkerhets skull är på plats

När du har [definierat (eller granskat) dina principer för säkrat ATP-filer](set-up-atp-safe-attachments-policies.md), ett bra sätt att se hur tjänsten fungerar är [att visa rapporter för avancerat skydd](view-reports-for-atp.md).

I följande tabell beskrivs några exempel scenarier. I alla de här fallen antar vi att organisationen har en Microsoft 365-prenumeration som innehåller Avancerat skydd.

****

|Exempel på scenario|Gäller säkerhetslovade skydd mot bifogade filer i det här fallet?|
|---|---|
|Pat organisation har Office 365 E5, men ingen har definierat några principer för betrodda ATP-filer.|Nej. Även om funktionen är tillgänglig måste minst en policy för säkerhet för flera säkerhets meddelanden per ATP vara definierad för att skydda säkerheten för tillgängligt.|
|Aaron Lee är en anställd på försäljnings avdelningen på contoso. Aaron Lee organisation har en policy för säker fil för ATP som gäller endast för ekonomiska medarbetare.|Nej. I det här fallet skulle de anställda ha ATP Safe Attachments, men andra anställda, inklusive försäljnings avdelningen, är inte förrän policyerna som innehåller dessa grupper har definierats.|
|Igår, en administratör på Jean organisation som har en policy för säkerhet för ATP som gäller för alla anställda. Tidigare i dag fick Jean fått ett e-postmeddelande som innehåller en bifogad fil.|Ja. I det här exemplet har Jean en licens för avancerat skydd och en princip för säker användning av ATP med Jean har definierats. Det tar vanligt vis ungefär 30 minuter innan en ny princip börjar gälla i data centers. eftersom en dag har gått i det här fallet ska policyn vara aktiv.|
|Chris organisation har Office 365 E5 med principer för säker bifogad fil med ATP för alla i organisationen. Chris får ett e-postmeddelande som innehåller en bifogad fil och vidarebefordrar meddelandet till andra personer utanför organisationen.|Säkerhet för ATP-säkerhet är på plats för meddelanden som Chris tar emot. Om mottagarnas organisationer också har principer för säkra bifogade filer (ATP), kommer meddelandet som Chris skickar tillbaka till dessa principer när det vidarebefordrade meddelandet anländer.|
|Jannes organisation har principer för säkert bifogade filer på plats och [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) har Aktiver ATS. Janne antar att alla filer i SharePoint Online har skannats och är säkra att öppna eller ladda ner.|Säkerhet för säkerhet per ATP är på plats enligt de principer som är definierade; men det betyder inte att alla filer i SharePoint Online, OneDrive för företag eller Microsoft Teams skannas. (Mer information finns i [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).)|
|

## <a name="submitting-files-for-malware-analysis"></a>Skicka filer för analys av skadlig program vara

- Om du får en fil som du vill be Microsoft att analysera kan du besöka [skicka en fil för analys av skadlig program vara](https://aka.ms/wdsi/submit).

- Om du får ett e-postmeddelande (med eller utan en bifogad fil) som du vill skicka till Microsoft för analys kan du läsa [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).
