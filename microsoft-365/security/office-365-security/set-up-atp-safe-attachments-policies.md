---
title: Konfigurera principer för office 365 ATP-säkra bifogade filer
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
description: Läs mer om hur du definierar principer för säkra bifogade filer för att skydda din organisation från skadliga filer i e-post.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d826cb6e0dd4370a1e02722901d083d4f021e2b4
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588126"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Konfigurera principer för office 365 ATP-säkra bifogade filer

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hemanvändare och letar efter information om säkra bilagor i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Personer skickar, ta emot och delar regelbundet bifogade filer, till exempel dokument, presentationer, kalkylblad med mera. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig bara genom att titta på ett e-postmeddelande. Och det sista du vill ha är en skadlig bilaga för att komma igenom, vilket orsakar förödelse för din organisation. Lyckligtvis kan [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) hjälpa till. Du kan ställa in principer för [betrodda bilagor](atp-safe-attachments.md) för att säkerställa att din organisation skyddas mot attacker av osäkra e-postbilagor.

## <a name="what-to-do"></a>Vad du ska göra

1. Gå igenom förutsättningarna

2. Konfigurera en ATP-princip för säkra bilagor

3. Läs mer om alternativ för atp-säkra bifogade filer

## <a name="step-1-review-the-prerequisites"></a>Steg 1: Granska förutsättningarna

- Kontrollera att din organisation har [ett avancerat skydd mot Office 365.](office-365-atp.md)

