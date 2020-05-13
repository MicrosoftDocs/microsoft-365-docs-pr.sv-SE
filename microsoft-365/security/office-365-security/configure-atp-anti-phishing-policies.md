---
title: Konfigurera principer för ATP-skydd mot nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du skapar, ändrar och tar bort de avancerade anti-phishing-principer som är tillgängliga i organisationer med Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: efecd830db7ed10210605e31aa0ded2599de1b72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208893"
---
# <a name="configure-atp-anti-phishing-policies"></a>Konfigurera principer för ATP-skydd mot nätfiske

ATP:s principer för phishing är en del av [Office 365 Advanced Threat Protection](office-365-atp.md). ATP:s principer för nätfiske kan skydda din organisation från skadliga nätfiskeattacker och andra typer av nätfiskeattacker. Mer information om skillnaderna mellan anti-phishing-policyer i EOP (Exchange Online Protection) och ATP:s principer för phishing finns i [Anti-phishing protection](anti-phishing-protection.md).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för ATP-phishing. För större granularitet kan du också skapa anpassade ATP-principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera ATP-principer för nätfiske i Security & Compliance Center eller i Exchange Online PowerShell.

Information om hur du konfigurerar de mer begränsade i anti-phishing-principer som är tillgängliga i Exchange Online Protection-organisationer (det vill säga Microsoft 365-organisationer utan Office 365 ATP) finns [i Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-exchange-online-powershell"></a>ATP:s principer för phishing-bekämpning i Security & Compliance Center vs Exchange Online PowerShell

De grundläggande inslagen i en ATP-policy mot nätfiske är:

- **Anti-phish-principen**: Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras och vilka åtgärder som ska tillämpas.

- **Anti-phish-regeln**: Anger prioritets- och mottagarfilter (vem principen gäller för) för en anti-phish-princip.

Skillnaden mellan dessa två element är inte uppenbar när du hanterar ATP-principer för phishing-bekämpning i Security & Compliance Center:

- När du skapar en ATP-anti-phishing-princip i Security & Compliance Center skapar du faktiskt en anti-phish-regel och den associerade anti-phish-principen samtidigt med samma namn för båda.

- När du ändrar en ATP-anti-phishing-princip i Security & Compliance Center ändras reglerna för namn, prioritet, aktiverad eller inaktiverad och mottagarfilter anti-phish-regeln. Alla andra inställningar ändrar den associerade anti-phish-principen.

- När du tar bort en ATP-anti-phishing-princip från Security & Compliance Center tas anti-phish-regeln och den associerade anti-phish-principen bort.

I Exchange Online PowerShell är skillnaden mellan anti-phish-principer och anti-phish-regler uppenbar. Du hanterar anti-phish-principer med hjälp av cmdlets ** \* -AntiPhishPolicy** och hanterar anti-phish-regler med hjälp av cmdlets ** \* -AntiPhishRule.**

- I PowerShell skapar du principen anti-phish först och sedan skapar du anti-phish-regeln som identifierar den princip som regeln gäller för.

- I PowerShell ändrar du inställningarna i anti-phish-principen och anti-phish-regeln separat.

- När du tar bort en anti-phish-princip från PowerShell tas inte motsvarande anti-phish-regel bort automatiskt och vice versa.

### <a name="default-atp-anti-phishing-policy"></a>Standardprincip för ATP-phishing

Varje ATP-organisation har en inbyggd ATP-anti-phishing-princip med namnet Office365 AntiPhish Default som har följande egenskaper:

- Anti-phish-principen med namnet Office365 AntiPhish Default tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-phish-regel (mottagarfilter) som är associerad med principen.

- Principen Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist). Alla anpassade principer som du skapar har alltid högre prioritet än principen Office365 AntiPhish Default.

- Principen som heter Office365 AntiPhish Default är standardprincipen (egenskapen **IsDefault** har `True` värdet) och du kan inte ta bort standardprincipen.

Om du vill öka effektiviteten i skyddet mot nätfiske kan du skapa anpassade ATP-principer mot nätfiske med striktare inställningar som tillämpas på specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **ATP:s sida mot nätfiske** använder du <https://protection.office.com/antiphishing> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** För skrivskyddad åtkomst till anti-phishing-principer måste du vara medlem i rollgruppen **Säkerhetsläsare.** Mer information om rollgrupper i säkerhets- och efterlevnadscentret finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- Våra rekommenderade inställningar för ATP-principer för nätfiske finns i [Principinställningar för Office ATP-phishing](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).

