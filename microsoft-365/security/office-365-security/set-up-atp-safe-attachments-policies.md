---
title: Konfigurera Office 365-principer för säkra bifogade filer
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Lär dig hur du definierar principer för säkra bifogade filer för att skydda din organisation från skadliga filer via e-post.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5f9f1a6cc250fdd336e48c19c6cb5d73e9a05800
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197229"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Konfigurera Office 365-principer för säkra bifogade filer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hem användare letar efter information om säkra bifogade filer i Outlook kan du läsa mer i [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Personer skickar, tar emot och delar ut bifogade filer regelbundet, till exempel dokument, presentationer, kalkyl blad och annat. Det är inte alltid enkelt att berätta om en bifogad fil är säker eller skadlig genom att titta i ett e-postmeddelande. Och det sista du vill ha är en skadlig bifogad fil som wreaking Havoc för din organisation. Som tur är kan [Office 365 Avancerat skydd](office-365-atp.md) (ATP) vara till hjälp. Du kan ställa in principer för säker åtkomst till [ATP](atp-safe-attachments.md) för att säkerställa att organisationen skyddas mot attacker via osäkra e-postbilagor.

## <a name="what-to-do"></a>Vad kan jag göra?

1. Granska kraven

2. Konfigurera en policy för säkrade säkerhets meddelanden för ATP

3. Läs mer om princip alternativ för säker användning av ATP

## <a name="step-1-review-the-prerequisites"></a>Steg 1: granska kraven

- Kontrol lera att din organisation har [Office 365 Avancerat skydd för hotet](office-365-atp.md).

- Se till att du har nödvändig behörighet. Om du vill definiera (eller redigera) ATP-principer måste du ha tilldelats antingen rollen som organisations hantering för Exchange Online (global administratör är tilldelad till den här rollen) eller båda rollerna för Exchange Online hygien hantering och säkerhets administratörer. Mer information finns i följande tabell:

  ****

  |Roll|Där/hur kopplat|
  |---|---|
  |global administratör |Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
  |Säkerhets administratör |Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
  |Exchange Online-organisations hantering, Exchange Online hygien hantering |Administrations Center för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
  |

  Mer information om roller och behörigheter finns i [behörigheter i Center för säkerhets &amp; kontroll](permissions-in-the-security-and-compliance-center.md).

