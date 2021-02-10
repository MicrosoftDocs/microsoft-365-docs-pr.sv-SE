---
title: Konfigurera principer för skydd mot nätfiske i EOP
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
description: Administratörer kan lära sig att skapa, ändra och ta bort de skydd mot nätfiskeprinciper som är tillgängliga i Organisationer med Eller utan Exchange Online-postlådor i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 052e19d811f56fe633ff0fbde79f51860a04a669
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165853"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Konfigurera principer för skydd mot nätfiske i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor finns det en standardprincip mot nätfiske som innehåller ett begränsat antal skydd mot förfalskning som är aktiverade som standard. Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för skydd mot nätfiske. För att få bättre detaljnivå kan du också skapa anpassade principer för nätfiske som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Organisationer med Exchange Online-postlådor kan konfigurera principer för skydd mot nätfiske i Säkerhets- & Efterlevnadscenter eller i Exchange Online PowerShell. Fristående EOP-organisationer kan endast använda Säkerhets- & Efterlevnadscenter.

Information om hur du skapar och ändrar de mer avancerade principerna för nätfiske i Microsoft Defender för Office 365 som är tillgängliga i Defender för Office 365 finns i Konfigurera principer för nätfiske i [Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)

De grundläggande elementen i en princip mot nätfiske är:

- **Nätfiskeprincipen:** Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras samt de åtgärder som används.
- **Den phish-regeln:** Anger prioritet och mottagarfilter (som principen gäller för) för en nätt phish-princip.

Skillnaden mellan dessa två element är inte uppenbara när du hanterar principer mot nätfiske i Säkerhets- och & Efterlevnadscenter:

- När du skapar en nätfiskeprincip skapar du i själva verket en nätfiskeskyddsregel och den tillhörande nätfiskeprincipen samtidigt som du använder samma namn för båda.
- När du ändrar en princip mot nätfiske ändrar inställningarna för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter ändrar nätfiskeregeln. Alla andra inställningar ändrar den tillhörande anti-phish-principen.
- När du tar bort en nätfiskeprincip tas nätfiskeregeln och den tillhörande nätfiskeprincipen bort.

I Exchange Online PowerShell hanterar du principen och regeln separat. Mer information finns i avsnittet Använda [Exchange Online PowerShell för att konfigurera principer mot](#use-exchange-online-powershell-to-configure-anti-phishing-policies) nätfiske senare i den här artikeln.

Alla organisationer har en inbyggd policy för skydd mot nätfiske med namnet Office365 AntiPhish Default som har följande egenskaper:

- Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon skyddande phish-regel (mottagarfilter) kopplad till principen.
- Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist). Alla anpassade policyer som du skapar har alltid högre prioritet.
- Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.

För att öka effektiviteten i skyddet mot nätfiske kan du skapa anpassade principer för nätfiske med striktare inställningar som tillämpas för specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt **till sidan mot nätfiske** använder du <https://protection.office.com/antiphishing> .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

  Du kan inte hantera principer för nätfiske i fristående EOP PowerShell.

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i rollgrupperna Organisationshantering **eller** **Säkerhetsadministratör.**
  - För skrivskyddade åtkomst till principer för nätfiske måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.** <sup>\*</sup>

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Rollgruppen **Skrivskyddade organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddsåtkomst till <sup>\*</sup> funktionen.
  - <sup>\*</sup> I Säkerhets- & efterlevnadscenter kan användare med skrivskyddsåtkomst visa inställningarna för anpassade principer för skydd mot nätfiske. Skrivskyddade användare kan inte se inställningarna i standardprincipen för nätfiske.

