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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Konfigurera Office 365 Avancerat skydd mot hot och skydda känsliga data.
ms.openlocfilehash: 8144bcebe8a0cdf28a5e092f592362922ccbdd48
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288754"
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

## <a name="set-up-azure-information-protection-features"></a>Konfigurera Azure information Protection-funktioner

Azure information Protection (AIP) hjälper dig att klassificera och eventuellt skydda dina dokument och e-postmeddelanden genom att använda etiketter. Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom att använda en kombination där användare ges rekommendationer.

I Outlook på webben kan du använda följande inbyggda etiketter och begränsningar i din e-post:
  
- **Vidarebefordra inte**: mottagarna kan läsa meddelandet, men de kan inte vidarebefordra, skriva ut eller kopiera innehåll
    
- **Kryptera**: hela meddelandet krypteras. Mottagarna måste bekräfta sin identitet innan de får åtkomst till krypterat innehåll och kan inte ta bort kryptering.
    
- **Konfidentiellt**: ger medarbetarna i organisationen fullständig behörighet till e-postinnehåll och bifogade filer, men inte till personer utanför organisationen. Data ägare kan spåra och återkalla innehåll när som helst.
    
- **Mycket konfidentiell**: den här begränsningen kan tillämpas på mycket konfidentiella data, vilket gör det möjligt för anställda att visa, redigera och svara, men inte vidarebefordra, skriva ut eller kopiera data. Data ägare kan spåra och återkalla innehåll när som helst.

### <a name="make-sure-azure-information-protection-is-activated"></a>Kontrollera att Azure information Protection är aktiverad

Så här kontrollerar du att AIP är aktiverat:

1. Logga in på [Azure Portal](https://portal.azure.com/).

2. Välj **alla tjänster** och skriv in *Azure information Protection* i **sökrutan**.

3. När resultatet visas klickar du på Start bredvid **Azure information Protection** för att göra det till en favorit och lätt att hitta senare.

4. Välj **Azure information Protection** \> **Protection-aktivering** och kontrollera att status är inställt på aktiverad. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Visa Azure information Protection-principen och standardetiketter 

Så här visar och ändrar du de befintliga etiketterna:

1. På den Azure information Protection-instrumentpanelen, Välj **klassificeringar** \> **Etiketter**. <br/>![Standard etiketter för Azure information Protection.](media/AIPLabels.png)

2. Du kan välja vilken etikett som helst för att visa alternativ, du kan ändra visningsnamn, färger, etc.
 
3. Se [ändra och skapa nya etiketter](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) om du vill skapa egna. 

### <a name="install-the-azure-information-protection-client-manually"></a>Installera Azure information Protection-klienten manuellt

Så här installerar du AIP-klienten manuellt:

1. Hämta **Azinfoprotection. exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **skydda** är tillgängligt på fliken **Start** . <br/>![Fliken skydd i ett Word-dokument.](media/Word_Protect.png)

Mer information finns [i installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
