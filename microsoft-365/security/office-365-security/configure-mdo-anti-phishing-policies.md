---
title: Konfigurera principer mot nätfiske i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att skapa, ändra och ta bort avancerade principer mot nätfiske som är tillgängliga i organisationer med Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8cbe517ef2a702e3e4fd7f6af4ee1d7ed1dd13d2
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789158"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Konfigurera principer mot nätfiske i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Skydd mot nätfiske [i Microsoft Defender för Office 365](defender-for-office-365.md) kan skydda organisationen från skadliga personifieringsbaserade nätfiskeattacker och andra typer av nätfiskeattacker. Mer information om skillnaderna mellan principer för skydd mot nätfiske i Exchange Online Protection (EOP) och principer för skydd mot nätfiske i Microsoft Defender för Office 365 finns i Skydd mot [nätfiske.](anti-phishing-protection.md)

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för nätfiske. För mer detaljerad information kan du också skapa anpassade principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera principer mot nätfiske i Defender för Office 365 i Microsoft 365 säkerhetscenter eller i Exchange Online PowerShell.

Information om hur du konfigurerar de mer begränsade i principer för skydd mot nätfiske som är tillgängliga i Exchange Online Protection (det vill säga organisationer som saknar Defender för Office 365) finns i Konfigurera principer för skydd mot nätfiske [i EOP.](configure-anti-phishing-policies-eop.md)

De grundläggande elementen i en princip mot nätfiske är:

- **Anti-phish policy:** Anger nätfiskeskydden som aktiverar eller inaktiverar samt de alternativ som används.
- **Antifrasregeln**: Anger prioritet och mottagarfilter (som principen gäller för) för en nättfnig policy.

Skillnaden mellan dessa två element är inte uppenbart när du hanterar principer mot nätfiske i säkerhetscentret:

- När du skapar en princip skapar du faktiskt en antifishregel och den tillhörande antifishprincipen samtidigt som du använder samma namn för båda.
- När du ändrar en princip ändrar inställningar för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter den antifish-regeln. Alla andra inställningar ändrar den associerade nätfn-principen.
- När du tar bort en princip tas den nättfiska regeln och den tillhörande antifiska policyn bort.

I Exchange Online PowerShell hanterar du principen och regeln separat. Mer information finns i avsnittet Använda [Exchange Online PowerShell för att konfigurera principer mot nätfiske längre](#use-exchange-online-powershell-to-configure-anti-phishing-policies) fram i den här artikeln.

Alla Defender för Office 365-organisationer har en inbyggd policy mot nätfiske med namnet Office365-skyddstrecksstandard som har följande egenskaper:

- Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon antifrasregel (mottagarfilter) kopplad till principen.
- Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist). Alla anpassade policyer som du skapar har alltid högre prioritet.
- Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.

Om du vill öka effektiviteten i skydd mot nätfiske i Defender för Office 365 kan du skapa anpassade principer för skydd mot nätfiske med striktare inställningar som tillämpas för specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Microsoft 365 Säkerhetscenter på <https://security.microsoft.com/>. Om du vill gå direkt **till sidan Mot nätfiske** använder du <https://security.microsoft.com/antiphishing> .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill lägga till, ändra och ta bort principer  för skydd mot nätfiske måste du vara medlem i rollgrupperna Organisationshantering **eller Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till principer mot nätfiske måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.** <sup>\*</sup>

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Vi rekommenderar inställningar för principer mot nätfiske i Defender för Office 365 finns i Princip mot nätfiske i [Defender för Office 365 inställningar.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

- Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.

- Information om var principer för skydd mot nätfiske tillämpas i filtreringsförloppet finns i Ordning och [prioritet för e-postskydd.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a>Använda säkerhetscentret för att skapa principer för skydd mot nätfiske

Om du skapar en anpassad policy för nätfiske i säkerhetscentret skapas samtidigt den antifiska regeln och den tillhörande nätfiskeprincipen med samma namn för båda.

1. I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**

2. På sidan **Mot nätfiske** klickar du på ![ Skapa ikon ](../../media/m365-cc-sc-create-icon.png) **Skapa**.

3. Principguiden öppnas. Konfigurera **följande inställningar på** sidan Principnamn:
   - **Namn**: Ange ett unikt, beskrivande namn på principen.
   - **Beskrivning**: Ange en valfri beskrivning av principen.

   Klicka på **Nästa** när du är klar.

4. På sidan **Användare, grupper och domäner** som visas identifierar du de interna mottagare som principen gäller för (mottagarvillkor):
   - **Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.
   - **Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.
   - **Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.

   Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet. Upprepa det här steget så många gånger som det behövs. Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

   För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet. Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.

   Använd ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_) för flera värden i samma villkor. Använd OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_) för olika villkor.

   - **Exkludera dessa användare, grupper och domäner**: Om du vill lägga till undantag för interna mottagare som principen gäller för (Mottagarundantag), väljer du det här alternativet och konfigurerar undantagen. Inställningarna och beteendet är likadana som villkoren.

   Klicka på **Nästa** när du är klar.

