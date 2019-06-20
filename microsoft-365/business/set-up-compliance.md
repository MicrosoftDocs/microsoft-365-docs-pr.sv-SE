---
title: Ökat skydd för Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
description: Konfigurera Office 365 Advanced Threat Protection och skydda känsliga data.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2019
ms.locfileid: "35086398"
---
# <a name="set-up-compliance-features"></a>Ställa in funktioner för regelefterlevnad

Företaget Microsoft 365 levereras med funktioner för att skydda dina data och enheter och hjälper dig att skydda dig och dina kunder känslig information.

## <a name="set-up-dlp-features"></a>Ställa in funktioner för DLP

Ett exempel på hur du ställer in en princip som skyddar mot personligt identifierbar information (PII) finns i [Skapa en DLP-princip från en mall](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) . 
  
DLP levereras med flera färdiga att använda principmallar för många olika språk. Till exempel ekonomiska Data i Australien, Kanada personlig Information Act, amerikanska ekonomiska Data, etc. Se [vad den DLP principmallar innehåller](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) en fullständig lista. Alla dessa mallar kan aktiveras ungefär så PII mall. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Ställ in e-lagring med Exchange Online-arkivering

 Funktioner för **Exchange Online-arkivering** licens hjälper upprätthålla överensstämmelse och reglerande normer genom att bevara e innehåll för e-informationsavslöjande. Det hjälper till att minska risken vid en rättegång och ger möjlighet att återskapa data efter ett intrång, eller om du behöver återskapa borttagna objekt. Du kan använda rättstvist håller för att bevara en användares innehåll eller använda bevarandeprinciper för att anpassa vad du vill behålla.
  
**Rättstvist håller:** Du kan behålla alla innehållet inklusive borttagna objekt genom att infoga hela postlådan för en användare i en rättstvist håller. 
    
Om du vill placera håller en postlåda på rättstvist i administratörscenter
    
1. Gå till **användare** i vänster navigeringsfält \> **aktiva användare**.
    
2. Välj en användare vars postlåda du vill placera på rättstvist håller och expandera **e-postinställningar** i fönstret användare och vid **Fler inställningar** väljer du **Redigera Exchange egenskaper**.
    
3. Välj på sidan postlåda för användaren ** postlåda funktioner ** i vänstra navigeringsfältet och välj sedan **Aktivera** länk under **rättstvist håller**.
    
4. I **rättstvist håller** dialogrutan kan du ange rättstvist håller varaktighet i fältet **rättstvist håller varaktighet** , lämna fältet tomt om du vill placera en oändlig håll. Du kan också lägga till anteckningar och direkt e-rutan ägare till en webbplats som du kan behöva förklara mer om tvisten håller \> **Spara**.
    
**Bevarande:** Du kan aktivera anpassade lagringsprinciper, till exempel att bevara under en viss tid eller permanent ta bort innehåll i slutet av loggperioden. Mer information finns i [Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="set-up-azure-information-protection-features"></a>Ställa in funktioner för informationsskydd i Azure

Azure Information skydd (AIP) hjälper dig att klassificera och du kan också skydda dokument och e-post, med hjälp av etiketter. Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom en kombination där användare ges rekommendationer.

I Outlook på webben kan du använda följande inbyggda etiketter och begränsningar till din e-post:
  
- **Vidarebefordra inte**: mottagarna kan läsa meddelandet, men de kan inte vidarebefordra, skriva ut eller kopiera innehåll
    
- **Kryptera**: hela meddelandet är krypterat. Mottagarna måste bekräfta sin identitet innan åtkomst till krypterade innehållet och kan inte ta bort kryptering.
    
- **Konfidentiellt**: ger anställda i organisationen fullständig behörighet till e-innehåll och bifogade filer, men inte till personer utanför organisationen. Data kan spåra och återkalla innehåll när som helst.
    
- **Mycket konfidentiella**: den här begränsningen kan användas till mycket konfidentiella data, vilket gör att anställda kan visa, redigera och svara, men inte vidarebefordra, skriva ut eller kopiera data. Data kan spåra och återkalla innehåll när som helst.

### <a name="make-sure-azure-information-protection-is-activated"></a>Kontrollera att Azure informationsskydd är aktiverat

Kontrollera att AIP är aktiverad:

1. Logga in på [Azure portal](https://portal.azure.com/).

2. Markera **alla tjänster** och Skriv i *Azure informationsskydd* i **Sökrutan**.

3. När resultatet visas klickar du på start nästa på **Azure informationsskydd** så att det blir en favorit och lätta att hitta senare.

4. Välj **Azure informationsskydd** \> **skydd aktivering** och gör att den har statusen till aktiverad. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Visa Azure informationsskydd princip- och etiketter 

Om du vill visa och ändra befintliga etiketter:

1. Välj **klassificeringar** på instrumentpanelen Azure informationsskydd \> **etiketter**. <br/>![Standardetiketter för informationsskydd i Azure.](media/AIPLabels.png)

2. Du kan välja alla etiketter för att visa alternativ kan du ändra visningsnamnet, färger osv.
 
3. Se [ändra och skapa nya etiketter](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) om du vill skapa en egen. 

### <a name="install-the-azure-information-protection-client-manually"></a>Installera Azure informationsskydd klienten manuellt

Att manuellt installera klienten för AIP:

1. Hämta **AzInfoProtection.exe** från [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **skydda** är tillgängliga på fliken **Start** . <br/>![Fliken skydd listrutan i ett Word-dokument.](media/Word_Protect.png)

Mer information finns i [installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
