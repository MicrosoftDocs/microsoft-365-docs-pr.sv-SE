---
title: Öka hotskyddet för Microsoft 365 Business
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
description: Konfigurera efterlevnadsfunktioner för att förhindra dataförlust och skydda dina och dina kunders känsliga information.
ms.openlocfilehash: 4c8efc4ca96f2db7bc4d1592ad3fdc85dfb6b3b5
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550066"
---
# <a name="set-up-compliance-features"></a>Konfigurera efterlevnadsfunktioner

Microsoft 365 Business levereras med funktioner för att skydda dina data och enheter och hjälpa dig att skydda dina och dina kunders känsliga information.

## <a name="set-up-dlp-features"></a>Konfigurera DLP-funktioner

Se [Skapa en DLP-princip från en mall](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) för ett exempel på hur du ställer in en princip för att skydda mot personligt identifierbar information (PII). 
  
DLP levereras med många färdiga att använda principmallar för många olika språk. Till exempel Australia Financial Data, Canada Personal Information Act, Us Financial Data och så vidare. Se [Vad DLP-principmallarna innehåller](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) för en fullständig lista. Alla dessa mallar kan aktiveras på samma sätt som exempel på PII-mall. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Konfigurera e-postlagring med Exchange Online Archiving

 **Licensfunktioner för Exchange Online Archiving** hjälper till att upprätthålla efterlevnads- och regelstandarder genom att bevara e-postinnehåll för eDiscovery. Det bidrar också till att minska risken om det finns en rättegång, och ger ett sätt att återställa data efter en säkerhetsöverträdelse eller när du behöver återställa borttagna objekt. Du kan använda rättstvistspärr för att bevara allt innehåll för en användare eller använda bevarandeprinciper för att anpassa det du vill bevara.
  
**Rättstvister håller:** Du kan bevara allt postlådeinnehåll, inklusive borttagna objekt genom att spärra en användares hela postlåda. 
    
Så här placerar du en postlåda på spärrning i administrationscentret:
    
1. I vänster nav går du till **användare** \> **aktiva användare**.
    
2. Välj en användare vars postlåda du vill spärra. Expandera **E-postinställningar**och **välj**Redigera Exchange-egenskaper i användarfönstret och välj **Redigera Exchange-egenskaper**i användarfönstret.
    
3. På postlådan satt du ** postlådefunktioner ** till vänster nav och väljer sedan länken **Aktivera** under **Håll i rättstvister**.
    
4. I dialogrutan **Förrättningsspärr** kan du ange varaktigheten för rättstvisthållning i fältet **Varaktighet för juridiska rättigheter.** Lämna fältet tomt om du vill placera en oändlig spärr. Du kan också lägga till anteckningar och dirigera postlådeägaren till en webbplats som du kanske måste förklara mer om rättstvisten. \>**Spara**.
    
**Kvarhållning:** Du kan aktivera anpassade bevarandeprinciper, till exempel för att bevara under en viss tid eller ta bort innehåll permanent i slutet av kvarhållningsperioden. Mer information finns i [Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="set-up-sensitivity-labels"></a>Ställ in känslighetsetiketter

Känslighetsetiketter levereras med Azure Information Protection (AIP) Plan 1 och hjälper dig att klassificera och eventuellt skydda dina dokument och e-postmeddelanden genom att använda etiketter. Etiketter kan tillämpas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom att använda en kombination där användarna får rekommendationer.

Om du vill ställa in känslighetsetiketter visar du [video med och hanterar känslighetsetiketter.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)



### <a name="install-the-azure-information-protection-client-manually"></a>Installera Azure Information Protection-klienten manuellt

Så här installerar du AIP-klienten manuellt:

1. Ladda ner **AzinfoProtection_UL.exe** från [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att **alternativet Känslighet** är tillgängligt på fliken **Start.**
<br/>![Fliken Skyddsflik i ett Word-dokument.](../media/word-sensitivity.png)

Mer information finns [i Installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
