---
title: Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365
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
ms.openlocfilehash: 2985766cf3388382dbe1d2217843504b2bfd1a1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906594"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Skydd mot nätfiske i Microsoft Defender för [Office 365](office-365-atp.md) kan skydda organisationen från skadliga personifieringsbaserade nätfiskeattacker och andra typer av nätfiskeattacker. Mer information om skillnaderna mellan principer för skydd mot nätfiske i Exchange Online Protection (EOP) och principer för skydd mot nätfiske i Microsoft Defender för Office 365 finns i Skydd mot [nätfiske.](anti-phishing-protection.md)

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för nätfiske. För mer detaljerad information kan du också skapa anpassade principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera principer för skydd mot nätfiske i Säkerhets- & säkerhets- och efterlevnadscenter eller i Exchange Online PowerShell.

Mer information om hur du konfigurerar de mer begränsade i principer för skydd mot nätfiske som är tillgängliga i Organisationer med Exchange Online Protection (det vill säga organisationer som saknar Microsoft Defender för Office 365) finns i Konfigurera principer för skydd mot nätfiske i [EOP.](configure-anti-phishing-policies-eop.md)

De grundläggande elementen i en princip mot nätfiske är:

- **Anti-phish policy:** Anger nätfiskeskydden som aktiverar eller inaktiverar samt de alternativ som används.
- **Antifrasregeln**: Anger prioritet och mottagarfilter (som principen gäller för) för en nättfnig policy.

Skillnaden mellan dessa två element är inte uppenbart när du hanterar principer mot nätfiske i Säkerhets- och & Efterlevnadscenter:

- När du skapar en princip skapar du faktiskt en antifishregel och den tillhörande antifishprincipen samtidigt som du använder samma namn för båda.
- När du ändrar en princip ändrar inställningar för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter den antifish-regeln. Alla andra inställningar ändrar den associerade nätfn-principen.
- När du tar bort en princip tas den nättfiska regeln och den tillhörande antifiska policyn bort.

I Exchange Online PowerShell kan du hantera principen och regeln separat. Mer information finns i avsnittet Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske i Microsoft Defender för [Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) längre fram i den här artikeln.

Alla Microsoft Defender för Office 365-organisationer har en inbyggd skydd mot nätfiskeprincip med namnet Office365-antifishstandard som har följande egenskaper:

- Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon antifrasregel (mottagarfilter) kopplad till principen.
- Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist). Alla anpassade policyer som du skapar har alltid högre prioritet.
- Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.