- [Läs mer om princip alternativ för säker](#step-3-learn-about-atp-safe-attachments-policy-options) användning av ATP (i den här artikeln). Vissa alternativ, till exempel alternativen bildskärm och ersätta, kan resultera i en mindre fördröjning av e-postmeddelanden medan bilagor skannas. Överväg att använda [dynamisk leverans och förhands granskning](dynamic-delivery-and-previewing.md)för att undvika fördröjningar för meddelanden.

- Tillåt upp till 30 minuter för att den nya eller uppdaterade principen ska spridas till alla Microsoft 365-datacenter.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Steg 2: Konfigurera (eller redigera) en policy för säkerhets meddelanden för ATP

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets-eller skol konto.

2. I &amp; det vänstra navigerings fönstret i Center för säkerhets kontroll väljer du **princip** säkra bilagor under **Threat Management** \> **Safe Attachments**.

3. Om du ser **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**rekommenderar vi att du väljer det här alternativet. Detta aktiverar [Office 365 Avancerat skydd för SharePoint-, OneDrive-och Microsoft Teams](atp-for-spo-odb-and-teams.md) för din Microsoft 365-miljö.

4. Välj **nytt** (knappen Ny ser ut som ett plus tecken ( **+** )) för att börja skapa din princip.

5. Ange namn, beskrivning och inställningar för policyn.<br/><br/>**Exempel:** Om du vill konfigurera en princip med namnet "ingen fördröjning" som levererar allas meddelanden omedelbart och sedan bifogar bilagor igen efter att de skannats kan du ange följande inställningar:

   - I rutan **namn** skriver du inga fördröjningar.

   - I rutan **Beskrivning** skriver du en beskrivning, till exempel skickar meddelanden direkt och bifogar bilagor igen efter skanningen.

   - I avsnittet svar väljer du alternativet **dynamisk leverans** . ([Läs mer om dynamisk leverans och för hands Visa med säkra bilagor från ATP](dynamic-delivery-and-previewing.md).)

   - I avsnittet **omdirigera bilaga** väljer du alternativet för att aktivera omdirigera och skriv e-postadressen till din globala administratör, säkerhets administratör eller säkerhetsanalytiker som kommer att undersöka skadliga bifogade filer.

   - I avsnittet **används** väljer **du mottagar domänen**och sedan din domän. Välj **Lägg till**och sedan **OK**.

6. Välj **Save**.

Överväg att ange fler principer för säkerhets meddelanden i flera ATP för din organisation. Dessa principer tillämpas i den ordning som de visas på sidan för **säkra bifogade ATP-filer** . När en princip har definierats eller redigerats kan du låta minst 30 minuter för polisen genomföras i Microsoft Data Center.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Steg 3: Lär dig mer om alternativ för att skydda ATP-filer

När du skapar principer för säkra bifogade filer via ATP väljer du bland många olika alternativ, till exempel övervaka, blockera, ersätta, dynamisk leverans och så vidare. Om du undrar över vad dessa alternativ gör, sammanfattar följande tabell och dess effekt.

****

|Alternativ|Fungerar|Använd när du vill:|
|---|---|---|
|**Av**|Söker inte igenom bifogade filer för skadlig kod  <br/> Fördröj inte leverans av meddelanden|Inaktivera inaktive avsökning för markerade mottagare.  <br/> Förhindra onödiga fördröjningar i routning av intern e-post.  <br/> **Det här alternativet rekommenderas inte för de flesta användare. Du bör bara använda det här alternativet om du vill inaktivera sökningar efter ATP-säkra bilagor för mottagare som bara får e-post från betrodda avsändare.**|
|**Övervaka**|Skickar meddelanden med bifogade filer och följer sedan upp vad som händer med identifierad skadlig kod|Se var upptäckta skadlig kod hamnar i din organisation|
|**Blockera**|Förhindrar att meddelanden med upptäckta bilagor för skadlig kod fortsätter  <br/> Skickar meddelanden med identifierat skadlig kod till [karantän i Office 365](manage-quarantined-messages-and-files.md) där en säkerhets administratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden  <br/> Blockerar framtida meddelanden och bilagor automatiskt|Skydda din organisation från upprepade attacker med samma skadliga program vara|
|**Byter**|Tar bort identifierade bifogade filer  <br/> Meddelar mottagare om att bifogade filer har tagits bort  <br/> Skickar meddelanden med identifierat skadlig kod till [karantän i Office 365](manage-quarantined-messages-and-files.md) där en säkerhets administratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden|Öka synligheten för mottagarna att bifogade filer har tagits bort på grund av upptäckt skadlig kod|
|**Dynamisk leverans**|Skickar meddelanden omedelbart  <br/> Ersätter bifogade filer med en plats hållare tills genomsökningen är klar och bifogar sedan bilagor igen om ingen skadlig kod hittas  <br/> Inkluderar funktioner för förhands granskning av bifogade filer för de flesta PDF-och Office-filer under genomsökning  <br/> Skickar meddelanden med identifierat skadlig kod till karantän där en säkerhets administratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden  <br/> [Lär dig mer om dynamisk leverans och förhands granskning med säkra filer för ATP](dynamic-delivery-and-previewing.md) <br/> |Undvik meddelande fördröjningar när du skyddar mottagare från skadliga filer  <br/> Aktivera användare för att förhandsgranska bifogade filer i fel säkert läge när genomsökning sker|
|**Aktivera omdirigering**|Gäller när alternativet övervaka, blockera eller Ersätt är markerat  <br/> Skickar bifogade filer till en viss e-postadress där säkerhets administratörer och analytiker kan undersöka|Aktivera säkerhets administratörer och analytiker för att undersöka misstänkta bilagor|
|**Använda ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel uppstår**|Tillämpar åtgärden som har kon figurer ATS för osäkra bifogade filer i bifogade filer som inte kan gås igenom (på grund av timeout eller fel)|
|

## <a name="next-steps"></a>Nästa steg

När dina principer för säkerhets meddelanden via ATP är på plats kan du se hur ATP fungerar för organisationen genom att visa rapporter. Mer information finns i följande resurser:

- [Visa rapporter för Office 365 Avancerat skydd](view-reports-for-atp.md)

- [Använda Utforskaren i säkerhets & Compliance Center](threat-explorer.md)

Håll koll på nya funktioner som kommer till ATP. Besök [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) och Läs mer om [nya funktioner som läggs till i ATP](office-365-atp.md#new-features-in-office-365-atp).
