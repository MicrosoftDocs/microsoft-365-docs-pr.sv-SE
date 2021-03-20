---
title: Öka skydd mot hot för Microsoft 365 Business Premium
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
description: Konfigurera efterlevnadsfunktioner för att förhindra dataförlust och skydda din och dina kunders känsliga information.
ms.openlocfilehash: e210787718025c5df29af8d4a2283291dcecc2a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912539"
---
# <a name="set-up-compliance-features"></a>Konfigurera funktioner för efterlevnad

Din Microsoft 365 Business Premium levereras med funktioner som skyddar dina data och enheter och hjälper dig att hålla din och dina kunders känsliga information säker.

## <a name="set-up-dlp-features"></a>Konfigurera DLP-funktioner

Se [Skapa en DLP-princip från](../compliance/create-a-dlp-policy-from-a-template.md) en mall för ett exempel på hur du skapar en princip för att skydda mot skydd mot förlust av personuppgifter. 
  
DLP innehåller många färdiga principmallar för många olika språk. Till exempel Australia Financial Data, Canada Personal Information Act, U.S. Financial Data och så vidare. Se [Vad DLP-principmallarna innehåller](../compliance/what-the-dlp-policy-templates-include.md) för en fullständig lista. Alla mallar kan aktiveras ungefär som i exemplet med pii-mallar. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Konfigurera e-postbevarande med Exchange Online-arkivering

 **Exchange Online-licensfunktioner hjälper till** att bevara efterlevnads- och regelstandarder genom att bevara e-postinnehållet för e-dataidentifiering. Det hjälper också till att minska risken om det finns en sekretess, och det är ett sätt att återställa data efter en säkerhetsöverträdelse eller när du behöver återställa borttagna objekt. Du kan använda bevarande av juridiska skäl för att bevara allt innehåll för en användare, eller använda bevarandeprinciper för att anpassa vad du vill bevara.
  
**Bevarande av juridiska skäl:** Du kan bevara allt innehåll i postlådan, inklusive borttagna objekt, genom att sätta en användares hela postlåda i bevarande av juridiska skäl. 
    
Så här placerar du en postlåda i bevarande av juridiska skäl i administrationscentret:
    
1. I det vänstra navigeringsfältet går du till **Användare** \> **aktiva användare.**
    
2. Välj en användare vars postlåda du vill skapa bevarande av juridiska skäl för. I användarfönstret expanderar du **E-postinställningar** och bredvid **Fler inställningar** väljer du **Redigera Exchange-egenskaper**.
    
3. På användarens postlådesida väljer du ** postlådefunktioner **  i det vänstra navigeringsfältet och väljer sedan länken Aktivera under Bevarande av juridiska **skäl.**
    
4. I dialogrutan **Bevarande av juridiska** skäl kan du ange varaktigheten för bevarande av juridiska skäl i fältet Bevarande av juridiska **skäl.** Lämna fältet tomt om du vill ha ett oändligt utrymme. Du kan också lägga till anteckningar och dirigera postlådans ägare till en webbplats som du kan behöva förklara mer om bevarande av juridiska skäl. \>**Spara**.
    
**Bevarande:** Du kan aktivera anpassade bevarandeprinciper, till exempel för att bevara under en viss tid eller ta bort innehåll permanent i slutet av kvarhållningsperioden. Mer information finns i Översikt [över bevarandeprinciper.](../compliance/retention.md)

## <a name="set-up-sensitivity-labels"></a>Konfigurera känslighetsetiketter

Känslighetsetiketter följer med Azure Information Protection (AIP) abonnemang 1 och hjälper dig att klassificera, och om du vill, skydda dina dokument och e-postmeddelanden genom att använda etiketter. Etiketter kan tillämpas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom en kombination där användarna får rekommendationer.

Om du vill konfigurera känslighetsetiketter, visa [och hantera känslighetsetiketter](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.



### <a name="install-the-azure-information-protection-client-manually"></a>Installera Azure Information Protection-klienten manuellt

Så här installerar du AIP-klienten manuellt:

1. Ladda **AzinfoProtection_UL.exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och kontrollera att **alternativet Känslighet** är tillgängligt på **fliken** Start.
<br/>![Nedrullningsrutan för fliken Skydd i ett Word-dokument.](../media/word-sensitivity.png)

Mer information finns i [Installera klienten.](/azure/information-protection/infoprotect-tutorial-step3)