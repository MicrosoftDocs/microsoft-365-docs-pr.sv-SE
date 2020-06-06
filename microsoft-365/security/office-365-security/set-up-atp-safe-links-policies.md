---
title: Konfigurera Office 365 ATP-principer för säkra länkar
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Konfigurera principer för säkra länkar för att skydda din organisation från skadliga länkar i Word-, Excel-, PowerPoint- och Visio-filer samt i e-postmeddelanden.
ms.openlocfilehash: 928f13ec8f04506540d02177acd82b2403a74683
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588094"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Konfigurera Office 365 ATP-principer för säkra länkar

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hemanvändare och letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

[ATP Safe Links](atp-safe-links.md), en funktion i [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), kan skydda din organisation från skadliga länkar som används vid nätfiske och andra attacker. Om du har de [behörigheter &amp; ](permissions-in-the-security-and-compliance-center.md)som krävs för Security Compliance Center kan du ställa in ATP Safe Links-principer för att se till att din organisation är skyddad när personer klickar på webbadresser. Dina ATP Safe Links-principer kan konfigureras för att skanna webbadresser i e-post och webbadresser i Office-dokument.

Om en användare klickar på en länk i ett e-postmeddelande och webbadressen har blockerats av organisationens anpassade blockerade URL-lista eller om webbadressen bedöms vara skadlig öppnas en varningssida.
  
