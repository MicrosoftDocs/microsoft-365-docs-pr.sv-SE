---
title: Konfigurera principer för betrodda bifogade filer i Office 365
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
description: Definiera principer för betrodda bifogade filer för att skydda din organisation från skadliga filer i e-post.
ms.openlocfilehash: c5001823979c19ec68cd15a10bf7c2d7e54cae1d
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808988"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Konfigurera principer för betrodda bifogade filer i Office 365

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Advanced Threat Protection](office-365-atp.md). Om du är hemanvändare som letar efter information om säkra bilagor i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Personer skickar, tar emot och delar regelbundet bilagor, till exempel dokument, presentationer, kalkylblad med mera. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig bara genom att titta på ett e-postmeddelande. Och det sista du vill ha är en illvillig anknytning för att komma igenom, anställer förödelse för din organisation. Lyckligtvis kan [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) hjälpa. Du kan ställa in principer för ansvarar för [beskydd för beskydd för atp](atp-safe-attachments.md) för att säkerställa att din organisation skyddas mot attacker av osäkra e-postbilagor.

## <a name="what-to-do"></a>Vad man ska göra

1. Granska förutsättningarna

2. Konfigurera en ATP-princip för säkra bifogade filer

3. Läs mer om principalternativ för ATP-säkra bifogade filer

## <a name="step-1-review-the-prerequisites"></a>Steg 1: Granska förutsättningarna

- Kontrollera att din organisation har [Office 365 Advanced Threat Protection](office-365-atp.md).