- Om du vill skapa och ändra principer för nätfiske i fristående EOP måste du göra något som _kräver av_ klientorganisationen. I till exempel administrationscentret för Exchange (EAC)  kan du gå till fliken  Behörigheter, välja en befintlig rollgrupp, klicka på redigeringsikonen och ta bort en roll (som du i slutänden lägger till ![ ](../../media/ITPro-EAC-EditIcon.png) igen). Om klientorganisationen aldrig har blivit bortskriden visas en dialogruta med namnet Uppdatera organisationsinställningar **med** en förloppsstapel som ska slutföras. Mer information om att använda finns i cmdleten [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (som inte är tillgänglig i fristående EOP PowerShell eller i Säkerhets- och & Compliance Center).

- Vi rekommenderar inställningar för principer för skydd mot nätfiske i [EOP:s standardinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)för skydd mot nätfiske.

- Det kan ta upp till 30 minuter innan den uppdaterade principen tillämpas.

- Information om var principer för skydd mot nätfiske tillämpas i filtreringsförloppet finns i Ordningen och [prioriteten för e-postskydd.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Använd Säkerhets- & center för att skapa principer för skydd mot nätfiske

Om du skapar en anpassad policy för nätfiske i Säkerhets- & Efterlevnadscenter skapas samtidigt den skyddande phish-regeln och den tillhörande nätfiskeprincipen med samma namn.

När du skapar en princip mot nätfiske kan du bara ange namn, beskrivning och mottagarfilter som identifierar vem principen gäller. När du har skapat principen kan du ändra den om du vill ändra eller granska standardinställningarna för skydd mot nätfiske.

1. Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**

2. Klicka på **Skapa på** sidan Mot **nätfiske.**

3. Guiden **Skapa en ny princip mot nätfiske** öppnas. Konfigurera **följande inställningar på** sidan Namnge principen:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   Klicka på Nästa när du är **klar.**

4. På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

   Klicka **på Lägg till ett villkor.** I listrutan som visas väljer du ett villkor under **Används om:**

   - **Mottagaren är: Anger** en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
   - **Mottagaren är medlem i:** Anger en eller flera grupper i organisationen.
   - **Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.

   När du har valt villkoret visas en motsvarande listruta med **rutan Valfri av dessa.**

   - Klicka i rutan och bläddra igenom listan med värden för att välja.
   - Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.
   - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
   - Om du vill ta bort enskilda poster klickar **du på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för värdet.
   - Om du vill ta bort hela villkoret klickar **du på ikonen** Ta bort i ![ ](../../media/scc-remove-icon.png) villkoret.

   Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om.**

   Om du vill lägga till undantag **klickar du på Lägg till ett** villkor och väljer ett undantag under Utom **om.** Inställningarna och beteendet är likadana som villkoren.

   Klicka på Nästa när du är **klar.**

5. Granska **inställningarna på sidan** Granska dina inställningar som visas. Du kan klicka **på Redigera** för varje inställning för att ändra den.

   Klicka på Skapa den här principen när **du är klar.**

6. Klicka **på OK** i bekräftelsedialogrutan som visas.

När du har skapat principen mot nätfiske med de här allmänna principinställningarna följer du anvisningarna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Använda Säkerhets- & Center för att ändra principer för skydd mot nätfiske

Använd följande procedurer för att ändra principer för skydd mot nätfiske: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.

1. Om du inte redan är där öppnar du Säkerhets- & Efterlevnadscenter och går **till** Policy för skydd \>  \> **mot nätfiske.**

2. Välj den anpassade principen för nätfiske som du vill ändra. Om det redan är markerat avmarkerar du det och markerar det igen.

3. Den **utfällna knappen Redigera \<name\>** principen visas. Om **du** klickar på Redigera i ett avsnitt får du åtkomst till inställningarna i det avsnittet.

   - Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).

   - När du klickar på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men  du kan hoppa  mellan  sidorna i valfri ordning och du kan klicka på Spara på valfri sida (eller  ![ ](../../media/scc-remove-icon.png) **\<name\>** ikonen Avbryt eller Stäng om du vill gå tillbaka till sidan Redigera principen (du behöver inte gå till den sista sidan i guiden för att spara eller lämna).

4. **Principinställning:** Klicka **på** Redigera om du vill ändra samma inställningar som var [tillgängliga när du](#use-the-security--compliance-center-to-create-anti-phishing-policies) skapade principen i föregående avsnitt:

   - **Name**
   - **Beskrivning**
   - **Används på**
   - **Granska dina inställningar**

   Klicka på Spara på valfri sida **när** du är klar.

5. **Spoof:**  Klicka på Redigera för att aktivera eller inaktivera förfalskningsinformation, aktivera eller inaktivera oauthiskt identifiering av avsändare i Outlook och konfigurera åtgärden för meddelanden från blockerade förfalskningsavsändare. Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)

   Observera att samma inställningar även är tillgängliga i principer för skydd mot nätfiske i Defender för Office 365.

   - **Filterinställningar för förfalskning:** Standardvärdet är **På** och vi rekommenderar att du låter det vara på. Om du vill inaktivera den drar du reglaget till **Av.** Mer information finns i [Konfigurera förfalskningsinformation i EOP.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > Du behöver inte inaktivera skydd mot förfalskning om MX-posten inte pekar på Microsoft 365. aktiverar du Utökad filtrering för kopplingar i stället. Instruktioner finns i Utökad [filtrering för kopplingar i Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **Aktivera funktionen Oauthenticerad avsändare:** Standardvärdet är **På.** Om du vill inaktivera den drar du reglaget till **Av.**

   - **Åtgärder:** Ange vilken åtgärd som ska vidtas för meddelanden som inte klarar förfalskningsinformation:

     **Om e-post skickas av någon som inte har tillåtelse att kapa din domän:**

     - **Flytta meddelandet till mottagarnas skräppostmappar**
     - **Sätt meddelandet i karantän**

   - **Granska dina inställningar:** i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka **på Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.
     - Du kan aktivera eller inaktivera följande **inställningar** **direkt** på den här sidan:

       - **Aktivera skydd mot förfalskning**
       - **Aktivera funktionen Oauthenticerad avsändare**

   Klicka på Spara på valfri sida **när** du är klar.

6. Tillbaka på sidan **Redigera \<Name\> principen** granskar du inställningarna och klickar sedan på **Stäng.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Använd Säkerhets- & Center för efterlevnad för att ändra standardprincipen för skydd mot nätfiske

Standardprincipen för skydd mot nätfiske heter Office365 AntiPhish Default och visas inte i listan med principer. Gör så här om du vill ändra standardprincipen för skydd mot nätfiske:

1. Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**

2. Klicka på **Standardprincip** på sidan **Skydd mot nätfiske.**

3. Sidan **Redigera standardprincip för Office365-skydd visas.** Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **Personifiering**
   - **Förfalskning**
   - **Avancerade inställningar**

   Följande inställningar är inte tillgängliga när du ändrar standardprincipen:

   - Du kan  se avsnittet och värdena för principinställningen, men det finns ingen redigeringslänk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)). 
   - Du kan inte ta bort standardprincipen.
   - Du kan inte ändra prioriteten för standardprincipen (den används alltid sist).

4. Granska inställningarna på sidan Redigera standardinställningen för principen i **Office365** och klicka sedan på **Stäng.**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aktivera eller inaktivera anpassade principer för nätfiske

1. Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**

2. Observera värdet i **kolumnen** Status:

   - Inaktivera principen genom att dra **reglaget** till Av.

   - Aktivera principen genom att **dra reglaget** till På.

Du kan inte inaktivera standardprincipen för skydd mot nätfiske.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Ange prioritet för anpassade principer för nätfiske

Som standard prioriteras principer mot nätfiske baserat på i vilken ordning de har skapats (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Anpassade principer för skydd mot nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0). Standardprincipen för skydd mot nätfiske med namnet Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** och du kan inte ändra det.

 **Obs!** I Säkerhets- & Efterlevnadscenter kan du bara ändra prioriteten för principen mot nätfiske efter att du har skapat den. I PowerShell kan du åsidosätta standardprioritet när du skapar nätt phish-regeln (vilket kan påverka prioriteten för befintliga regler).

Om du vill ändra prioritet för en  princip klickar du på Öka prioritet eller Minska  prioriteten för principens egenskaper (du kan inte direkt ändra prioritetsnumret i Säkerhets- & Efterlevnadscenter).  Att ändra prioritet för en princip är bara meningsfullt om du har flera principer.

1. Gå till ATP för skydd mot  nätfiske i Säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**

2. Markera den princip som du vill ändra. Om det redan är markerat avmarkerar du det och markerar det igen.

3. Den **utfällna knappen Redigera \<name\>** principen visas.

   - Den anpassade principen för nätfiske med **prioritetsvärdet** **0** har endast **knappen Minska** prioritet tillgänglig.

   - Den anpassade principen för nätfiske med lägsta **prioritetsvärde** (till exempel **3)** har endast knappen Öka **prioritet** tillgänglig.

   - Om du har tre eller fler anpassade principer för skydd mot nätfiske finns det både knapparna Öka prioritet och Minska prioritet mellan de högsta och lägsta prioritetsvärdena.  

4. Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra **prioritetsvärdet.**

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Använd Säkerhets- & Center för att visa principer för skydd mot nätfiske

1. Gå till policyn för skydd mot  nätfiske i säkerhets- och & Säkerhets- och \>  \> **efterlevnadscenter.**

2. Gör något av följande:

   - Välj en anpassad princip för nätfiske som du vill visa. Om det redan är markerat avmarkerar du det och markerar det igen.

   - Klicka **på Standardprincip** om du vill visa standardprincipen för skydd mot nätfiske.

3. Den **utfällga \<name\>** menyn Redigera princip visas, där du kan visa inställningar och värden.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Använda Säkerhets- & Center för att ta bort principer för skydd mot nätfiske

1. Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.**

2. Markera den princip som du vill ta bort. Om det redan är markerat avmarkerar du det och markerar det igen.

3. I den **utfällingsrutan \<name\>** Redigera principen som visas klickar du på Ta bort princip och sedan **på Ja** i varningsdialogrutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Använda Exchange Online PowerShell för att konfigurera principer för skydd mot nätfiske

Som tidigare beskrivits består en nätfiskeprincip av en nätfiskeprincip och en nätfiskeregel.

I Exchange Online PowerShell visar sig skillnaden mellan nättringsprinciper och nätt phish-regler. Du hanterar phish-principer med hjälp av cmdletarna **\* -AntiPhishPolicy** och du hanterar nätfingregler med hjälp av **\* cmdlets -AntiPhishRule.**

- I PowerShell skapar du först en nätt phish-princip och sedan skapar du den skyddande phish-regel som identifierar den princip som regeln gäller för.
- I PowerShell kan du ändra inställningarna separat i nätt phish-principen och anti-phish-regeln.
- När du tar bort en nätt phish-princip från PowerShell tas inte motsvarande phish-regel bort automatiskt och vice versa.

> [!NOTE]
> Följande PowerShell-procedurer är inte tillgängliga i fristående EOP-organisationer som använder Exchange Online Protection PowerShell.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Använda PowerShell för att skapa principer för skydd mot nätfiske

Att skapa en princip mot nätfiske i PowerShell är en process i två steg:

1. Skapa en anti-phish-policy.
2. Skapa den phish-regel som anger den anti-phish-policy som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny, phish-regel och tilldela den en befintlig, oassocierad nätt phish-princip. En nätt phish-regel kan inte associeras med mer än en anti-phish-policy.

- Du kan konfigurera följande inställningar för nya skyddsprinciper i PowerShell som inte är tillgängliga i Säkerhets- & och efterlevnadscenter förrän du har skapat principen:

  - Skapa den nya principen som inaktiverad _(aktiverad_ för `$false` cmdleten **New-AntiPhishRule).**
  - Ange prioriteten för principen när den skapas _(Priority)_ _\<Number\>_ på **cmdleten New-AntiPhishRule).**

- En ny, phish-princip som du skapar i PowerShell visas inte i Säkerhets- & och efterlevnadscenter förrän du tilldelar principen till en nätt phish-regel.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Steg 1: Använda PowerShell för att skapa en anti-phish-princip

Om du vill skapa en anti-phish-princip använder du följande syntax:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

I det här exemplet skapas en antifishprincip som heter Research Quarantine med följande inställningar:

- Beskrivningen är: Forskningavdelningens policy.
- Ändrar standardåtgärden för förfalskning till karantän.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Detaljerad information om syntax och parametrar finns [i New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Steg 2: Använda PowerShell för att skapa en antifishregel

Om du vill skapa en antifishregel använder du följande syntax:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

I det här exemplet skapas en antifishregel som heter Research Department med följande villkor:

- Regeln är kopplad till den phish-policy som heter Research Quarantine.
- Regeln gäller för medlemmar i gruppen Research Department.
- Eftersom vi inte använder _parametern Priority_ används standardprioritet.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Detaljerad information om syntax och parametrar finns [i New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)

### <a name="use-powershell-to-view-anti-phish-policies"></a>Använda PowerShell för att visa nätträcksprinciper

Använd följande syntax för att visa befintliga principer för nätt phish:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattning av alla principer för nätt phish tillsammans med de angivna egenskaperna.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

I det här exemplet returneras alla egendomsvärden för den nättfiska policyn som heter Chefer.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Detaljerad information om syntax och parametrar finns [i Hämta-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)

### <a name="use-powershell-to-view-anti-phish-rules"></a>Använda PowerShell för att visa nätträcksregler

Om du vill se befintliga skyddande regler använder du följande syntax:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattning av alla skyddande regler tillsammans med de angivna egenskaperna.

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

I det här exemplet returneras alla egenskapsvärden för den phish-regeln Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns [i Get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Använda PowerShell för att ändra nätthetsprinciper

Förutom följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar en princip enligt beskrivningen i steg 1: Använda PowerShell för att skapa en nätt [phish-princip](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i den här artikeln.

- Växeln _MakeDefault_ som omvandlar den angivna principen till  standardprincipen (gäller för alla, alltid lägsta prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en nätt phish-princip i PowerShell.

- Du kan inte byta namn på en nätt **phish-princip (cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._ När du byter namn på en policy mot nätfiske i Säkerhets- & Efterlevnadscenter byter du bara namn på _nätfiskeregeln._

Om du vill ändra en anti-phish-princip använder du följande syntax:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns [i Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Använda PowerShell för att ändra nätthetsregler

Den enda inställning som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktiverad regel. Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga skyddande regler.

Annars är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i steg [2:](#step-2-use-powershell-to-create-an-anti-phish-rule) Använd PowerShell för att skapa ett avsnitt som inte är phish längre fram i den här artikeln.

Om du vill ändra en anti-phish-regel använder du följande syntax:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns [i Set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Använda PowerShell för att aktivera eller inaktivera phish-regler

Om du aktiverar eller inaktiverar en nätfiskeregel i PowerShell aktiveras eller inaktiveras hela nätfiskeprincipen (nätfiskeregeln och den tilldelade nätfiskeprincipen). Du kan inte aktivera eller inaktivera standardprincipen för nätfiske (den används alltid för alla mottagare).

Om du vill aktivera eller inaktivera en nätträcksregel i PowerShell använder du följande syntax:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras den phish-regeln marknadsföringsavdelningen.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) [och Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Använd PowerShell för att ange prioriteten för nätträcksregler

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Använd följande syntax för att ange prioriteten för en anti-phish-regel i PowerShell:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Anmärkningar**:

- Om du vill ange prioriteten för en  ny regel när du skapar den använder du prioritetsparametern i cmdleten **New-AntiPhishRule** i stället.

- Standardprincipen för nätt phish har inte en motsvarande antifishregel och har alltid det omoderbara prioritetsvärdet **Lägsta.**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Använda PowerShell för att ta bort nätt phish-principer

När du använder PowerShell för att ta bort en nätt phish-princip tas inte motsvarande phish-regel bort.

Om du vill ta bort en anti-phish-princip i PowerShell använder du följande syntax:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

I det här exemplet tas den antifishpolicy som heter Marknadsföringsavdelningen bort.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Använda PowerShell för att ta bort nätträcksregler

När du använder PowerShell för att ta bort en nätt phish-regel tas inte motsvarande nätt phish-princip bort.

Om du vill ta bort en anti-phish-regel i PowerShell använder du följande syntax:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

I det här exemplet tas den phish-regeln med namnet Marknadsföringsavdelningen bort.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns [i Remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har konfigurerat principer för skydd mot nätfiske i Microsoft Defender för Office 365 genom att göra något av följande:

- Gå till policyn för skydd mot nätfiske i säkerhets- **och** & Säkerhets- och \>  \> **efterlevnadscenter.** Kontrollera listan över principer, deras **statusvärden** och deras **prioritetsvärden.** Om du vill visa mer information gör du något av följande:

  - Välj principen i listan och visa informationen i den utfällade listrutan.
  - Klicka **på Standardprincip** och visa informationen i den utfällna menyn.

- I Exchange Online PowerShell ersätter du med namnet på principen \<Name\> eller regeln, kör följande kommando och kontrollerar inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