- Tillåt upp till 30 minuter för en ny eller uppdaterad princip som ska tillämpas.

- Information om var principer mot nätfiske tillämpas i filtreringspipelinen finns i [Ordning och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>Använd Security & Compliance Center för att skapa ATP-principer för nätfiske

Om du skapar en anpassad ATP-anti-phishing-princip i Security & Compliance Center skapas anti-phish-regeln och den associerade anti-phish-principen samtidigt med samma namn för båda.

När du skapar en ATP-princip mot nätfiske kan du bara ange principnamn, beskrivning och mottagarfilter som identifierar vem principen gäller för. När du har skapat principen kan du ändra principen för att ändra eller granska standardinställningarna mot nätfiske.

1. I Security & Compliance Center går **Threat management** du till \> **Policy** \> **ATP-principen**mot hothantering.

2. Klicka på **Skapa**på sidan **Anti-phishing.**

3. Guiden **Skapa en ny anti-phishing-princip** öppnas. Konfigurera följande inställningar på sidan Namn på **principen:**

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   När du är klar klickar du på **Nästa**.

4. På sidan **Tillämpad på** som visas identifierar du de interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<mottagare1\>_ eller _\<mottagare2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<mottagare1\>_ och _\<medlem i grupp 1\>_).

   Klicka på **Lägg till ett villkor**. I listrutan som visas väljer du ett villkor under **Tillämpad om:**

   - **Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
   - **Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.
   - **Mottagardomänen är**: Anger mottagare i en eller flera av de konfigurerade accepterade domänerna i organisationen.

   När du har valt villkoret visas en motsvarande listruta med rutan **Någon av dessa.**

   - Klicka i rutan och bläddra igenom listan med värden att välja.
   - Klicka i rutan och börja skriva för att filtrera listan och välj ett värde.
   - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
   - Om du vill ta bort enskilda poster klickar du på **Ikonen Ta bort** ta bort i ![ ](../../media/scc-remove-icon.png) värdet.
   - Om du vill ta bort hela villkoret klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) villkoret.

   Om du vill lägga till ytterligare ett villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **Tillämpat om**.

   Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under Förutom **om**. Inställningarna och beteendet är likadana som villkoren.

   När du är klar klickar du på **Nästa**.

5. Granska **inställningarna** på sidan Granska dina inställningar. Du kan klicka på **Redigera** på varje inställning för att ändra den.

   När du är klar klickar du på **Skapa den här principen**.

6. Klicka på **OK** i bekräftelsedialogrutan som visas.

När du har skapat ATP:s anti-nätfiskeprincip med de här allmänna principinställningarna använder du instruktionerna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>Använda Security & Compliance Center för att ändra ATP:s principer för phishing-phishing

Använd följande procedurer för att ändra ATP:s principer för nätfiske: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.

1. Om du inte redan är där öppnar du Security & **Threat management** Compliance Center och går till \> **Policy** \> **ATP-principen**mot nätfiske mot hothantering .

2. Välj den anpassade ATP-principen mot nätfiske som du vill ändra. Om den redan är markerad avmarkerar du den och markerar den igen.

3. Den **utfällbara sidan Redigera ditt \< principnamn \> ** visas. Om du klickar på **Redigera** i ett avsnitt får du tillgång till inställningarna i det avsnittet.

   - Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).

   - När du har **klickat** på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men du kan hoppa inom sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Ikonen Avbryt** eller **Stäng** avsluta för att återgå till sidan Redigera ![ ditt ](../../media/scc-remove-icon.png) ** \< principnamn \> ** (du behöver inte besöka den sista sidan i guiden för att spara eller lämna).

4. **Principinställning**: Klicka på **Redigera** om du vill ändra samma inställningar som var tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) i föregående avsnitt:

   - **Name**
   - **Beskrivning**
   - **Tillämpas på**
   - **Granska dina inställningar**

   När du är klar klickar du på **Spara** på valfri sida.