- Kontrollera att du har de behörigheter som krävs. Om du vill definiera (eller redigera) ATP-principer måste du tilldelas antingen en roll för Exchange Online Organization Management (Office 365 Global Administrator tilldelas den här rollen som standard) eller både Exchange Online Hygiene Management och säkerhetsadministratörroller. Mer information finns i följande tabell:

  |||
  |---|---|
  |**Roll**|**Var/hur tilldelad**|
  |Global administratör för Office 365 |Personen som registrerar sig för att köpa Office 365 är som standard en global administratör. (Se [Om Office 365-administratörsroller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) att lära sig mer.)|
  |Säkerhetsadministratör |Administrationscenter för[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory ( )|
  |Exchange Online Organisation Management, Exchange Online Hygien Management |Administrationscenter[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)för Exchange ( ) <br>eller <br>  PowerShell-cmdlets (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|
  |

  Mer information om roller och behörigheter finns [i Behörigheter &amp; i Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- [Läs mer om principalternativ för ATP-säkra bifogade filer](#step-3-learn-about-atp-safe-attachments-policy-options) (i den här artikeln). Vissa alternativ, till exempel alternativen Övervaka eller Ersätt, kan resultera i en mindre fördröjning av e-post medan bilagor skannas. Om du vill undvika fördröjningar i meddelandet kan du överväga att använda [Dynamisk leverans och förhandsgranska](dynamic-delivery-and-previewing.md).

- Ge upp till 30 minuter innan den nya eller uppdaterade principen sprids till alla Office 365-datacenter.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Steg 2: Konfigurera (eller redigera) en ATP-princip för säkra bifogade filer

1. Gå [https://protection.office.com](https://protection.office.com) till och logga in med ditt arbets- eller skolkonto.

2. Välj &amp; **Principsäkra** \> **bifogade filer**i det vänstra navigeringsfönstret i Office 365 Security Compliance Center. **Threat management**

3. Om du ser **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**rekommenderar vi att du väljer det här alternativet. Detta aktiverar [Office 365 Advanced Threat Protection för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) för din Office 365-miljö.

4. Välj **Ny** (knappen Nytt liknar ett **+** plustecken ()) för att börja skapa principen.

5. Ange namn, beskrivning och inställningar för principen.<br/><br/>**Exempel:** Om du vill ställa in en princip som kallas "inga fördröjningar" som levererar allas meddelanden omedelbart och sedan återförkopplar bifogade filer efter att de har skannats kan du ange följande inställningar:

   - Skriv inga fördröjningar i rutan **Namn.**

   - Skriv en beskrivning som i rutan **Beskrivning,** skicka meddelanden direkt och återkoppla bifogade filer efter skanning.

   - Välj alternativet **Dynamisk leverans** i svarsavsnittet. (Läs[mer om dynamisk leverans och förhandsgranskning med ATP-säkra bilagor](dynamic-delivery-and-previewing.md).)

   - I avsnittet **Omdirigera bifogad fil** väljer du alternativet för att aktivera omdirigering och skriv e-postadressen för din globala Office 365-administratör, säkerhetsadministratör eller säkerhetsanalytiker som undersöker skadliga bilagor.

   - Välj **Mottagardomänen i**avsnittet **Tillämpad på** och välj sedan din domän. Välj **Lägg till**och välj sedan **OK**.

6. Välj **Save**.

Överväg att konfigurera flera principer för betrodda bifogade filer för ATP för din organisation. Dessa principer tillämpas i den ordning de visas på sidan **BETRODDa bifogade filer på ATP.** När en princip har definierats eller redigerats kan du tillåta att minst 30 minuter för polisen att träda i kraft i microsofts datacenter.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Steg 3: Lär dig mer om akuta-alternativ för säkra bifogade filer

När du ställer in dina atp-principer för säkra bilagor väljer du bland många alternativ, bland annat Övervaka, Blockera, Ersätt, Dynamisk leverans och så vidare. Om du undrar över vad dessa alternativ gör sammanfattar följande tabell var och dess effekt.

||||
|---|---|---|
|**Alternativet**|**Effekt**|**Använd när du vill:**|
|**Av**|Söker inte igenom bifogade filer för skadlig kod  <br/> Fördröjinte meddelandeleverans|Inaktivera skanning för skannrar, fax eller smarta värdar som bara skickar kända, bra bilagor  <br/> Förhindra onödiga fördröjningar i routning intern e-post.  <br/> **Vi rekommenderar inte det här alternativet för de flesta användare. Du bör bara använda det här alternativet för att stänga av ATP-säkra bilagor som söker efter en liten grupp betrodda avsändare.**|
|**Övervaka**|Levererar meddelanden med bilagor och spårar sedan vad som händer med upptäckt skadlig kod|Se vart upptäckt skadlig kod finns i organisationen|
|**Blockera**|Förhindrar att meddelanden med identifierade bifogade filer av skadlig kod fortsätter  <br/> Skickar meddelanden med upptäckt skadlig kod till [karantän i Office 365](manage-quarantined-messages-and-files.md) där en säkerhetsadministratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden  <br/> Blockerar framtida meddelanden och bilagor automatiskt|Skydda din organisation från upprepade attacker med samma bifogade filer av skadlig kod|
|**Ersätta**|Tar bort upptäckta bifogade filer för skadlig kod  <br/> Meddelar mottagarna att bifogade filer har tagits bort  <br/> Skickar meddelanden med upptäckt skadlig kod till [karantän i Office 365](manage-quarantined-messages-and-files.md) där en säkerhetsadministratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden|Öka synligheten för mottagare som bilagor har tagits bort på grund av upptäckt skadlig kod|
|**Dynamisk leverans**|Levererar meddelanden omedelbart  <br/> Ersätter bilagor med en platshållarfil tills skanningen är klar och återför sedan bilagorna om ingen skadlig kod upptäcks  <br/> Inkluderar förhandsgranskningsfunktioner för bifogade filer för de flesta PDF-filer och Office-filer under skanning  <br/> Skickar meddelanden med upptäckt skadlig kod till Karantän där en säkerhetsadministratör eller analytiker kan granska och släppa (eller ta bort) dessa meddelanden  <br/> [Lär dig mer om dynamisk leverans och förhandsgranskning med ATP-säkra bilagor](dynamic-delivery-and-previewing.md) <br/> |Undvik fördröjningar i meddelandet samtidigt som mottagare skyddas från skadliga filer  <br/> Gör det möjligt för mottagarna att förhandsgranska bifogade filer i felsäkert läge medan skanning pågår|
|**Aktivera omdirigering**|Gäller när alternativet Övervaka, Blockera eller Ersätt har valts  <br/> Skickar bilagor till en angiven e-postadress där säkerhetsadministratörer eller analytiker kan undersöka|Aktivera säkerhetsadministratörer och analytiker för att undersöka misstänkta bilagor|
|**Använd ovanstående val om skadlig kod söker efter uttider av bifogade filer eller fel inträffar**|Använder åtgärden som konfigurerats för unasfe-bilagor på de bifogade filer som inte kan skannas (på grund av timeout eller fel)|
|

## <a name="next-steps"></a>Nästa steg

När dina atp-principer för säkra bilagor är på plats kan du se hur ATP fungerar för din organisation genom att visa rapporter. Mer information finns i följande resurser:

- [Visa rapporter för Avancerad hotskydd i Office 365](view-reports-for-atp.md)

- [Använda Explorer i Säkerhets- & Compliance Center](threat-explorer.md)

Håll koll på nya funktioner som kommer till ATP. besök [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) och lär dig mer om [nya funktioner som läggs till i ATP](office-365-atp.md#new-features-in-office-365-atp).
