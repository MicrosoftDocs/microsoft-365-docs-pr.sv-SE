---
title: Konfigurera principer för säkra Office 365 ATP-länkar
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
description: Konfigurera principer för säkra Länkar för att skydda din organisation från skadliga länkar i Word-, Excel-, PowerPoint-och Visio-filer samt i e-postmeddelanden.
ms.openlocfilehash: 8c72473a9b1337e1d932ec7235ed12e79f0c48f6
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201765"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Konfigurera principer för säkra Office 365 ATP-länkar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hem användare letar efter information om säkra länkar i Outlook kan du läsa mer i [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

[ATP-säkra länkar](atp-safe-links.md), en funktion i [Office 365 Avancerat skydd](office-365-atp.md) (ATP), skyddar din organisation från illasinnade länkar som används i nätfiske och andra attacker. Om du har nödvändig [behörighet för säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md)kan du konfigurera principer för säkraste säkerhets Länkar för att säkerställa att när personer klickar på webb adresser (URL: er) skyddas din organisation. Dina principer för säker säkerhet för ATP kan konfigureras för genomsökning av URL-adresser i e-post och URL-adresser i Office-dokument

Med Safet ATP-länkar aktiverat, om en användare klickar på en länk i ett e-postmeddelande och URL-adressen har blockerats av organisationens anpassade blockerade URL-lista eller om URL: en är skadlig, öppnas en varnings sida.

