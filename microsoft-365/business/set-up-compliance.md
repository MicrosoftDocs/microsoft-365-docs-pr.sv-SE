---
title: Öka hotet mot skyddet för Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Konfigurera kompatibla funktioner för att förhindra förlust av data och hålla dina kunder känslig information.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841182"
---
# <a name="set-up-compliance-features"></a>Konfigurera funktioner för efterlevnad

Ditt Microsoft 365 Business Premium innehåller funktioner för att skydda dina data och enheter och hjälper dig att hålla dina kunder känslig information.

## <a name="set-up-dlp-features"></a>Konfigurera DLP-funktioner

Se [skapa en DLP-princip från en mall](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) för ett exempel på hur du konfigurerar en princip som skyddar mot att skydda person uppgifter. 
  
DLP innehåller många färdiga principmallar för många olika språk. Till exempel, ekonomiska data för Australien, privat person uppgifter och så vidare. Se [vad mallarna för DLP-principer innehåller](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) för en fullständig lista. Alla de här mallarna kan aktive ras på liknande sätt som i mallen PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Konfigurera e-postlagring med Exchange Online-arkivering

 Licenser för **Exchange Online-arkivering** hjälper till att upprätthålla efterlevnad och myndighets standarder genom att bevara e-postinnehåll för eDiscovery. Den minskar också risken för att du har en rättegång och ger ett sätt att återställa data efter en säkerhets överträdelse eller när du behöver återställa borttagna objekt. Du kan använda behållning för att bevara all en användares innehåll eller använda bevarande principer för att anpassa vad du vill behålla.
  
**Rättsliga undantag:** Du kan bevara allt innehåll i post lådan inklusive borttagna objekt genom att ange användarens hela post låda. 
    
Om du vill placera en post låda på en arbets grupp i administrations centret:
    
1. I det vänstra navigerings fältet går du till **användare** \> **aktiva användare** .
    
2. Välj en användare vars post låda du vill använda i en beställnings plats. I fönstret användare expanderar du **Inställningar för e-post** och bredvid **fler inställningar** väljer du **Redigera Exchange-egenskaper** .
    
3. På sidan med post lådan för användaren väljer du * * Mailbox features * * i det vänstra navigerings fältet och väljer sedan länken **Aktivera** under **rättsliga undantag** .
    
4. I dialog rutan **tvist undantag** kan du ange arbets tidens varaktighet i fältet **varaktighet** . Lämna fältet tomt om du vill sätta ett oändligt undantag. Du kan också lägga till anteckningar och direkt skicka post lådans ägare till en webbplats. \>**Spara** .
    
**Bevarande:** Du kan aktivera anpassade bevarande principer, till exempel för att bevara en viss tid eller ta bort innehåll permanent i slutet av lagrings perioden. Mer information finns i [Översikt över bevarande principer](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).

## <a name="set-up-sensitivity-labels"></a>Ange känslighets etiketter

Känslighets etiketter levereras med Azure information Protection (AIP) plan 1, och du kan skydda dina dokument och e-postmeddelanden genom att använda etiketter. Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare, eller genom att använda en kombination där användarna får rekommendationer.

Om du vill ställa in känslighets etiketter kan du läsa [skapa och hantera video med känslighets etiketter](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .



### <a name="install-the-azure-information-protection-client-manually"></a>Installera Azure information Protection client manuellt

Så här installerar du AIP-klienten manuellt:

1. Ladda ned **AzinfoProtection_UL.exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Du kan kontrol lera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **känslighet** finns på fliken **Start** .
<br/>![List rutan skydd i ett Word-dokument.](../media/word-sensitivity.png)

Mer information finns i [Installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