5. **Personifiering:** Klicka på **Redigera** om du vill ändra skyddade avsändare och skyddade domäner i principen. Dessa inställningar är ett villkor för principen som identifierar förfalskade avsändare att söka efter (individuellt eller efter domän) i Från-adressen för inkommande meddelanden. Mer information finns [i Inställningar för personifiering i ATP:s principer för phishing.](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)

   - **Lägg till användare för att skydda:** Standardvärdet är **Av**. Om du vill aktivera den drar du växlingsknappen till **På**och klickar sedan på knappen **Lägg till användare** som visas.

     Konfigurera följande värden i utfällningen **för Lägg till användare:**

     - **E-postadress:**

        - Klicka i rutan och bläddra igenom listan över användare att välja.
        - Klicka i rutan och börja skriva för att filtrera listan och välj en användare.
        - Om du vill ta bort en post klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) användaren.

     - **Namn**: Det här värdet fylls i baserat på den e-postadress du har valt, men du kan ändra det.

     När du är klar klickar du på **Spara** på valfri sida.

    Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.

   - **Lägg till domäner som ska skyddas:** Konfigurera en eller båda av följande inställningar:

     - **Inkludera automatiskt de domäner jag äger:** Standardvärdet är **Av**. Om du vill aktivera den drar du växlingsknappen till **På**.
     - **Inkludera anpassade domäner:** Standardvärdet är **Av**. Om du vill aktivera den drar du växlingsknappen till **På**och i rutan **Lägg till domäner** anger du domännamnet (till exempel contoso.com), trycker på RETUR och upprepar vid behov.

   - **Åtgärder**: Klicka på **Redigera**

     - **Om e-post skickas av en personifierad användare:** Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren är en av de skyddade användare som du har angett i **Lägg till användare för att skydda:**

       - **Använd inga åtgärder**
       - **Omdirigera meddelande till andra e-postadresser**
       - **Flytta meddelande till mappen Skräppost**
       - **Karantän meddelandet**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

     - **Om e-post skickas av en personifierad domän:** Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren finns i en av de skyddade domäner som du har angett i **Lägg till domäner för att skydda:**

     - **Använd inga åtgärder**
     - **Omdirigera meddelande till andra e-postadresser**
     - **Flytta meddelande till mappen Skräppost**
     - **Karantän meddelandet**
     - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
     - **Ta bort meddelandet innan det levereras**

   - Klicka **på aktivera säkerhetstips för personifiering** och konfigurera någon av följande inställningar:

     - **Visa tips för personifierade användare:** Standardvärdet är **Av**. Om du vill aktivera den drar du växlingsknappen till **På**.
     - **Visa tips för personifierade domäner**: Standardvärdet är **Av**. Om du vill aktivera den drar du växlingsknappen till **På**.
     - **Visa tips för ovanliga tecken:** Standardvärdet är **Av**. Om du vill aktivera den drar du växlingsknappen till **På**.

     Klicka på **Spara** när du är klar.

   - **Brevlåda intelligens:**

     - **Aktivera postlådeinformation?**: Standardvärdet är **På**. Om du vill inaktivera den drar du växlingsknappen till **Av**.

     - **Aktivera informationsskydd för postlådainformationsbaserad personifiering?**: Den här inställningen är endast tillgänglig om **Aktivera postlådeinformation?** är **På**.

       I **Om e-post skickas av en personifierad användare**kan du ange en av följande åtgärder för att ta på meddelanden som inte kan skicka postlådeinformation (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):

       - **Använd inga åtgärder**
       - **Omdirigera meddelande till andra e-postadresser**
       - **Flytta meddelande till mappen Skräppost**
       - **Karantän meddelandet**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

   - **Lägg till betrodda avsändare och domäner**: Ange undantag för principen:

     - **Betrodda avsändare:**

       - Klicka i rutan och bläddra igenom listan över användare att välja.
       - Klicka i rutan och börja skriva för att filtrera listan och välj en användare.
       - Om du vill ta bort en post klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) användaren.

     - **Betrodda domäner**: Ange domännamnet (till exempel contoso.com), tryck på RETUR och upprepa vid behov.

   - **Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka på **Redigera** i varje avsnitt om du vill gå tillbaka till den aktuella sidan.
     - Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:

       - **Skyddade användare**
       - **Skyddade domäner** \> **Inkludera domäner som jag äger**
       - **Skyddade domäner** \> **Skyddade domäner** (anpassade domäner)
       - **Information om brevlåda**

   När du är klar klickar du på **Spara** på valfri sida.

