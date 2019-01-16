---
title: Säkerhetsfunktionerna i Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Lär dig mer om säkerhetsfunktioner som medföljer Microsoft 365 Business.
ms.openlocfilehash: 17bcc57d57e837f18b05f66cfd54185324f3cad8
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26983179"
---
# <a name="microsoft-365-business-security-features"></a>Säkerhetsfunktionerna i Microsoft 365 Business

Microsoft 365 Business erbjuder förenklad säkerhetsfunktioner för att skydda data på datorer, telefoner och Tablet-datorer.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Säkerhetsfunktioner i Microsoft 365 Business admin center

Du kan hantera många Microsoft 365 Business säkerhetsfunktionerna i administratörscenter, som ger dig ett förenklat sätt att aktivera och inaktivera dessa funktioner. I administratörscenter kan du göra följande:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Ange inställningar för programmet för Android eller iOS-enheter](app-protection-settings-for-android-and-ios.md) . 
    
    Dessa inställningar inkluderar filer tas bort från en inaktiv enhet efter en angiven period, kryptera filer för arbete, som kräver att användare anger en PIN-kod osv.
    
- [Ange programinställningar skydd för Windows 10 enheter](protection-settings-for-windows-10-devices.md) . 
    
    Dessa inställningar kan användas till företagsdata på båda ägda företag eller personligt ägda enheter.
    