För att öka effektiviteten i skydd mot nätfiske i Microsoft Defender för Office 365 kan du skapa anpassade principer för nätfiske med striktare inställningar som tillämpas för specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **ATP-sidan för** skydd mot nätfiske använder du <https://protection.office.com/antiphishing> .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill lägga till, ändra och ta bort principer  för skydd mot nätfiske måste du vara medlem i rollgrupperna Organisationshantering **eller Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till principer mot nätfiske måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.** <sup>\*</sup>

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Organisationshantering, skrivskyddade** i [Exchange Online,](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddsåtkomst till <sup>\*</sup> funktionen.
  - <sup>\*</sup> I Säkerhets- & efterlevnadscenter kan användare med skrivskyddsåtkomst visa inställningarna för anpassade principer för nätfiske. Skrivskyddade användare kan inte se inställningarna i standardprincipen för nätfiske.

- Vi rekommenderar inställningar för principer mot nätfiske i Microsoft Defender för Office 365 i Artikeln om skydd mot nätfiske i Defender för [Office 365-inställningar.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

- Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.

- Information om var principer för skydd mot nätfiske tillämpas i filtreringsförloppet finns i Ordning och [prioritet för e-postskydd.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använd Säkerhets- & efterlevnadscenter för att skapa principer mot nätfiske i Microsoft Defender för Office 365

Om du skapar en anpassad policy mot nätfiske i Säkerhets- och efterlevnadscenter för & skapas samtidigt den skyddande phish-regeln och den tillhörande nätfiskeprincipen med samma namn för båda.

När du skapar en princip mot nätfiske kan du bara ange principens namn, beskrivning och mottagarfilter som identifierar vem principen gäller. När du har skapat principen kan du ändra principen för att ändra eller granska standardinställningarna för skydd mot nätfiske.

1. Gå till ATP för & skydd  mot nätfiske i Säkerhets- och \>  \> **efterlevnadscenter.**

2. På sidan **Mot nätfiske** klickar du på **Skapa**.

3. Guiden **Skapa en ny princip mot nätfiske** öppnas. Konfigurera **följande inställningar på** sidan Namnge principen:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   Klicka på Nästa när du är **klar.**

4. På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

   Klicka **på Lägg till ett villkor.** I listrutan som visas väljer du ett villkor under **Används om:**

   - **Mottagaren är: Anger** en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
   - **Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.
   - **Mottagardomänen är:** Anger mottagare i en eller flera av de konfigurerade godkända domänerna i organisationen.

   När du har valt villkoret visas motsvarande listruta med rutan **Valfri av dessa.**

   - Klicka i rutan och bläddra igenom listan med värden du vill välja.
   - Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.
   - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
   - Om du vill ta bort enskilda poster klickar **du på Ta** bort ikon för ![ ](../../media/scc-remove-icon.png) värdet.
   - Om du vill ta bort hela villkoret klickar du **på Ta** bort ikon ![ för ](../../media/scc-remove-icon.png) villkoret.

   Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om**.

   Om du vill lägga till undantag klickar **du på Lägg till ett** villkor och väljer ett undantag under Utom **om**. Inställningarna och beteendet är likadana som villkoren.

   Klicka på Nästa när du är **klar.**

5. Granska **inställningarna på sidan** Granska dina inställningar som visas. Du kan klicka **på Redigera** för varje inställning för att ändra den.

   När du är klar klickar du på **Skapa den här principen.**

6. Klicka **på OK** i bekräftelsedialogrutan som visas.

När du har skapat principen mot nätfiske med de här allmänna inställningarna följer du anvisningarna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använd Säkerhets- & efterlevnadscenter för att ändra principer för skydd mot nätfiske i Microsoft Defender för Office 365

Använd följande procedurer för att ändra principer för skydd mot nätfiske: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.

1. Om du inte redan är där öppnar du Säkerhets- och  & efterlevnadscenter och går till ATP -skydd mot nätfiske i \>  \> **hothanteringspolicyn.**

2. Välj den anpassade principen för nätfiske som du vill ändra. Om den redan är markerad avmarkerar du den och markerar den igen.

3. Den **utfällna knappen Redigera \<name\>** princip visas. Om **du** klickar på Redigera i ett avsnitt får du åtkomst till inställningarna i det avsnittet.

   - Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).

   - När du  har klickat på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men du  kan  hoppa inom sidorna i valfri ordning och du kan klicka på Spara på valfri sida (eller  ![ ](../../media/scc-remove-icon.png) **\<name\>** på ikonen Avbryt eller Stäng stäng för att återgå till sidan Redigera principen (du behöver inte gå till den sista sidan i guiden för att spara eller lämna).

4. **Principinställning:** Klicka **på** Redigera om du vill ändra samma inställningar som var [tillgängliga när du skapade principen](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) i föregående avsnitt:

   - **Name**
   - **Beskrivning**
   - **Tillämpas på**
   - **Granska dina inställningar**

   När du är klar klickar du på **Spara** på valfri sida.

5. **Personifiering:** Klicka på **Redigera** om du vill ändra de skyddade avsändarna och de skyddade domänerna i principen. De här inställningarna är ett villkor för principen som identifierar förfalskningsavsändare som ska leta efter (individuellt eller per domän) i från-adressen för inkommande meddelanden. Mer information finns i Inställningar [för personifiering i principer för skydd mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Lägga till användare att skydda:** Standardvärdet är **Av**. Om du vill aktivera den drar du reglaget **till På** och klickar sedan på knappen **Lägg till** användare som visas.

     Konfigurera **följande värden i** den utfäll plats som visas för Lägg till användare:

     - **E-postadress:**

       - Klicka i rutan och bläddra igenom listan med användare du vill välja.
       - Klicka i rutan och börja skriva för att filtrera listan och välj en användare.
       - Om du vill ta bort en post klickar **du på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för användaren.

     - **Namn:** Det här värdet fylls i baserat på den e-postadress du valde, men du kan ändra det.

     När du är klar klickar du på **Spara** på valfri sida.

     Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.

     > [!NOTE]
     >
     > - I varje princip mot nätfiske kan du ange högst 60 skyddade användare (avsändar-e-postadresser). Du kan inte ange samma skyddade användare i flera principer.
     >
     > - Skydd för användarpersonifiering fungerar inte om avsändaren och mottagaren tidigare har kommunicerat via e-post. Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifieringsförsök.

   - **Lägga till domäner att skydda:** Konfigurera en eller båda av följande inställningar:

     - **Inkludera automatiskt domänerna jag äger:** Standardvärdet är **Av**. Aktivera den genom att dra reglaget till **På**.
     - **Inkludera egna domäner:** Standardvärdet är **Av**. Aktivera den genom att dra reglaget till  På och ange domännamnet (till exempel contoso.com) i rutan Lägg till domäner, tryck på RETUR och upprepa efter behov.

     > [!NOTE]
     > Du kan ha högst 50 domäner i alla principer mot nätfiske.

   - **Åtgärder:** Klicka på **Redigera**

     - **Om e-post** skickas av en imiterad användare : Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren är en av de skyddade användare som du angav i Lägg till användare **att skydda:**

       - **Använd inte någon åtgärd**
       - **Omdirigera meddelandet till andra e-postadresser**
       - **Flytta meddelandet till mappen Skräppost**
       - **Sätt meddelandet i karantän**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

     - **Om e-post** skickas med en imiterad domän: Konfigurera någon av följande åtgärder för meddelanden där den falska avsändaren finns i någon av de skyddade domäner som du har angett i Lägg till domäner **att skydda:**

       - **Använd inte någon åtgärd**
       - **Omdirigera meddelandet till andra e-postadresser**
       - **Flytta meddelandet till mappen Skräppost**
       - **Sätt meddelandet i karantän**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

   - Klicka **på Aktivera säkerhetstips för personifiering** och konfigurera någon av följande inställningar:

     - **Visa tips för imiterade användare:** Standardvärdet är **Av**. Aktivera den genom att dra reglaget till **På**.
     - **Visa tips för imiterade domäner:** Standardvärdet är **Av**. Aktivera den genom att dra reglaget till **På**.
     - **Visa tips för ovanliga tecken:** Standardvärdet är **Av**. Aktivera den genom att dra reglaget till **På**.

     Klicka på **Spara** när du är klar.

   - **Postlådeintelligens:**

     - **Aktivera postlådeintelligens?**: Standardvärdet är **På.** Om du vill inaktivera den drar du reglaget till **Av**.

     - **Aktivera postlådeintelligensbaserat personifieringsskydd?**: Den här inställningen är bara tillgänglig om **Aktivera postlådeintelligens?** är **På.**

       I **Om** e-post skickas av en imiterad användare kan du ange någon av följande åtgärder för meddelanden som inte fungerar med postlådeintelligens (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):

       - **Använd inte någon åtgärd**
       - **Omdirigera meddelandet till andra e-postadresser**
       - **Flytta meddelandet till mappen Skräppost**
       - **Sätt meddelandet i karantän**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

   - **Lägga till betrodda avsändare och** domäner : Ange undantag för principen:

     - **Betrodda avsändare:**

       - Klicka i rutan och bläddra igenom listan med användare du vill välja.
       - Klicka i rutan och börja skriva för att filtrera listan och välj en användare.
       - Om du vill ta bort en post klickar **du på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för användaren.

     - **Betrodda** domäner: Ange domännamnet (till exempel contoso.com), tryck på RETUR och upprepa om det behövs.

   - **Granska dina inställningar:** I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka **på Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.
     - Du kan aktivera eller inaktivera följande **inställningar** **direkt på** den här sidan:

       - **Skyddade användare**
       - **Skyddade domäner** \> **Inkludera domäner som jag äger**
       - **Skyddade domäner** \> **Skyddade domäner** (egna domäner)
       - **Postlådeintelligens**

   När du är klar klickar du på **Spara** på valfri sida.

6. **Förfalskning:** Klicka  på Redigera för att aktivera eller inaktivera förfalskningsinformation, aktivera eller inaktivera oauthticerad avsändaridentifiering i Outlook och konfigurera åtgärden som ska gälla för meddelanden från spärrade förfalskningsavsändare. Mer information finns i [Inställningar för förfalskning i principer mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)

   Observera att samma inställningar även är tillgängliga i principer för skydd mot nätfiske i EOP.

   - **Filterinställningar för förfalskning:** Standardvärdet är **På** och vi rekommenderar att du låter det vara på. Om du vill inaktivera den drar du reglaget till **Av**. Mer information finns i [Konfigurera förfalskningsinformation i EOP.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället. Instruktioner finns i [Utökad filtrering för kopplingar i Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **Aktivera funktionen Oauthenticated Sender:** Standardvärdet är **På**. Om du vill inaktivera den drar du reglaget till **Av**.

   - **Åtgärder**: Ange vilken åtgärd som ska vidtas på meddelanden som inte klarar förfalskningsinformation:

     **Om e-post skickas av någon som inte har tillåtelse att kapa din domän:**

     - **Flytta meddelandet till mottagarnas skräppostmappar**
     - **Sätt meddelandet i karantän**

   - **Granska dina inställningar:** I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka **på Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.
     - Du kan aktivera eller inaktivera följande **inställningar** **direkt på** den här sidan:
       - **Aktivera skydd mot förfalskning**
       - **Aktivera funktionen Oauthenticated Sender**

   När du är klar klickar du på **Spara** på valfri sida.

7. **Avancerade inställningar:** Klicka på **Redigera för** att konfigurera avancerade tröskelvärden för nätfiske. Mer information finns i Avancerade [tröskelvärden för nätfiske i principer mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Avancerade tröskelvärden för nätfiske:** Välj något av följande värden:

   - **1 – Standard** (det här är standardvärdet.)
   - **2 – Aggressivt**
   - **3 – Mer aggressiva**
   - **4 – Mest aggressiva**

   - **Granska dina inställningar:** Klicka på **Redigera för** att gå tillbaka till **sidan Avancerade tröskelvärden för nätfiske.**

   När du är klar klickar du på **Spara** på någon av sidorna.

8. Gå tillbaka till **sidan Redigera principen, \<Name\>** granska dina inställningar och klicka sedan på **Stäng**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att ändra standardprincipen för skydd mot nätfiske i Microsoft Defender för Office 365

Standardprincipen för skydd mot nätfiske i Microsoft Defender för Office 365 heter Office365-skyddstrecksstandard och visas inte i listan med principer. Gör så här om du vill ändra standardprincipen för nätfiske:

1. Gå till ATP för & skydd  mot nätfiske i Säkerhets- och \>  \> **efterlevnadscenter.**

2. På sidan **Skydd mot nätfiske** klickar du på **Standardprincip.**

3. Sidan **Redigera principen Som standard för Office365-skyddstreck** visas. Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Personifiering**
   - **Förfalskning**
   - **Avancerade inställningar**

   Följande inställningar är inte tillgängliga när du ändrar standardprincipen:

   - Du kan  se avsnittet och värdena för principinställningen, men det finns ingen redigera-länk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)). 
   - Du kan inte ta bort standardprincipen.
   - Du kan inte ändra prioriteten för standardprincipen (den används alltid sist).

4. Granska dina **inställningar på sidan Redigera principen som standard för Office365-skydd,** och klicka sedan på **Stäng.**

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Aktivera eller inaktivera anpassade principer för skydd mot nätfiske i Microsoft Defender för Office 365

1. Gå till ATP för & skydd  mot nätfiske i Säkerhets- och \>  \> **efterlevnadscenter.**

2. Observera värdet i **kolumnen** Status:

   - Inaktivera principen genom att dra **reglaget** till Av.

   - Aktivera principen genom att dra **reglaget** till På.

Du kan inte inaktivera standardprincipen för nätfiske.

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Ange prioritet för anpassade principer för nätfiske i Microsoft Defender för Office 365

Som standard prioriteras principer mot nätfiske baserat på i vilken ordning de skapades (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Anpassade principer för skydd mot nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0). Standardprincipen för skydd mot nätfiske med namnet Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägst** och du kan inte ändra det.

 **Obs!** I Säkerhets- & säkerhets- och efterlevnadscenter kan du bara ändra prioriteten för principen mot nätfiske när du har skapat den. I PowerShell kan du åsidosätta standardprioritet när du skapar antifrasregeln (vilket kan påverka prioriteringen för befintliga regler).

Om du vill ändra prioriteten för  en princip klickar du på Öka prioritet eller  Minska prioritet för egenskaperna för principen (du kan inte direkt ändra prioritetsnumret i Säkerhets- & efterlevnadscenter).  Att ändra prioritet för en princip är bara meningsfullt om du har flera principer.

1. Gå till ATP för & skydd  mot nätfiske i Säkerhets- och \>  \> **efterlevnadscenter.**

2. Markera den princip som du vill ändra. Om den redan är markerad avmarkerar du den och markerar den igen.

3. Den **utfällna knappen Redigera \<name\>** princip visas.

   - Den anpassade principen för nätfiske med **prioritetsvärdet** **0** har endast knappen **Minska** prioritet tillgänglig.

   - Den anpassade principen för nätfiske med lägsta **prioritetsvärde** (till exempel **3)** har endast knappen **Öka** prioritet tillgänglig.

   - Om du har tre eller fler anpassade principer för skydd mot nätfiske finns det både knapparna Öka prioritet och Minska prioritet mellan de högsta och lägsta prioritetsvärdena.  

4. Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra värdet **för** Prioritet.

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använd Säkerhets- & för att visa principer mot nätfiske i Microsoft Defender för Office 365

1. Gå till  \>  \> **ATP** mot nätfiske i säkerhets- och & säkerhets- och efterlevnadscenter.

2. Gör något av följande:

   - Välj en anpassad princip mot nätfiske som du vill visa. Om den redan är markerad avmarkerar du den och markerar den igen.

   - Klicka **på Standardprincip** om du vill visa standardprincipen för nätfiske.

3. Den **utfällna \<name\>** menyn Redigera princip visas, där du kan visa inställningar och värden.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använda Säkerhets- & efterlevnadscenter för att ta bort principer mot nätfiske i Microsoft Defender för Office 365

1. Gå till ATP för & skydd  mot nätfiske i Säkerhets- och \>  \> **efterlevnadscenter.**

2. Markera den princip som du vill ta bort. Om den redan är markerad avmarkerar du den och markerar den igen.

3. I den **utfällna \<name\>** menyn Redigera principen som visas klickar du på **Ta** bort princip och sedan **på Ja** i varningsdialogrutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använda Exchange Online PowerShell för att konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365

Som tidigare beskrivits består en policy mot skräppost av en anti-phish-policy och en anti-phish-regel.

I Exchange Online PowerShell syns skillnaden mellan nättfiska policyer och anti-phish-regler. Du hanterar antifish-principer med hjälp av cmdletarna **\* -AntiPhishPolicy** och du hanterar anti-phish-regler med hjälp av cmdletarna **\* -AntiPhishRule.**

- I PowerShell skapar du först den nätfiska principen och sedan skapar du den skyddande phish-regeln som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna separat i antifish-principen och antifish-regeln.
- När du tar bort en anti-phish-policy från PowerShell tas inte motsvarande anti phish-regel bort automatiskt, och vice versa.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Använda PowerShell för att skapa principer för skydd mot nätfiske

Det krävs två steg för att skapa en princip mot nätfiske i PowerShell:

1. Skapa den anfish-policy som du sedan skapar.
2. Skapa den anti phish-regel som anger den antifishpolicy som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny anti-phish-regel och tilldela en befintlig, oassocierad antifishprincip till den. An anti-phish rule can't be associated with more than one anti-phish policy.

- Du kan konfigurera följande inställningar för nya skyddsprinciper i PowerShell som inte är tillgängliga i Säkerhets- och &-efterlevnadscenter förrän du har skapat principen:

  - Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på cmdleten **New-AntiPhishRule).**
  - Ange prioritet för principen vid skapandet (_Prioritet_ _\<Number\>_ ) på **cmdleten New-AntiPhishRule).**

- En ny antifishpolicy som du skapar i PowerShell visas inte i säkerhets- och efterlevnadscentret för & förrän du tilldelar principen en antifishregel.

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

- Du kan inte byta namn på en nätt **phish-policy (cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._ När du byter namn på en policy mot nätfiske i Säkerhets- och & Säkerhets- och efterlevnadscenter byter du bara namn på _nätfiskeregeln._

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

Verifiera att du har konfigurerat principer för skydd mot nätfiske i Microsoft Defender för Office 365 genom att göra något av följande:

- Gå till ATP för & skydd  mot nätfiske i Säkerhets- och \>  \> **efterlevnadscenter.** Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.** Om du vill visa mer information gör du något av följande:

  - Välj principen i listan och visa informationen i den utfällade listrutan.
  - Klicka **på Standardprincip** och visa informationen i den utfällade menyn.

- Ersätt med namnet på principen eller regeln i Exchange Online PowerShell och kör \<Name\> följande kommando och verifiera inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```