6. **Spoof**: Klicka på **Redigera** om du vill aktivera eller inaktivera falska underrättelser, inaktivera oautentiserade avsändande avsändare i Outlook på eller inaktivera och konfigurera åtgärden så att den gäller för meddelanden från blockerade förfalskade avsändare. Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).

   Observera att samma inställningar också är tillgängliga i anti-phishing-principer i EOP.

   - **Spoofing filterinställningar:** Standardvärdet är **På**, och vi rekommenderar att du lämnar den på. Om du vill inaktivera den drar du växlingsknappen till **Av**. Mer information finns [i Konfigurera falska underrättelser i EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Microsoft 365. du aktiverar utökad filtrering för kopplingar i stället. Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Aktivera funktionen Oautentiserade avsändare:** Standardvärdet är **På**. Om du vill inaktivera den drar du växlingsknappen till **Av**.

   - **Åtgärder**: Ange vilken åtgärd som ska vidtas för meddelanden som inte innehåller falska underrättelser:

     **Om e-post skickas av någon som inte får förfalska din domän:**

     - **Flytta meddelande till mottagarnas skräppostmappar**
     - **Karantän meddelandet**

   - **Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka på **Redigera** i varje avsnitt om du vill gå tillbaka till den aktuella sidan.
     - Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:

       - **Aktivera skydd mot förfalskning**
       - **Aktivera funktionen Oautentiserad avsändare**

   När du är klar klickar du på **Spara** på valfri sida.

7. **Avancerade inställningar**: Klicka på **Redigera** för att konfigurera de avancerade tröskelvärdena för nätfiske. Mer information finns [i Avancerade tröskelvärden för nätfiske i ATP:s principer för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).

   - **Avancerade tröskelvärden för nätfiske**: Välj ett av följande värden:

   - **1 - Standard** (Detta är standardvärdet.)
   - **2 - Aggressiv**
   - **3 - Mer aggressiv**
   - **4 - Mest aggressiva**

   - **Granska dina inställningar**: Klicka på **Redigera** för att gå tillbaka till sidan **Avancerade nätfiskegränser.**

   När du är klar klickar du på **Spara** på någon av sidor.

8. Tillbaka på sidan **Redigera \< \> principnamn,** granska inställningarna och klicka sedan på **Stäng**.

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>Använd Security & Compliance Center för att ändra standardprincipen för ATP-phishing

Standardprincipen för ATP-phishing heter Office365 AntiPhish Default och visas inte i listan över principer. Så här ändrar du standardprincipen för ATP-bekämpningsfiske:

1. I Security & Compliance Center går **Threat management** du till \> **Policy** \> **ATP-principen**mot hothantering.

2. Klicka på **Standardprincip**på sidan **Anti-phishing.**

3. Sidan **Redigera din princip office365 AntiPhish Standard** visas. Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip:](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)

   - **Personifiering**
   - **Spolat**
   - **Avancerade inställningar**

   Följande inställningar är inte tillgängliga när du ändrar standardprincipen:

   - Du kan se avsnittet **Principinställning** och värden, men det finns ingen **redigera** länk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)).
   - Du kan inte ta bort standardprincipen.
   - Du kan inte ändra prioriteten för standardprincipen (den tillämpas alltid sist).

4. På sidan **Redigera din princip office365 AntiPhish Standard** granskar du inställningarna och klickar sedan på **Stäng**.

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>Aktivera eller inaktivera anpassade ATP-principer för phishing

1. I Security & Compliance Center går **Threat management** du till \> **Policy** \> **ATP-principen**mot hothantering.

2. Lägg märke till värdet i kolumnen **Status:**

   - Dra växlingsknappen till **Av** för att inaktivera principen.

   - Dra växlingsknappen till **På** för att aktivera principen.

Du kan inte inaktivera standardpolicyn mot nätfiske.

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>Ange prioritet för anpassade ATP-principer för nätfiske

Som standard ges ATP-principer för phishing en prioritet som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Två principer kan inte ha samma prioritet.

Anpassade ATP-principer för nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0). Standardprincipen mot nätfiske med namnet Office365 AntiPhish Default har det anpassade **prioritetsvärdet Lägsta**och du kan inte ändra det.

 **I**Security & Compliance Center kan du bara ändra prioriteten för ATP-principen mot nätfiske när du har skapat den. I PowerShell kan du åsidosätta standardprioriteten när du skapar anti-phish-regeln (vilket kan påverka prioriteten för befintliga regler).

Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra **prioritetsnumret** i säkerhets- & compliance center). Det är bara meningsfullt att ändra prioriteten för en princip om du har flera principer.