- [Ange inställningar för skydd för Windows 10 enheter](protection-settings-for-windows-10-pcs.md) . 
    
    Du kan aktivera [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) -diskkryptering för att skydda data om en enhet försvinner eller blir stulen och aktiverar [Windows utnyttja Guard](https://go.microsoft.com/fwlink/p/?linkid=871404) till ger ett avancerat skydd mot ransomware. 
    
- [Ta bort företagsdata från enheter](remove-company-data.md)
    
    Du kan torka företagsdata från en annan dator om en enhet går förlorad, stulen, eller om en medarbetare lämnar företaget.
    
- [Återställ Windows 10 enheter till sina fabriksinställningar](reset-devices-to-factory-settings.md) . 
    
    Du kan återställa Windows 10-enheter som har inställningar för dataskydd tillämpas.
    
## <a name="additional-security-features"></a>Ytterligare säkerhetsfunktioner 

Avancerade funktioner i Microsoft 365 Business finns tillgängliga för att hjälpa dig att skydda ditt företag mot cyber-hot och skydda känslig information.
  
- **[Office 365 avancerade Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) skyddar ditt företag mot sofistikerade phishing och ransomware attacker som utformats för att angripa medarbetare eller kundinformation. Bland funktionerna finns:
    
  - Avancerade bifogad fil skanning och AI-powered analys för att identifiera och ta bort farliga meddelanden.
    
  - Automatiska kontroller av länkar i e-post för att bedöma om de är en del av ett schema för nätfiske. Detta håller du säker tillgång till osäkra webbplatser.
    
- **[Översikt över data förlust förebyggande principer](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Du kan ställa in DLP automatiskt ska identifiera känslig information, som kreditkortsnummer, personnummer, etc. för att förhindra att deras oavsiktlig delning utanför företaget.
    
- **[Exchange Online - arkivering](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online-arkivering licens gör att meddelanden kan enkelt arkiveras med kontinuerlig säkerhetskopiering. Lagrar alla en användares e-post, inklusive Borttaget, om de behövs för identifiering eller återställande senare. Du kan dessutom använda olika lagringsprinciper att bevara e-data för rättstvist lastrum, e-informationsavslöjande, eller för att uppfylla myndigheternas krav.
    
- **[Azure informationsskydd](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    Information skydd kan du styra åtkomsten till känslig information i e-post och dokument med kontroller som ”inte framåt” och ”kopiera inte”. Du kan även klassificera känslig information som ”konfidentiellt” och anger hur sekretessbelagda uppgifter kan delas utanför och innanför verksamhet. Företagsverktyg kryptering är lätt att använda för e-post och dokument för att hålla din information privat. Microsoft 365 Business innehåller alla funktioner i [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Du kan också installera Azure informationsskydd klienten tillägget för Office-program. Mer information finns i [Azure informationsskydd klient admininstrator guide](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).
    
- **[Alla funktioner i Intune i Azure portal](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Komma åt Intune administratörscenter i Azure portal kan du konfigurera ytterligare säkerhetsfunktioner, till exempel hantering av MacOS-enheter, iPhone och Android-enheter med avancerad enhetshantering för Windows, som inte är tillgängliga via Microsoft 365 business administratörscenter.
    
I nästa avsnitt beskrivs hur du kan hantera dessa funktioner i säkerhet &amp; regelefterlevnadscentret och Intune administratörscenter. Förenklade kontroller kommer att läggas till Microsoft 365 Business administratörscenter över tiden.
  
## <a name="set-up-advanced-threat-protection-features"></a>Ställa in avancerade Threat Protection funktioner

- **Skydd mot osäkra bilagor:** ATP identifierar skadligt innehåll genom att öppna e-postbilagor i en virtuell miljö och utför analys av resulterande beteende. Innehåll utvärderas för att avgöra dess avsikt (normal eller skadliga), och ATP blockerar leverans av osäkra bifogade filer, skydda mot phishing system och ransomware infektioner. Om du vill aktivera skydd för bifogade filer finns i [ställa in principer för Office 365 ATP säkra bifogade filer](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775).
    
- Skydda miljön när användaren klickar på skadliga länkar: ATP undersöker också länkar i e-post när en användare klickar på dem.. Om en länk är osäkra, inte att besöka webbplatsen för användaren eller informeras om att webbplatsen har blockerats. Detta skyddar mot phishing system. Du kan [Konfigurera principer för Office 365 ATP Safe länkar](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) eller [Konfigurera Office 365 ATP Safe länkar principer](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
## <a name="set-up-dlp-features"></a>Ställa in funktioner för DLP

Ett exempel på hur du ställer in en princip som skyddar mot personligt identifierbar information (PII) finns i [Skapa en DLP-princip från en mall](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) . 
  
DLP levereras med flera färdiga att använda principmallar för många olika språk. Till exempel ekonomiska Data i Australien, Kanada personlig Information Act, amerikanska ekonomiska Data, etc. Se [vad den DLP principmallar innehåller](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) en fullständig lista. Alla dessa mallar kan aktiveras ungefär så PII mall. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Ställ in e-lagring med Exchange Online-arkivering

 Funktioner för **Exchange Online-arkivering** licens ger dig möjlighet att upprätthålla överensstämmelse och reglerande normer genom att bevara e innehåll för e-informationsavslöjande. Det hjälper till att minska risken i händelse av tvist och ger möjlighet att återskapa data efter ett intrång eller när du behöver återskapa borttagna objekt. Om du vill aktivera dessa funktioner kan du använda rättstvist håller för att bevara en användares innehåll eller använda bevarandeprinciper för större anpassning. 
  
**Rättstvist håller:** Du kan behålla alla innehållet inklusive borttagna objekt genom att infoga hela postlådan för en användare i en rättstvist håller. 
    
Om du vill placera håller en postlåda på rättstvist i administratörscenter
    
1. Gå till **användare** i vänster navigeringsfält \> **aktiva användare**.
    
2. Välj en användare vars postlåda du vill placera på rättstvist håller och expandera **e-postinställningar** i fönstret användare och vid **Fler inställningar** väljer du **Redigera Exchange egenskaper**.
    
3. Välj på sidan postlåda för användaren ** postlåda funktioner ** i vänstra navigeringsfältet och välj sedan **Aktivera** länk under **rättstvist håller**.
    
4. I **rättstvist håller** dialogrutan kan du ange rättstvist håller varaktighet i fältet **rättstvist håller varaktighet** , lämna fältet tomt om du vill placera en oändlig håll. Du kan också lägga till anteckningar och direkt e-rutan ägare till en webbplats som du kan behöva förklara mer om tvisten håller \> **Spara**.
    
**Bevarande:** Du kan aktivera anpassade lagringsprinciper, till exempel att bevara under en viss tid eller permanent ta bort innehåll i slutet av loggperioden. Mer information finns i [Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
## <a name="set-up-azure-information-protection-features"></a>Ställa in funktioner för informationsskydd i Azure

Azure Information skydd (AIP) är en molnbaserad lösning som hjälper företaget att klassificera och du kan också skydda sina dokument och e-post med hjälp av etiketter. Etiketter kan användas av administratörer som definierar regler och villkor manuellt av användare eller en kombination där användare ges rekommendationer automatiskt.

Möjligheten att använda följande begränsningar när du skickar e-postmeddelanden i Outlook på webben aktiveras automatiskt för alla användare:
  
- **Vidarebefordra inte**: mottagarna kan läsa meddelandet, men de kan inte vidarebefordra, skriva ut eller kopiera innehåll
    
- **Kryptera**: hela meddelandet är krypterat. Mottagarna måste vidta ytterligare åtgärder för att bekräfta sin identitet innan åtkomst till krypterade innehållet och kan inte ta bort kryptering.
    
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

Mer information finns i [installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)

## <a name="go-to-intune-admin-center"></a>Gå till Intune administratörscenter

1. Logga in på [Azure portal](https://portal.azure.com/).

2. Markera **alla tjänster** och Skriv i *Intune* i **Sökrutan**.

3. När resultatet visas klickar du på start nästa **Microsoft Intune** så att det blir en favorit och lätta att hitta senare.
 
Du kan använda Intune för att registrera och hantera enheter i din organisation. Mer information finns i [funktioner som metod för certifikatregistrering för Windows-enheter](https://docs.microsoft.com/intune/enrollment-method-capabs) och [registreringsalternativ för enheter som hanteras av Intune](https://docs.microsoft.com/intune/enrollment-options).
    
## <a name="faq"></a>Vanliga frågor och svar

 ### <a name="are-these-security-features-available-in-all-markets"></a>Är dessa funktioner tillgängliga på alla marknader?
  
Ja, dessa funktioner finns på alla marknader där Microsoft 365 Business säljs.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hur hittar säkerhet &amp; regelefterlevnadscentret?
  
1. [Logga in på Microsoft 365 Business](https://portal.microsoft.com/) med admin-referenser. 
    
2. Hitta **resurser Admin** i vänster navigeringsfält och expandera den. 
    
    ![Välj Admin Center i vänstra navigeringsfältet i Microsoft 365 administratörscenter.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Välj **säkerhet &amp; att** att gå till säkerhet &amp; regelefterlevnadscentret.