[Nya funktioner läggs kontinuerligt till i ATP.](office-365-atp.md#new-features-in-office-365-atp) När nya funktioner läggs till kan du behöva göra justeringar i dina befintliga ATP Safe Links-principer.

## <a name="what-to-do"></a>Vad du ska göra 
  
1. Gå igenom förutsättningarna.
    
2. Granska och redigera standardprincipen för betrodda länkar för ATP som gäller för alla. Du kan till exempel [ställa in listan anpassade blockerade webbadresser för betrodda ATP-länkar](set-up-a-custom-blocked-urls-list-atp.md).
    
3. Lägg till eller redigera principer för specifika e-postmottagare, inklusive [att ställa in din anpassade webbadresserlista "Skriv inte om" för ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
4. Läs mer om atp-principalternativ för säkra länkar (i den här artikeln), inklusive inställningar för de senaste ändringarna.
    
## <a name="step-1-review-the-prerequisites"></a>Steg 1: Granska förutsättningarna

- Kontrollera att din organisation har [ett avancerat skydd mot Office 365.](office-365-atp.md)
    
- Kontrollera att du har de behörigheter som krävs. Om du vill definiera (eller redigera) ATP-principer måste du tilldelas en lämplig roll. Några exempel beskrivs i följande tabell: <br>

    |Roll  |Var/hur tilldelas  |
    |---------|---------|
    |global administratör |Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Läs [mer om Microsoft 365-administratörsroller.)](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)         |
    |Säkerhetsadministratör |Administrationscenter för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
    |Hantering av Exchange Online-organisation |Administrationscenter för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

    Mer information om roller och behörigheter finns [i Behörigheter i &amp; Säkerhetsefterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- Kontrollera att Office-klienter är konfigurerade för att använda [modern autentisering](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (detta är för ATP Safe Links-skydd i Office-dokument).
    
- Läs mer om alternativ för [ATP Safe Links](#step-4-learn-about-atp-safe-links-policy-options) (i den här artikeln). 

- Tillåt upp till 30 minuter innan den nya eller uppdaterade principen sprids till alla Microsoft 365-datacenter.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Steg 2: Definiera (eller granska) ATP Safe Links-principen som gäller för alla

När du har [Ett avancerat skydd mot office 365](office-365-atp.md)har du en standardprincip för ATP Safe Links som gäller för alla i organisationen. Se till att granska och redigera standardprincipen om det behövs.
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets- eller skolkonto. 
    
2. Välj ** \> Policy** Säkra länkar under **Hothantering**i den vänstra **navigeringen.**
    
3. I de **principer som gäller för hela organisationsavsnittet** väljer du **Standard**och väljer sedan **Redigera** (knappen Redigera liknar en penna).<br/>![Klicka på Redigera om du vill redigera standardprincipen för skydd av säkra länkar](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. I avsnittet **Blockera följande webbadresser** anger du en eller flera webbadresser som du vill förhindra att personer i organisationen besöker. (Se [Konfigurera en anpassad lista med blockerade webbadresser med ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).)
    
5. I avsnittet **Inställningar som gäller för innehåll utom e-post** väljer du (eller avmarkerar) de alternativ du vill använda. (Vi rekommenderar att du väljer alla alternativ.) 
    
6. Välj **Save**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Steg 3: Lägga till (eller redigera) ATP Safe Links-principer som gäller för specifika e-postmottagare

När du har granskat (eller redigerat) standardprincipen för betrodda länkar till ATP som gäller för alla, är nästa steg att definiera ytterligare principer som skulle gälla för specifika mottagare. Du kan till exempel ange undantag från standardprincipen genom att definiera ytterligare en princip. 
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets- eller skolkonto. 
    
2. Välj **Policy**under **Hothantering**i den vänstra navigeringen .
    
3. Välj **säkra länkar**.
    
4. I avsnittet **Principer som gäller för specifika mottagare** väljer du **Ny** (knappen Nytt liknar ett plustecken ( **+** )).<br/>![Välj Ny om du vill lägga till en princip för säkra länkar för specifika e-postmottagare](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Ange namn, beskrivning och inställningar för principen.<br/>**Exempel:** Om du vill ställa in en princip som kallas "inget direkt klick igenom" som inte tillåter att personer i en viss grupp i organisationen kan klicka sig vidare till en viss webbplats utan ATP Safe Links-skydd kan du ange följande rekommenderade inställningar: 
    
    - Skriv inget direkt klick i rutan **Namn.**

    - Skriv en beskrivning på **en** beskrivning som förhindrar att personer i vissa grupper klickar sig vidare till en webbplats utan ATP Safe Links-verifiering.

    - Välj **På**i avsnittet **Välj åtgärd** .

    - Välj **Använd URL-skanning i realtid efter misstänkta länkar och länkar som pekar på filer** om du vill aktivera URL-detonation för misstänkta och filpekande webbadresser (rekommenderas). Och välj **Vänta tills URL-skanningen slutförs innan du levererar meddelandet** om du bara vill att användarna ska få meddelanden efter att webbadresserna har skannats igenom helt.

    - Välj **Använd säkra länkar på meddelanden som skickas inom organisationen** om du vill aktivera Säkra länkar för meddelanden som skickas mellan användare inom organisationen (rekommenderas).

    - Välj **Tillåt inte att användaren klickar sig vidare till den ursprungliga webbadressen** om du inte vill att de enskilda användarna ska åsidosätta en *pågående genomsökning* eller *url-blockerade* meddelandesidor.

    - (Detta är valfritt) I avsnittet **Skriv inte om följande webbadresser** anger du en eller flera webbadresser som anses vara säkra för din organisation. (Se [Konfigurera en anpassad webbadresslista "Skriv inte om" med HJÄLP av ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))

    - I avsnittet **Tillämpad på** väljer du **Mottagaren är medlem i**och väljer sedan den grupp(er) som du vill ta med i principen. Välj **Lägg till**och välj sedan **OK**.
    
6. Välj **Save**.

> [!NOTE]
> ATP Safe Links-principer med högre prioritet har företräde. Om en användare är föremål för två eller flera politikområden kommer endast principen med högre prioritet att träda i kraft.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Steg 4: Lär dig mer om atp safe links-principalternativ

När du ställer in eller redigerar atp-principerna för säkra länkar visas flera tillgängliga alternativ. Om du undrar vad dessa alternativ är, beskriver följande tabell var och en och dess effekt. Kom ihåg att det finns två huvudtyper av ATP Safe Links-principer som ska definieras eller redigeras:
- en [standardprincip](#default-policy-options) som gäller för alla. Och  
- ytterligare [principer för specifika mottagare](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>Standardprincipalternativ

Standardprincipalternativ gäller för alla i organisationen.

|Det här alternativet  |Gör detta  |
|---------|---------|
| **Blockera följande webbadresser** <br/>    | Gör att din organisation kan ha en anpassad lista över webbadresser som blockeras automatiskt. När användare klickar på en webbadress i den här listan kommer de till en [varningssida](atp-safe-links-warning-pages.md) som förklarar varför webbadressen blockeras. Mer information finns i [Konfigurera en anpassad lista med blockerade webbadresser med office 365 ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md). |
| **Microsoft 365 Apps för företag, Office för iOS och Android** <br/>    | När det här alternativet är markerat tillämpas ATP-skydd för säkra länkar på WEBBADRESSER i Word-, Excel- och PowerPoint-filer i Windows eller Mac OS, e-postmeddelanden i Outlook, Office-dokument på iOS- eller Android-enheter, Visio 2016-filer i Windows och filer som är öppna i webbversionerna av Office-appar (Word, PowerPoint, Excel, Outlook och OneNote), förutsatt att användaren har loggat in på Office 365. |
| **Spåra inte när användare klickar på ATP Safe Links** <br/>  | När det här alternativet är markerat klickar du på data för webbadresser i e-postmeddelanden i Word, Excel, PowerPoint, Visio och Outlook-e-postmeddelanden lagras inte.  <br/> |
|**Låt inte användare klicka igenom ATP Säkra länkar till ursprungliga WEBBADRESSEN** <br/> |När det här alternativet är markerat kan användarna inte gå förbi en [varningssida](atp-safe-links-warning-pages.md) till en URL som bedöms vara skadlig.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>Principer som gäller för specifika e-postmottagare

|Det här alternativet  |Gör detta  |
|---------|---------|
|**Av** <br/> |Söker inte igenom webbadresser i e-postmeddelanden.  <br/> Gör att du kan definiera en undantagsregel, till exempel en regel som inte söker igenom webbadresser i e-postmeddelanden för en viss grupp mottagare.  <br/> |
|**På** <br/> |Skriver om webbadresser för att dirigera användare via ATP Safe Links-skydd när användarna klickar på WEBBADRESSER i e-postmeddelanden och aktiverar ATP Safe Links i Outlook (C2R) i Windows.  <br/> Kontrollerar en URL när du klickar mot en lista med blockerade eller skadliga webbadresser och utlöser en detonation av URL:en i bakgrunden asynkront om webbadressen inte har ett giltigt rykte.  <br/> |
|**Använda URL-skanning i realtid efter misstänkta länkar och länkar som pekar på filer** <br/> |När det här alternativet är markerat genomsöks misstänkta webbadresser och länkar som pekar på nedladdningsbart innehåll.  <br/> |
|**Vänta tills URL-skanningen har slutförts innan meddelandet levereras** <br/> |När det här alternativet är markerat hålls meddelanden som innehåller webbadresser som ska skannas tills webbadresserna har skannats klart och bekräftas vara säkra innan meddelandena levereras.  <br/> |
|**Använda säkra länkar på meddelanden som skickas inom organisationen** <br/> | När det här alternativet är tillgängligt och markerat tillämpas ATP-skydd för säkra länkar på e-postmeddelanden som skickas mellan personer i organisationen, förutsatt att e-postkontona finns i Office 365.  <br/> |
|**Spåra inte användarens klick** <br/> |När det här alternativet är markerat lagras inte data för webbadresser i e-post från externa avsändare. URL-klickspårning för länkar i e-postmeddelanden som skickas inom organisationen stöds för närvarande inte.  <br/> |
|**Tillåt inte att användare klickar sig vidare till den ursprungliga webbadressen** <br/> |När det här alternativet är markerat kan användarna inte gå förbi en [varningssida](atp-safe-links-warning-pages.md) till en URL som bedöms vara skadlig.  <br/> |
|**Skriv inte om följande webbadresser** <br/> |Lämnar webbadresser som de är. Håller en anpassad lista över säkra webbadresser som inte behöver söka efter en viss grupp e-postmottagare i organisationen.  Se [Konfigurera en anpassad webbadresslista "Skriv inte om" med hjälp av ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) för mer information, inklusive de senaste ändringarna av stödet för jokertecken asterisker ( \* ).  <br/> |
   
## <a name="next-steps"></a>Nästa steg

När atp-principerna för säkra länkar har införts kan du se hur ATP fungerar för din organisation genom att visa rapporter. Läs följande resurser om du vill veta mer:

- [Visa rapporter för avancerat hotskydd för Office 365](view-reports-for-atp.md)

- [Använda Explorer i &amp; Säkerhetsefterlevnadscenter](threat-explorer.md)

Håll koll på nya funktioner som kommer till ATP. besök Översikt över [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).