1. I Security & Compliance Center går **Threat management** du till \> **Policy** \> **ATP-principen**mot hothantering.

2. Markera den princip som du vill ändra. Om den redan är markerad avmarkerar du den och markerar den igen.

3. Den **utfällbara sidan Redigera ditt \< principnamn \> ** visas.

   - Den anpassade ATP-principen mot nätfiske med **prioritetsvärde** **0** har bara knappen **Minska prioritet** tillgänglig.

   - Den anpassade ATP-principen mot nätfiske med det lägsta **prioritetsvärdet** (till exempel **3)** har bara knappen **Öka prioritet** tillgänglig.

   - Om du har tre eller flera anpassade anti-phishing-principer har principer mellan de högsta och lägsta prioritetsvärdena både knapparna **Öka prioritet** och **Minska prioritet** tillgängliga.

4. Klicka på **Öka prioritet** eller **Minska prioritet** om du vill ändra **prioritetsvärdet.**

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>Använda Security & Compliance Center för att visa ATP-principer för nätfiske

1. I Security & Compliance Center och gå **Threat management** till \> **Policy** \> **Atp-anti-phishing-principen**mot hothanteringspolicy .

2. Gör något av följande:

   - Välj en anpassad ATP-anti-phishing-princip som du vill visa. Om den redan är markerad avmarkerar du den och markerar den igen.

   - Klicka på **Standardprincip** om du vill visa standardprincipen mot nätfiske.

3. Den **utfällbara sidan Redigera ditt \< principnamn \> ** visas, där du kan visa inställningar och värden.

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>Använd Security & Compliance Center för att ta bort ATP-principer för nätfiske

1. I Security & Compliance Center går **Threat management** du till \> **Policy** \> **ATP-principen**mot hothantering.

2. Markera den princip som du vill ta bort. Om den redan är markerad avmarkerar du den och markerar den igen.

3. Klicka på **Ta bort princip i**den utfällbara principen Redigera ditt ** \< \> principnamn** som visas och klicka sedan på **Ja** i varningsdialogrutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>Använda Exchange Online PowerShell för att konfigurera ATP-principer för phishing

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Använda PowerShell för att skapa principer mot nätfiske

Att skapa en anti-phishing-policy i PowerShell är en tvåstegsprocess:

1. Skapa anti-phish-principen.

2. Skapa anti-phish-regeln som anger den anti-phish-princip som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny anti-phish-regel och tilldela den en befintlig, oassocierad anti-phish-princip. En anti-phish regel kan inte associeras med mer än en anti-phish politik.

- Du kan konfigurera följande inställningar för nya anti-phish-principer i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:

  - Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny anti-AntiPhishRule).**

  - Ange prioritet för principen när du skapar _ \< \> (Prioritetsnummer)_ på cmdleten **Ny anti-AntiPhishRule).** _Priority_

- En ny anti-phish-princip som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en anti-phish-regel.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Steg 1: Använd PowerShell för att skapa en anti-phish-policy

Om du vill skapa en anti-phish-princip använder du den här syntaxen:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas anti-phish-principen Research Quarantine med följande inställningar:

