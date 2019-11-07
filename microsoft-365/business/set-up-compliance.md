---
title: Öka skyddet mot hot för Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
description: Ställ in efterlevnadsfunktioner för att förhindra dataförlust och etikettkänsliga data.
ms.openlocfilehash: 5213c55f4a8ce0e223896f1b960847714d6d06cb
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031424"
---
# <a name="set-up-compliance-features"></a>Ställa in efterlevnadsfunktioner

Din Microsoft 365-verksamhet levereras med funktioner som skyddar dina data och enheter och hjälper dig att skydda dina och kundernas känsliga information.

## <a name="set-up-dlp-features"></a>Konfigurera DLP-funktioner

Se [skapa en DLP-princip från en mall](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) för ett exempel på hur du ställer in en princip för att skydda mot personligt identifierbar information (PII). 
  
DLP levereras med många färdiga att använda principmallar för många olika språk. Till exempel Australien Financial data, Kanada personuppgifter Act, amerikanska finansiella data, etc. Se [vad DLP-principmallarna innehåller](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) för en fullständig lista. Alla dessa mallar kan aktiveras liknande den PII mall exempel. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Konfigurera e-postlagring med Exchange Online-arkivering

 **Exchange Online arkivering** licens funktioner bidra till att upprätthålla efterlevnad och reglerande standarder genom att bevara e-innehåll för eDiscovery. Det bidrar också till att minska risken i händelse av en rättegång och ger ett sätt att återskapa data efter en säkerhetsöverträdelse, eller när du behöver återskapa borttagna objekt. Du kan använda bevarande av juridiska tvister för att bevara allt innehåll i en användare eller använda loggperiodsprinciper för att anpassa vad du vill bevara.
  
**Rättstvist håller:** Du kan bevara allt postlådeinnehåll inklusive borttagna objekt genom att placera en användares hela postlåda i rättstvist håller. 
    
Om du vill placera en postlåda i rättstvist håller du i administratörscenter:
    
1. Gå till **användare** \> **aktiva användare**i det vänstra navigeringsfältet.
    
2. Välj en användare vars postlåda du vill placera på rättstvist håller och i fönstret användare expandera **e-postinställningar** och bredvid **fler inställningar** väljer **Redigera Exchange-egenskaper**.
    
3. På sidan postlådesida för användaren väljer du * * Postlådefunktioner * * i det vänstra navigeringsfältet och väljer sedan **Aktivera** länk under **rättstvist håller**.
    
4. I dialogrutan **rättstvist håller** du kan ange rättstvist håller varaktighet i fältet **rättstvist håller varaktighet** , lämna fältet tomt om du vill placera en oändlig spärr. Du kan också lägga till anteckningar och dirigera brev låde ägaren till en webbplats som du kanske måste förklara mer om bevarande av \> rätts **tvister.**
    
**Retention:** Du kan aktivera anpassade bevarandeprinciper, till exempel för att bevara under en viss tid eller ta bort innehåll permanent i slutet av kvarhållningsperioden. Mer information finns [i Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="set-up-sensitivity-labels"></a>Ställ in känslighets etiketter

Känslighets etiketter levereras med Azure information Protection (AIP) plan 1 och hjälper dig att klassificera och eventuellt skydda dina dokument och e-postmeddelanden genom att använda etiketter. Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom att använda en kombination där användare ges rekommendationer.

Om du vill ställa in känslighets etiketter, Visa [skapa och hantera känslighets etiketter](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.



### <a name="install-the-azure-information-protection-client-manually"></a>Installera Azure information Protection-klienten manuellt

Så här installerar du AIP-klienten manuellt:

1. Hämta **AzinfoProtection_UL. exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **känslighet** är tillgängligt på fliken **Start** .
<br/>![Fliken skydd i ett Word-dokument.](media/word-sensitivity.png)

Mer information finns [i installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