5. Konfigurera följande **inställningar & skyddssidan** som visas på tröskelvärdet för nätfiske:

   - **Tröskelvärde för nätfiske:** Använd skjutreglaget för att välja något av följande värden:
     - **1 – Standard** (det här är standardvärdet.)
     - **2 – Aggressivt**
     - **3 – Mer aggressiva**
     - **4 – Mest aggressiva**

     Mer information finns i Avancerade [tröskelvärden för nätfiske i principer mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Personifiering:** De här inställningarna är ett villkor för principen som identifierar specifika avsändare som ska leta efter (individuellt eller per domän) i från-adressen till inkommande meddelanden. Mer information finns i Inställningar [för personifiering i principer för skydd mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

     > [!NOTE]
     >
     > - I varje princip mot nätfiske kan du ange högst 60 skyddade användare (avsändar-e-postadresser). Du kan inte ange samma skyddade användare i flera principer.
     >
     > - Skydd för användarpersonifiering fungerar inte om avsändaren och mottagaren tidigare har kommunicerat via e-post. Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifieringsförsök.

     - **Aktivera att användare skyddar:** Standardvärdet är inaktiverat (inte markerat). Om du vill aktivera den markerar du kryssrutan och klickar sedan på länken **Hantera (nn)** avsändare som visas.

       I den **utfällandefällningen Hantera avsändare** för personifieringsskydd som visas gör du så här:

       - **Interna avsändare: Klicka** på Lägg ![ till intern ikon Välj ](../../media/m365-cc-sc-add-internal-icon.png) **intern**. I den **utfällfältet Lägg** till interna avsändare som visas klickar du i rutan och väljer en intern användare i listan. Du kan filtrera listan genom att skriva in användaren och sedan välja användaren i resultatet. Du kan använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn och så vidare), men motsvarande visningsnamn visas i resultatet.

         Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

         När du är klar klickar du på Lägg **till**

       - **Externa avsändare: Klicka** på Lägg ![ till extern ikon Välj ](../../media/m365-cc-sc-create-icon.png) **extern**. I den **utfällna** menyn Lägg till externa  avsändare som visas anger du  ett visningsnamn i rutan Lägg till ett namn och en e-postadress i rutan Lägg till en **e-postadress.** Klicka sedan på Lägg till .

         Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

         När du är klar klickar du på Lägg **till**

       Tillbaka på den **utfällande listrutan** Hantera avsändare för personifiering kan du ta bort poster genom att välja en eller flera poster i listan. Du kan söka efter poster med hjälp av ![ ](../../media/m365-cc-sc-create-icon.png) **sökikonen Sök.**

       När du har markerat minst en post visas ikonen Ta bort markerade användare Ta bort markerade användare, som du kan använda för att ![ ta bort de markerade ](../../media/m365-cc-sc-remove-selected-users-icon.png)  posterna.

       Klicka på **Klar** när du är klar.

     - **Aktivera domäner att skydda:** Standardvärdet är av (inte markerat). Om du vill aktivera den markerar du kryssrutan och konfigurerar sedan en eller båda av följande inställningar:
       - **Inkludera de domäner som jag** äger : Om du vill aktivera den här inställningen markerar du kryssrutan. Om du vill visa de domäner som du äger klickar du **på Visa mina domäner**.
       - **Ta med egna** domäner: Aktivera den här inställningen genom att markera kryssrutan och sedan klicka på länken **Hantera (nn)** egna domäner som visas. I den **utfällande menyn Hantera egna domäner** för personifieringsskydd klickar du på ikonen Lägg till domäner Lägg till ![ ](../../media/m365-cc-sc-create-icon.png) **domäner.**

         I den **utfällliga** menyn Lägg  till egna domäner som visas klickar du i rutan Domän, anger ett värde och trycker på Retur eller väljer det värde som visas under rutan. Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du ![ikonen Ta bort](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

         När du är klar klickar du på Lägg **till domäner**

         > [!NOTE]
         > Du kan ha högst 50 domäner i alla principer mot nätfiske.

       På den **utfällande sidan** Hantera egna domäner för personifiering kan du ta bort poster genom att välja en eller flera poster i listan. Du kan söka efter poster med hjälp av ![ ](../../media/m365-cc-sc-create-icon.png) **sökikonen Sök.**

       När du har markerat minst en post visas ikonen Ta bort, som du kan använda ![ för att ta bort de markerade ](../../media/m365-cc-sc-delete-icon.png)  posterna.

   - **Lägga till betrodda** avsändare och domäner: : Ange undantag för personifieringsskydd för principen genom att klicka på Hantera **(nn)** betrodda avsändare och domäner. I den **utfällande menyn Hantera egna domäner** för personifieringsskydd konfigurerar du följande inställningar:
      - **Avsändare:** Kontrollera att fliken **Avsändare** är markerad och klicka på ![ ikonen Lägg till ](../../media/m365-cc-sc-create-icon.png) avsändare. I den **utfällfältet Lägg till** betrodda avsändare som visas anger du en e-postadress i rutan och klickar sedan på **Lägg till.** Upprepa det här steget så många gånger det behövs. Om du vill ta bort en befintlig post klickar ![ du på Ikonen Ta bort för ](../../media/m365-cc-sc-close-icon.png) posten.

        När du är klar klickar du på Lägg **till**.

      - **Domäner:** Välj fliken **Domän och** klicka på ikonen Lägg ![ till ](../../media/m365-cc-sc-create-icon.png) domäner.
  
        I den **utfällingsrutan** Lägg  till betrodda domäner som visas klickar du i rutan Domän, anger ett värde och trycker på Retur eller väljer det värde som visas under rutan. Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du ![ikonen Ta bort](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

        När du är klar klickar du på Lägg **till**.

     På den **utfällbar** fliken Hantera egna domäner för personifiering  kan du ta bort poster från flikarna Avsändare och Domän genom att välja en eller flera poster i listan.  Du kan söka efter poster med hjälp av ![ ](../../media/m365-cc-sc-create-icon.png) **sökikonen Sök.**

     När du har markerat minst en post visas **ikonen Ta** bort, som du kan använda för att ta bort de markerade posterna.

     Klicka på **Klar** när du är klar.

   - **Aktivera** postlådeintelligens: Standardvärdet är på (markerat) och vi rekommenderar att du låter det vara på. Om du vill inaktivera den avmarkerar du kryssrutan.

     - **Aktivera intelligence-baserat personifieringsskydd: Den** här inställningen är bara tillgänglig om **Aktivera postlådeintelligens** är på (markerad). Med den här inställningen kan postlådeinformation vidta åtgärder på meddelanden som identifieras som personifieringsförsök. Du anger vilken åtgärd som ska vidtas i **inställningen Om postlådeinformation identifierar en imiterad** användare på nästa sida.

       Vi rekommenderar att du aktiverar den här inställningen genom att markera kryssrutan. Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.

   - **Förfalskning**: I det här avsnittet använder du kryssrutan Aktivera **förfalskningsinformation** för att aktivera eller inaktivera förfalskningsinformation. Standardvärdet är på (markerat) och vi rekommenderar att du låter det vara på. Du anger vilken åtgärd som ska vidtas på meddelanden från blockerade förfalskningsavsändare i inställningen Om meddelande identifieras som **förfalskning** på nästa sida.

     Om du vill inaktivera förfalskningsinformation avmarkerar du kryssrutan.

     > [!NOTE]
     > Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället. Instruktioner finns i [Utökad filtrering för kopplingar i Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   Klicka på **Nästa** när du är klar.

6. På sidan **Åtgärder** som visas kan du konfigurera följande inställningar:

   - **Meddelandeåtgärder:** Konfigurera följande åtgärder i det här avsnittet:
     - **Om meddelandet identifieras som en imiterad** användare: Den här inställningen är bara tillgänglig om du har valt Aktivera användare att **skydda** på föregående sida. Välj någon av följande åtgärder i listrutan för meddelanden där avsändaren är en av de skyddade användare som du angav på föregående sida:
       - **Använd inte någon åtgärd**
       - **Omdirigera meddelandet till andra e-postadresser**
       - **Flytta meddelandet till mottagarnas skräppostmappar**
       - **Sätt meddelandet i karantän**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

     - **Om meddelandet identifieras som en** imiterad domän: Den här inställningen är bara tillgänglig om du har markerat Aktivera domäner att **skydda** på föregående sida. Välj någon av följande åtgärder i listrutan för meddelanden där avsändarens e-postadress finns i någon av de skyddade domäner som du angav på föregående sida:
       - **Använd inte någon åtgärd**
       - **Omdirigera meddelandet till andra e-postadresser**
       - **Flytta meddelandet till mottagarnas skräppostmappar**
       - **Sätt meddelandet i karantän**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

     - **Om postlådeintelligen identifierar** en imiterad användare : Den här inställningen är bara tillgänglig om du har markerat Aktivera intelligens för **personifieringsskydd** på föregående sida. Välj någon av följande åtgärder i listrutan för meddelanden som identifierats som personifieringsförsök av postlådeinformation:
       - **Använd inte någon åtgärd**
       - **Omdirigera meddelandet till andra e-postadresser**
       - **Flytta meddelandet till mottagarnas skräppostmappar**
       - **Sätt meddelandet i karantän**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

     - **Om meddelandet identifieras som förfalskning: Den** här inställningen är bara tillgänglig om du har markerat Aktivera **förfalskningsinformation** på föregående sida. Välj någon av följande åtgärder i listrutan för meddelanden från blockerade förfalskningsavsändare:
       - **Flytta meddelandet till mottagarnas skräppostmappar**
       - **Sätt meddelandet i karantän**

   - **Säkerhetstips för &**: Konfigurera följande inställningar:
     - **Visa funktionen för användarpersonifiering säkerhetstips:** Den här inställningen är bara tillgänglig om du har markerat Aktivera användare **att skydda** på föregående sida.
     - **Visa domänpersonifiering säkerhetstips:** Den här inställningen är bara tillgänglig om du har markerat Aktivera **domäner att skydda** på föregående sida.
     - **Visa ovanliga tecken för användarpersonifiering säkerhetstips** Den här inställningen är bara tillgänglig om du **har markerat Aktivera användare för att** skydda eller Aktivera domäner att **skydda** på föregående sida.
     - **Visa (?) för oauthenticerade** avsändare för förfalskning: Den här inställningen är bara tillgänglig om du har markerat Aktivera **förfalskningsinformation** på föregående sida. Lägger till ett frågetecken på avsändarens foto i rutan Från i Outlook om meddelandet inte  klarar SPF eller DKIM kontrollerar och meddelandet inte klarar DMARC eller sammansatt [autentisering.](email-validation-and-authentication.md#composite-authentication)
     - **Visa via-taggen:** Den här inställningen är bara tillgänglig om du **har markerat Aktivera förfalskningsinformation** på föregående sida. Lägger till en via-tagg (chris@contoso.com via fabrikam.com) till från-adressen om den skiljer sig från domänen i DKIM-signaturen eller **MAIL FROM-adressen.** Standardvärdet är på (markerat). Om du vill inaktivera den avmarkerar du kryssrutan.

       > [!NOTE]
       > För närvarande är **tagginställningen Visa via** inte tillgänglig i alla organisationer. Om du inte har tagginställningen **Visa "via"**  styrs frågetecknet och via-taggen av Show **(?) för oauthenticerade** avsändare för förfalskning i organisationen.

     Markera kryssrutan om du vill aktivera en inställning. Om du vill inaktivera den avmarkerar du kryssrutan.

   Klicka på **Nästa** när du är klar.

7. Granska inställningarna på sidan **Granska** som visas. Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.

   När du är klar klickar du på **Skicka.**

8. På bekräftelsesidan som visas klickar du på **Klar**.

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a>Använd säkerhetscentret för att visa principer för skydd mot nätfiske

1. I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**

2. På **sidan Mot nätfiske** visas följande egenskaper i listan över principer mot nätfiske:

   - **Namn**
   - **Status**
   - **Prioritet**
   - **Senast ändrad**

3. När du väljer en princip genom att klicka på namnet visas principinställningarna i en utfällbladstext.

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a>Använda säkerhetscentret för att ändra principer för skydd mot nätfiske

1. I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**

2. På sidan **Mot nätfiske** väljer du en princip i listan genom att klicka på namnet.

3. I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Mer information om inställningarna finns i avsnittet Använda [säkerhetscentret för](#use-the-security-center-to-create-anti-phishing-policies) att skapa principer mot nätfiske längre fram i den här artikeln.  

   Standardprincipen för skydd mot nätfiske är avsnittet **Användare,** grupper och domäner inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.

Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aktivera eller inaktivera anpassade principer för skydd mot nätfiske

Du kan inte inaktivera standardprincipen för nätfiske.

1. I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**

2. På sidan **Mot nätfiske** väljer du en anpassad princip i listan genom att klicka på namnet.

3. Högst upp i den utfällda menyn principinformation ser du något av följande värden:
   - **Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .
   - **Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.

4. I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.

5. Klicka **Stäng** i den utfällda menyn principinformation.

Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Ange prioritet för anpassade principer för skydd mot nätfiske

Som standard prioriteras principer mot nätfiske baserat på i vilken ordning de skapades (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Säkerhetscenter). Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.

 **Anmärkningar**:

- I säkerhetscentret kan du bara ändra prioriteten för nätfiskeprincipen när du har skapat den. I PowerShell kan du åsidosätta standardprioritet när du skapar antifrasregeln (vilket kan påverka prioriteringen för befintliga regler).
- Principer för skydd mot nätfiske bearbetas i den ordning som de visas (den första principen har **prioritetsvärdet** 0). Standardprincipen för skydd mot nätfiske har **prioritetsvärdet Lägsta** och du kan inte ändra den.

1. I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**

2. På sidan **Mot nätfiske** väljer du en anpassad princip i listan genom att klicka på namnet.

3. Högst upp i den utfällda menyn principinformation som visas ser du **Öka prioritet** eller **Minska prioritet** baserat på det aktuella prioritetsvärdet och antalet anpassade principer:
   - Principen mot nätfiske med **prioritetsvärdet 0** har endast alternativet **Minska prioritet** tillgängligt. 
   - Principen mot nätfiske med lägst **prioritetsvärde** (till exempel **3**) har endast alternativet **Öka** prioritet tillgängligt.
   - Om du har tre eller fler principer för skydd mot nätfiske  finns det både alternativ för öka prioritet och minska prioritet mellan de högsta och lägsta  prioritetsvärdena.

   Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.

4. Klicka **Stäng** i den utfällda menyn principinformation när du är klar.

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a>Använda säkerhetscentret för att ta bort anpassade principer för nätfiske

När du använder säkerhetscentret för att ta bort en anpassad policy mot nätfiske tas både nätfiskeregeln och motsvarande nätfiskeprincip bort. Du kan inte ta bort standardprincipen för nätfiske.

1. I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.**

2. Välj en anpassad princip i listan genom att klicka på namnet på principen. Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.

3. I bekräftelsedialogrutan som visas klickar du på **Ja**.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske

Som tidigare beskrivits består en policy mot skräppost av en anti-phish-policy och en anti-phish-regel.

I Exchange Online PowerShell visar sig skillnaden mellan anti-phish-policyer och anti-phish-regler. Du hanterar antifish-principer med hjälp av cmdletarna **\* -AntiPhishPolicy** och du hanterar anti-phish-regler med hjälp av cmdletarna **\* -AntiPhishRule.**

- I PowerShell skapar du först den nätfiska principen och sedan skapar du den skyddande phish-regeln som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna separat i antifish-principen och antifish-regeln.
- När du tar bort en anti-phish-policy från PowerShell tas inte motsvarande anti phish-regel bort automatiskt, och vice versa.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Använda PowerShell för att skapa principer för skydd mot nätfiske

Det krävs två steg för att skapa en princip mot nätfiske i PowerShell:

1. Skapa den anfish-policy som du sedan skapar.
2. Skapa den anti phish-regel som anger den antifishpolicy som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny anti-phish-regel och tilldela en befintlig, oassocierad antifishprincip till den. An anti-phish rule can't be associated with more than one anti-phish policy.
- Du kan konfigurera följande inställningar för nya skyddsprinciper i PowerShell som inte är tillgängliga i säkerhetscentret förrän du har skapat principen:
  - Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på cmdleten **New-AntiPhishRule).**
  - Ange prioritet för principen vid skapandet (_Prioritet_ _\<Number\>_ ) på **cmdleten New-AntiPhishRule).**
- En ny anti-phish-policy som du skapar i PowerShell visas inte i säkerhetscentret förrän du tilldelar principen till en antifishregel.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Steg 1: Använd PowerShell för att skapa en anti-phish-policy

Använd följande syntax för att skapa en antifishpolicy:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas en antifishprincip som heter Forskningsin karantän med följande inställningar:

- Principen är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).
- Beskrivningen är: Forskningavdelningens policy.
- Ger skydd av organisationsdomäner för alla godkända domäner och skydd för riktade domäner fabrikam.com.
- Anger MaiOrto (mfujito@fabrikam.com) som användaren som ska skydda från personifiering.
- Aktiverar postlådeintelligens.
- Aktiverar postlådeintelligensskydd och anger karantänåtgärden.
- Aktiverar säkerhetstips.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Detaljerad information om syntax och parametrar finns [i New-AntiPhishPolicy.](/powershell/module/exchange/New-AntiPhishPolicy)

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Steg 2: Använd PowerShell för att skapa en antifishregel

Använd följande syntax för att skapa en antifishregel:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

I det här exemplet skapas en antifishregel som heter Forskningsavdelningen med följande villkor:

- Regeln är kopplad till den nättfiska principen som heter Research Quarantine.
- Regeln gäller för medlemmar i gruppen Research Department.
- Eftersom vi inte använder _parametern Priority_ används standardprioritet.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Detaljerad information om syntax och parametrar finns [i New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Använda PowerShell för att se nätträcksprinciper

Om du vill se befintliga skyddsprinciper använder du följande syntax:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattning av alla antifishpolicys tillsammans med de angivna egenskaperna.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

Det här exemplet returnerar alla egenskapsvärden för den nättfiska policyn cheferna.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Detaljerad information om syntax och parametrar finns i [Get-AntiPhishPolicy.](/powershell/module/exchange/Get-AntiPhishPolicy)

### <a name="use-powershell-to-view-anti-phish-rules"></a>Använda PowerShell för att se nätträcksregler

Använd följande syntax för att visa befintliga skydd mot phish-regler:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattning av alla nättringsregler tillsammans med de angivna egenskaperna.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

I det här exemplet returneras alla egenskapsvärden för den nättfiska regeln Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns [i Get-AntiPhishRule.](/powershell/module/exchange/Get-AntiPhishrule)

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Använda PowerShell för att ändra skydd mot nättfingor

Förutom följande objekt är samma inställningar tillgängliga när du ändrar en [anti-phish-princip](#step-1-use-powershell-to-create-an-anti-phish-policy) i PowerShell som när du skapar principen enligt beskrivningen i Steg 1: Använda PowerShell för att skapa ett avsnitt för en anti-phish-policy tidigare i den här artikeln.

- Växeln _MakeDefault_ som omvandlar den angivna principen till  standardprincipen (används för alla, alltid lägst prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en nätfnig princip i PowerShell.

- Du kan inte byta namn på en nätt **phish-policy (cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._ När du byter namn på en policy mot nätfiske i säkerhetscentret byter du bara namn på _nätfiskeregeln._

Använd följande syntax för att ändra en nätt phish-policy:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns [i Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Använda PowerShell för att ändra skydd mot phish-regler

Den enda inställningen som inte är tillgänglig när du ändrar en antifishregel i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel. Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga skyddsregler.

Annars finns det inga ytterligare inställningar tillgängliga när du ändrar en antifn-regel i PowerShell. Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i steg 2: Använd PowerShell för att skapa en [nättfingrregel](#step-2-use-powershell-to-create-an-anti-phish-rule) längre fram i den här artikeln.

Använd följande syntax för att ändra en antifishregel:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns [i Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Använda PowerShell för att aktivera eller inaktivera nätthetsregler

Om du aktiverar eller inaktiverar en nätfiskeregel i PowerShell aktiveras eller inaktiveras hela nätfiskeprincipen (nätfiskeregeln och den tilldelade nätfiskeprincipen). Du kan inte aktivera eller inaktivera standardprincipen för nätfiske (den används alltid för alla mottagare).

Om du vill aktivera eller inaktivera en nätträcksregel i PowerShell använder du följande syntax:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras den phish-regeln Marknadsföringsavdelningen.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns [i Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) [och Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Använd PowerShell för att ange prioriteten för nätträcksregler

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Om du vill ange prioriteten för en anti-phish-regel i PowerShell använder du följande syntax:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Anmärkningar**:

- Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-AntiPhishRule** i stället.

- Den förvalda antifish-principen har inte en motsvarande antifiska regel och har alltid det oföränderliga prioritetsvärdet **Lägsta.**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Använda PowerShell för att ta bort nättfällprinciper

När du använder PowerShell för att ta bort en anti-phish-policy tas motsvarande anti phish-regel inte bort.

Om du vill ta bort en anti-phish-policy i PowerShell använder du följande syntax:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

I det här exemplet tas den nättfiska policyn Marketing Department bort.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Använda PowerShell för att ta bort nätträcksregler

När du använder PowerShell för att ta bort en anti-phish-regel tas motsvarande anti-phish-policy inte bort.

Om du vill ta bort en anti-phish-regel i PowerShell använder du följande syntax:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

I det här exemplet tas den antifiska regeln Marknadsföringsavdelningen bort.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Verifiera att du har konfigurerat principer för skydd mot nätfiske i Defender för Office 365 genom att göra något av följande:

- I säkerhetscentret går du till avsnittet & **för** & principer för skydd mot \> **nätfiske** i \>  \>  \> **säkerhetscentret.** Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.** Om du vill visa mer information väljer du principen i listan genom att klicka på namnet och visa informationen i den utfäll vy som visas.

- I Exchange Online Ersätt med namnet på principen eller regeln i PowerShell och kör \<Name\> följande kommando och verifiera inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