- Principen är aktiverad (vi använder inte parametern _Aktiverad_ och standardvärdet är `$true` ).
- Beskrivningen är: Forskningsavdelningens policy.
- Aktiverar organisationsdomänskydd för alla accepterade domäner och riktade domänskydd för fabrikam.com.
- Anger Mai Fujito (mfujito@fabrikam.com) som användare för att skydda mot personifiering.
- Aktiverar postlådeinformation.
- Aktiverar intelligensskydd för postlådor och anger karantänåtgärden.
- Möjliggör säkerhetstips.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Detaljerad syntax- och parameterinformation finns i [Ny-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Steg 2: Använd PowerShell för att skapa en anti-phish-regel

Om du vill skapa en anti-phish-regel använder du den här syntaxen:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

I det här exemplet skapas en anti-phish-regel med namnet Forskningsavdelningen med följande villkor:

- Regeln är associerad med anti-phish-principen som heter Forskningskarantän.
- Regeln gäller för medlemmar i gruppen som heter Forskningsavdelningen.
- Eftersom vi inte använder parametern _Prioritet_ används standardprioriteten.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Detaljerad syntax- och parameterinformation finns i [Ny anti-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Använda PowerShell för att visa anti-phish-principer

Om du vill visa befintliga anti-phish-principer använder du följande syntax:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

I det här exemplet returneras en sammanfattningslista över alla anti-phish-principer tillsammans med de angivna egenskaperna.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

I det här exemplet returneras alla egenskapsvärden för anti-phish-principen Chefer.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Använda PowerShell för att visa anti-phish-regler

Om du vill visa befintliga anti-phish-regler använder du följande syntax:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

I det här exemplet returneras en sammanfattningslista över alla anti-phish-regler tillsammans med de angivna egenskaperna.

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

I det här exemplet returneras alla egenskapsvärden för anti-phish-regeln Contoso-chefer.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Använda PowerShell för att ändra anti-phish-principer

Andra än följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett anti-phish-principavsnitt](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i det här avsnittet.

- _MakeDefault-växeln_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid **lägsta** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en anti-phish-princip i PowerShell.

- Du kan inte byta namn på en anti-phish-princip **(cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._ När du byter namn på en anti-phishing-princip i Security & Compliance Center byter du bara namn på _anti-phish-regeln_.

Om du vill ändra en anti-phish-princip använder du den här syntaxen:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Använda PowerShell för att ändra anti-phish-regler

Den enda inställningen som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är parametern _Aktiverad_ som gör att du kan skapa en inaktiverad regel. Information om hur du aktiverar eller inaktiverar befintliga anti-phish-regler finns i nästa avsnitt.

Annars är inga ytterligare inställningar tillgängliga när du ändrar en anti-phish-regel i PowerShell. Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett anti-phish-regelavsnitt](#step-2-use-powershell-to-create-an-anti-phish-rule) tidigare i det här avsnittet.

Om du vill ändra en anti-phish-regel använder du den här syntaxen:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Använda PowerShell för att aktivera eller inaktivera anti-phish-regler

Om du aktiverar eller inaktiverar en anti-phish-regel i PowerShell aktiveras eller inaktiveras hela anti-phishing-principen (anti-phish-regeln och den tilldelade anti-phish-principen). Du kan inte aktivera eller inaktivera standardpolicyn mot nätfiske (den tillämpas alltid på alla mottagare).

Om du vill aktivera eller inaktivera en anti-phish-regel i PowerShell använder du den här syntaxen:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras anti-phish-regeln med namnet Marknadsavdelningen.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad syntax- och parameterinformation finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) och [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Använd PowerShell för att ange prioritet för anti-phish-regler

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Om du vill ange prioritet för en anti-phish-regel i PowerShell använder du följande syntax:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Anmärkningar**:

- Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **Ny-AntiPhishRule** i stället.

- Standardanti-phish-principen har ingen motsvarande anti-phish-regel, och den har alltid det omodifierbara prioritetsvärdet **Lägsta**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Använda PowerShell för att ta bort anti-phish-principer

När du använder PowerShell för att ta bort en anti-phish-princip tas inte motsvarande anti-phish-regel bort.

Om du vill ta bort en anti-phish-princip i PowerShell använder du den här syntaxen:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

I det här exemplet tas anti-phish-principen med namnet Marknadsavdelningen bort.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Använd PowerShell för att ta bort anti-phish-regler

När du använder PowerShell för att ta bort en anti-phish-regel tas inte motsvarande anti-phish-princip bort.

Om du vill ta bort en anti-phish-regel i PowerShell använder du den här syntaxen:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

I det här exemplet tas anti-phish-regeln med namnet Marknadsavdelningen bort.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Så här kontrollerar du att du har konfigurerat ATP:s principer för phishing:er:

- I Security & Compliance Center går **Threat management** du till \> **Policy** \> **ATP-principen**mot hothantering. Verifiera listan över principer, deras **statusvärden** och deras **prioritetsvärden.** Så här visar du mer information:

  - Välj principen i listan och visa informationen i utfällbara.
  - Klicka på **Standardprincip** och visa informationen i utfällbara.

- I Exchange Online PowerShell ersätter du \< Namn med namnet på principen eller regeln och kör följande kommando och verifiera \> inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