[Nya funktioner läggs hela tiden till för ATP](office-365-atp.md#new-features-in-office-365-atp). När nya funktioner läggs till kan du behöva justera dina befintliga principer för säkerhet på ATP.

## <a name="what-to-do"></a>Vad kan jag göra?

1. Granska kraven.

2. Granska och redigera den princip för standard säkra säkerhets säkerhet för ATP som gäller för alla. Du kan till exempel [Konfigurera din anpassade lista över blockerade URL-adresser för säkra säkerhets](set-up-a-custom-blocked-urls-list-atp.md)-och ATP-länkar.

3. Lägga till eller redigera principer för specifika e-postmottagare, inklusive [inställning av din anpassade webb adress lista "Skriv inte över" för att skapa nya ATP-länkar](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).

4. Läs mer om princip alternativ (i den här artikeln) för säkerhets ATP – inklusive inställningar för senaste ändringar.

## <a name="step-1-review-the-prerequisites"></a>Steg 1: granska kraven

- Kontrol lera att din organisation har [Office 365 Avancerat skydd för hotet](office-365-atp.md).

- Se till att du har nödvändig behörighet. Om du vill definiera (eller redigera) ATP-principer måste du ha en lämplig roll. Några exempel beskrivs i följande tabell:

    |Roll|Där/hur kopplat|
    |---|---|
    |global administratör|Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard. (Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
    |Säkerhets administratör|Azure Active Directory-administratörs Center ( <https://aad.portal.azure.com> )|
    |Organisations hantering i Exchange Online|Administrations Center för Exchange ( <https://outlook.office365.com/ecp> ) <br>eller <br>  PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|

    Mer information om roller och behörigheter finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Kontrol lera att Office-klienter är konfigurerade för att använda [modern](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016) säkerhet (det här gäller för säkerhet i Office-dokument).

- [Läs mer om princip alternativ för säker användning för ATP](#step-4-learn-about-atp-safe-links-policy-options) (i den här artikeln).

- Tillåt upp till 30 minuter för att den nya eller uppdaterade principen ska spridas till alla Microsoft 365-datacenter.

## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Steg 2: definiera (eller granska) policyn för Safet ATP-länkar som gäller för alla

När du har [Office 365 Avancerat skydd](office-365-atp.md)har du en standard princip för säkerhet för säkerhets ATP som gäller för alla i organisationen. Se till att granska och om det behövs redigerar du din standard princip.

1. Gå till <https://protection.office.com> och logga in med ditt arbets-eller skol konto.

2. I det vänstra navigerings fältet, under **Threat Management**, väljer du **policy \> ** **Safe Links**.

3. I de **principer som gäller för hela avsnittet organisation** väljer du **standard**och sedan **Redigera** (knappen Redigera påminner om en penna).

   ![Klicka på Redigera om du vill redigera standard principen för skydd av säkra länkar](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)

4. I avsnittet **Blockera följande URL-adresser** anger du en eller flera URL: er som du inte vill att personer i organisationen ska kunna besöka. (Mer information finns i [Konfigurera en anpassad lista med blockerade URL-adresser](set-up-a-custom-blocked-urls-list-atp.md).)

5. Välj (eller avmarkera) de alternativ som du vill använda i avsnittet **inställningar som gäller förutom e-postadress** . (Vi rekommenderar att du markerar alla alternativ.)

6. Välj **Save**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients"></a>Steg 3: lägga till (eller redigera) principer för säkra anslutningar för ATP som gäller för alla eller vissa e-postmottagare

När du har granskat (eller redigerat) standard policyn för Safet säkerhet för ATP som gäller för alla är nästa steg att definiera ytterligare principer som gäller för alla eller specifika e-postmottagare. Du kan till exempel ange undantag för standard principen genom att definiera en ytterligare princip eller skapa mer detaljerade begränsningar för alla anställda.
  
1. Gå till <https://protection.office.com> och logga in med ditt arbets-eller skol konto. 
    
2. I det vänstra navigerings fältet under **Threat Management**väljer du **policy**.

3. Välj **Safe Links**.

4. I avsnittet **principer som gäller för specifika mottagare** väljer du **nytt** (den nya knappen liknar ett plus tecken ( **+** )).

   ![Välj nytt för att lägga till en policy för säkra Länkar för specifika e-postmottagare](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

5. Ange namn, beskrivning och inställningar för din policy.

   **Exempel:** Om du vill konfigurera en princip med namnet "ingen direkt klickning genom" som inte tillåter personer i en viss grupp i organisationen att klicka dig fram till en viss webbplats utan skydd för säkra länkar från ATP kan du ange följande rekommenderade inställningar:

   - I rutan **namn** skriver du ingen direkt klickning genom.

   - I rutan **Beskrivning** skriver du en beskrivning, till exempel hindrar personer i vissa grupper från att klicka på till en webbplats utan verifiering med säkerhet per ATP.

   - I avsnittet **Välj åtgärd väljer du** **på**.

   - Välj **Använd URL-genomsökning i real tid för att få misstänkta länkar och länkar som pekar på filer** om du vill aktivera URL-sprängning för misstänkta och filbaserade URL-adresser (rekommenderas). Och välj **vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet** om du endast vill få meddelanden efter att URL-adresserna har skannats helt.

   - Välj **Använd Safe Links för meddelanden som skickas inom organisationen** om du vill aktivera säkra Länkar för meddelanden som skickas mellan användare inom organisationen (rekommenderas).

   - Välj **Tillåt inte användare att klicka dig fram till original-URL:** en om du inte vill att de enskilda användarna ska åsidosätta en *pågående genomsökning* eller *URL-blockerade* aviserings sidor.

   - (Det här är valfritt) Ange en eller flera URL-adresser som anses vara säkra för din organisation i avsnittet **gör inte om följande URL: er** . (Mer information finns i [Konfigurera en egen URL-lista "Skriv inte över" med hjälp av säkerhet för ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))

   - I avsnittet **används för** väljer du **mottagaren är medlem i**och väljer sedan de grupper som du vill ta med i policyn. Välj **Lägg till**och sedan **OK**.

6. Välj **Save**.

> [!NOTE]
> Principer för Safet ATP-länkar med högre prioritet prioriteras. Om en användare lyder i två eller fler principer kommer bara den högre prioritets principen att träda i kraft. Om du vill att kund policyn ska ha högre prioritet måste du höja prioriteten för policyn.

## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Steg 4: Lär dig mer om princip alternativ för att skydda ATP

När du ställer in eller redigerar principer för säkrat ATP-länkar visas flera tillgängliga alternativ. I händelse av att de här alternativen är uppfyllde beskrivs var och en av följande tabeller. Kom ihåg att det finns två huvudsakliga typer av principer för säkra anslutningar för ATP för att definiera och redigera:

- en [standard policy](#default-policy-options) som gäller för alla. och
- ytterligare [principer för specifika mottagare](#policies-that-apply-to-specific-email-recipients)

### <a name="default-policy-options"></a>Standard princip alternativ

Standard princip alternativ gäller för alla i organisationen.

****

|Det här alternativet|Gör det här|
|---|---|
|**Blockera följande URL: er**|Gör det möjligt för organisationen att ha en anpassad lista med URL-adresser som automatiskt blockeras. När användare klickar på en URL i den här listan kommer de till en [varnings sida](atp-safe-links-warning-pages.md) som förklarar varför URL-adressen blockeras. Mer information finns i [Konfigurera en anpassad lista över blockerade URL-adresser med Office 365 ATP-Safe-länkar](set-up-a-custom-blocked-urls-list-atp.md).|
|**Microsoft 365-appar för Enterprise, Office för iOS och Android**| När det här alternativet är markerat säkerhets säkra Länkar för ATP-säkerhet tillämpas på webb adresser i Word-, Excel-och PowerPoint-filer på Windows-eller Mac-datorer, e-postmeddelanden i Outlook, Office-dokument på iOS-eller Android-enheter, Visio 2016-filer i Windows och filer som är öppna i webb versioner av 365 Office-program|
|**Spåra inte när användare klickar på säkra Länkar för ATP**|När det här alternativet är markerat klickar du på data för URL: er i Word, Excel, PowerPoint, Visio-dokument och Outlook-e-postmeddelanden sparas inte.|
|**Låt inte användare klicka via säkra Länkar för ATP till ursprunglig URL**|Om du väljer det här alternativet kan användarna inte gå förbi en [varnings sida](atp-safe-links-warning-pages.md) till en webb adress som bedöms vara skadlig.|
|

### <a name="policies-that-apply-to-specific-email-recipients"></a>Principer som gäller för specifika e-postmottagare

****

|Det här alternativet|Gör det här|
|---|---|
|**Av**|Skannar inte URL-adresser i e-postmeddelanden.  <br/> Gör det möjligt att definiera en undantags regel, till exempel en regel som inte söker igenom URL-adresser i e-postmeddelanden för en viss grupp mottagare.|
|**På**|Skriver om URL: er för att dirigera användare via skydd mot säkerhet för ATP när användare klickar på URL: er i e-postmeddelanden och aktiverar säkerhet för ATP i Outlook (C2R) i Windows.  <br/> Kontrollerar en URL när någon klickar på en lista över blockerade eller skadliga URL: er och utlöser en sprängning av URL: en i bakgrunden asynkront om URL-adressen inte har ett giltigt rykte.|
|**Använda URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer**|När det här alternativet är markerat skannas misstänkta URL: er och länkar som pekar på nedladdnings Bart innehåll.|
|**Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet**|När du väljer det här alternativet hålls meddelanden som innehåller URL-adresser som ska genomsökas tills URL-adresserna har skannats och bekräftas vara säkra innan meddelanden levereras.|
|**Använda säkra Länkar för meddelanden som skickas inom organisationen** <br/> | När det här alternativet är tillgängligt och markerat används skydd för säkrade säkerhets samtal för e-postmeddelanden mellan personer i organisationen, förutsatt att e-postkonton finns i Office 365.|
|**Spåra inte användar klickningar**|När det här alternativet är markerat klickar du på data för URL: er i e-post från externa avsändare lagras inte. URL-adress klicka på spårning för länkar i e-postmeddelanden som skickas inom organisationen stöds för närvarande inte.|
|**Tillåt inte att användare klickar genom till ursprunglig URL**|Om du väljer det här alternativet kan användarna inte gå förbi en [varnings sida](atp-safe-links-warning-pages.md) till en webb adress som bedöms vara skadlig.|
|**Skriv inte om följande URL: er**|Lämnar URL-adresser som de är. Behåller en anpassad lista över säkra URL: er som inte behöver söka efter en viss grupp e-postmottagare i organisationen. Se [Konfigurera en anpassad URL-lista "Skriv inte över"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) för mer information, inklusive senaste ändringar av stöd för asterisker ( \* ).|
|

## <a name="next-steps"></a>Nästa steg

När dina principer för säker säkerhet för ATP är på plats kan du se hur ATP fungerar för organisationen genom att visa rapporter. Mer information finns i följande resurser:

- [Visa rapporter för Office 365 Avancerat skydd](view-reports-for-atp.md)

- [Använda Utforskaren i säkerhets & Compliance Center](threat-explorer.md)

Håll koll på nya funktioner som kommer till ATP. Besök [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).