- Kontrollera att du har de behörigheter som krävs. Om du vill definiera (eller redigera) ATP-principer måste du antingen tilldelas en Exchange Online Organization Management-roll (global administratör tilldelas den här rollen som standard) eller både Exchange Online Hygiene Management och Security Administrator roller. Mer information finns i följande tabell:

  |Roll|Var/hur tilldelas|
  |---------|---------|
  |global administratör |Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Läs [mer om Microsoft 365-administratörsroller.)](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
  |Säkerhetsadministratör |Administrationscenter för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
  |Exchange Online Organisation Management, Exchange Online Hygien Management |Administrationscenter för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|
  |

  Mer information om roller och behörigheter finns [i Behörigheter i &amp; Säkerhetsefterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- [Läs mer om alternativ för atp-säkra bifogade filer](#step-3-learn-about-atp-safe-attachments-policy-options) (i den här artikeln). Vissa alternativ, till exempel alternativen Bildskärm eller Ersätt, kan leda till en mindre fördröjning av e-post medan bifogade filer genomsöks. Om du vill undvika meddelandeförseningar bör du överväga att använda [dynamisk leverans och förhandsgranska](dynamic-delivery-and-previewing.md).

- Tillåt upp till 30 minuter innan den nya eller uppdaterade principen sprids till alla Microsoft 365-datacenter.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Steg 2: Konfigurera (eller redigera) en ATP-princip för säkra bilagor

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets- eller skolkonto.

2. Välj &amp; **Principsäkra** bilagor i det vänstra **Threat management**navigeringsfönstret i det vänstra \> **navigeringsfönstret.**

3. Om du ser **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**rekommenderar vi att du väljer det här alternativet. Detta aktiverar [Office 365 Advanced Threat Protection för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) för din Microsoft 365-miljö.

4. Välj **Ny** (knappen Ny liknar ett plustecken ( **+** )) för att börja skapa din princip.

5. Ange namn, beskrivning och inställningar för principen.<br/><br/>**Exempel:** Om du vill ställa in en princip som kallas "inga fördröjningar" som levererar allas meddelanden omedelbart och sedan sätter i lösningar igen när de har skannats kan du ange följande inställningar:

   - Skriv inga fördröjningar i rutan **Namn.**

   - Skriv en beskrivning i rutan **Beskrivning** som, Levererar meddelanden omedelbart och fäster fasten igen efter skanning.

   - Välj alternativet **Dynamisk leverans** i svarsavsnittet. (Läs[mer om dynamisk leverans och förhandsgranskning med ATP Säkra bilagor](dynamic-delivery-and-previewing.md).)

   - I avsnittet **Omdirigera bifogad fil** väljer du alternativet att aktivera omdirigering och skriver e-postadressen till den globala administratören, säkerhetsadministratören eller säkerhetsanalytikern som undersöker skadliga bilagor.

   - I avsnittet **Tillämpad på** väljer du **Den mottagande domänen är**och väljer sedan din domän. Välj **Lägg till**och välj sedan **OK**.

6. Välj **Save**.

Överväg att ställa in flera ATP-principer för säkra bilagor för din organisation. Dessa principer tillämpas i den ordning de visas på sidan BETRODDa bilagor med **ATP.** När en princip har definierats eller redigerats tillåter du minst 30 minuter för att polisen ska börja gälla i hela Microsoft-datacenter.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Steg 3: Lär dig mer om alternativ för ATP-säkra bilagor

När du ställer in principerna för betrodda bilagor vid ATP väljer du bland många alternativ, till exempel Övervaka, Blockera, Ersätt, Dynamisk leverans och så vidare. Om du undrar vad dessa alternativ gör sammanfattar följande tabell varje och dess effekt.

||||
|---|---|---|
|**Alternativ**|**Effekt**|**Använd när du vill:**|
|**Av**|Söker inte igenom bilagor efter skadlig kod  <br/> Försenar inte meddelandeleverans|Inaktivera skanning för skannrar, fax eller smarta värdar som bara skickar kända, bra bilagor  <br/> Förhindra onödiga fördröjningar i routning av intern e-post.  <br/> **Vi rekommenderar inte det här alternativet för de flesta användare. Du bör bara använda det här alternativet för att inaktivera ATP-säkra bilagor som söker efter en liten grupp betrodda avsändare.**|
|**Övervaka**|Levererar meddelanden med bilagor och spårar sedan vad som händer med upptäckt skadlig kod|Se var upptäckt skadlig kod hamnar i organisationen|
|**Blockera**|Förhindrar att meddelanden med identifierade bifogade filer för skadlig kod fortsätter  <br/> Skickar meddelanden med upptäckt skadlig kod till [karantän i Office 365](manage-quarantined-messages-and-files.md) där en säkerhetsadministratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden  <br/> Blockerar framtida meddelanden och bilagor automatiskt|Skydda din organisation från upprepade attacker med samma bifogade skadliga program|
|**Ersätta**|Tar bort identifierade bifogade skadliga program  <br/> Meddelar mottagarna att bifogade filer har tagits bort  <br/> Skickar meddelanden med upptäckt skadlig kod till [karantän i Office 365](manage-quarantined-messages-and-files.md) där en säkerhetsadministratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden|Öka synligheten för mottagare av att bifogade filer har tagits bort på grund av upptäckt skadlig kod|
|**Dynamisk leverans**|Levererar meddelanden omedelbart  <br/> Ersätter bifogade filer med en platshållarfil tills skanningen är klar och fäster sedan fast bilagorna igen om ingen skadlig kod upptäcks  <br/> Inkluderar förhandsgranskningsfunktioner för bifogade filer för de flesta PDF-filer och Office-filer under skanningen  <br/> Skickar meddelanden med upptäckt skadlig kod till Karantän där en säkerhetsadministratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden  <br/> [Lär dig mer om dynamisk leverans och förhandsgranskning med ATP Säkra bilagor](dynamic-delivery-and-previewing.md) <br/> |Undvik meddelandefördröjningar samtidigt som mottagare skyddas från skadliga filer  <br/> Gör det möjligt för mottagarna att förhandsgranska bifogade filer i felsäkert läge medan skanningen sker|
|**Aktivera omdirigering**|Gäller när alternativet Bildskärm, Blockera eller Ersätt är valt  <br/> Skickar bilagor till en angiven e-postadress där säkerhetsadministratörer eller analytiker kan undersöka|Aktivera säkerhetsadministratörer och analytiker för att undersöka misstänkta bilagor|
|**Använd ovanstående val om malware scanning för bilagor time out eller fel inträffar**|Tillämpar åtgärden som konfigurerats för osäkra bilagor till de bifogade filer som inte kan skannas (på grund av time out eller error)|
|

## <a name="next-steps"></a>Nästa steg

När dina ATP-principer för säkra bilagor är på plats kan du se hur ATP fungerar för din organisation genom att visa rapporter. Läs följande resurser om du vill veta mer:

- [Visa rapporter för avancerat hotskydd för Office 365](view-reports-for-atp.md)

- [Använda Explorer i Security & Compliance Center](threat-explorer.md)

Håll koll på nya funktioner som kommer till ATP. besök [Översikten över Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) och lär dig mer om [nya funktioner som läggs till i ATP](office-365-atp.md#new-features-in-office-365-atp).
