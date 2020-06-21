---
title: Konfigurera principer för nätfiske i EOP
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
description: Administratörer kan lära sig hur du skapar, ändrar och tar bort de anti-nätfiskeprinciper som är tillgängliga i EOP-organisationer (Exchange Online Protection) med eller utan Exchange Online-postlådor.
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726784"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Konfigurera principer för nätfiske i EOP

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor finns det en standardpolicy mot nätfiske som innehåller ett begränsat antal anti-spoofing-funktioner som är aktiverade som standard. Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen mot nätfiske. För större granularitet kan du också skapa anpassade principer mot nätfiske som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Organisationer med Exchange Online-postlådor kan konfigurera principer mot nätfiske i Security & Compliance Center eller Exchange Online PowerShell. Fristående EOP-organisationer kan bara använda Security & Compliance Center.

Information om hur du skapar och ändrar de mer avancerade ATP-principerna för nätfiske som är tillgängliga i Office 365 Advanced Threat Protection (Office 365 ATP) finns i [Konfigurera ATP-principer för nätfiske](configure-atp-anti-phishing-policies.md).

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>Principer mot nätfiske i Security & Compliance Center vs PowerShell

De grundläggande inslagen i en anti-phishing-policy är:

- **Anti-phish-principen**: Anger vilka nätfiskeskydd som ska aktiveras eller inaktiveras och vilka åtgärder som ska tillämpas.

- **Anti-phish-regeln**: Anger prioritets- och mottagarfilter (vem principen gäller för) för en anti-phish-princip.

Skillnaden mellan dessa två element är inte uppenbar när du hanterar anti-phishing-principer i Security & Compliance Center:

- När du skapar en anti-phishing-princip i Security & Compliance Center skapar du faktiskt en anti-phish-regel och den associerade anti-phish-principen samtidigt som du använder samma namn för båda.

- När du ändrar en anti-phishing-princip i Security & Compliance Center ändrar inställningarna som är relaterade till namn, prioritet, aktiverad eller inaktiverad och mottagarfilter anti-phish-regeln. Alla andra inställningar ändrar den associerade anti-phish-principen.

- När du tar bort en anti-phishing-princip från Security & Compliance Center tas anti-phish-regeln och den associerade anti-phish-principen bort.

I Exchange Online PowerShell är skillnaden mellan anti-phish-principer och anti-phish-regler uppenbar. Du hanterar anti-phish-principer med hjälp av cmdleterna ** \* -AntiPhishPolicy** och hanterar anti-phish-regler med hjälp av cmdlets ** \* -AntiPhishRule.**

- I PowerShell skapar du principen mot phish först och sedan skapar du anti-phish-regeln som identifierar den princip som regeln gäller för.

- I PowerShell ändrar du inställningarna i anti-phish-principen och anti-phish-regeln separat.

### <a name="default-atp-anti-phishing-policy"></a>Standardprincip för ATP-phishing

Varje organisation har en inbyggd anti-phishing-princip med namnet Office365 AntiPhish Standard som har följande egenskaper:

- Principen Office365 AntiPhish Default tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-phish-regel (mottagarfilter) som är associerad med principen.

- Principen Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist). Alla anpassade principer som du skapar har alltid högre prioritet än principen Office365 AntiPhish Default.

- Principen som heter Office365 AntiPhish Default är standardprincipen (egenskapen **IsDefault** har värdet `True` ) och du kan inte ta bort standardprincipen.

Om du vill öka effektiviteten i skyddet mot nätfiske kan du skapa anpassade principer mot nätfiske med striktare inställningar som tillämpas på specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **Mot nätfiske** använder du <https://protection.office.com/antiphishing> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

  Du kan inte hantera anti-phishing-principer i fristående EOP PowerShell.

- Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:

  - Om du vill lägga till, ändra och ta bort principer för nätfiske måste du vara medlem i någon av följande rollgrupper:

    - **Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - För skrivskyddad åtkomst till anti-phishing-policyer måste du vara medlem i någon av följande rollgrupper:

    - **Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- För att kunna skapa och ändra anti-spam politik i fristående EOP, måste du göra något som kräver _hydrering_ för din hyresgäst. I Administrationscentret för Exchange (EAC) kan du till exempel gå till fliken **Behörigheter,** välja en befintlig rollgrupp, klicka på **Redigera** ![ redigera ikon och ta bort en roll ](../../media/ITPro-EAC-EditIcon.png) (som du slutligen lägger till). Om din klient aldrig har hydrerats får du en dialogruta med namnet **Uppdatera organisationsinställningar** med ett förloppsindikator som ska slutföras. Mer information om hydrering finns i cmdleten [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (som inte är tillgänglig i fristående EOP PowerShell eller i Security & Compliance Center).

- Våra rekommenderade inställningar för anti-phishing-principer finns i [EOP:s standardinställningar för anti-nätfiske](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Tillåt upp till 30 minuter för den uppdaterade principen som ska tillämpas.

- Information om var anti-nätfiskeprinciper tillämpas i filtreringspipelinen finns i [Ordning och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Använda Security & Compliance Center för att skapa policyer mot nätfiske

Om du skapar en anpassad anti-phishing-princip i Security & Compliance Center skapas anti-phish-regeln och den associerade anti-phish-principen samtidigt som du använder samma namn för båda.

När du skapar en anti-phishing-princip kan du bara ange principnamn, beskrivning och mottagarfilter som identifierar vem principen gäller för. När du har skapat principen kan du ändra principen för att ändra eller granska standardinställningarna mot nätfiske.

1. Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .

2. Klicka på **Skapa**på sidan **Anti-phishing** .

3. Guiden **Skapa en ny anti-phishing-princip** öppnas. Konfigurera följande inställningar på sidan Namn på **principen:**

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   När du är klar klickar du på **Nästa**.

4. På sidan **Tillämpad på** som visas identifierar du de interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

   Klicka på **Lägg till ett villkor**. I listrutan som visas väljer du ett villkor under **Tillämpad om:**

   - **Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
   - **Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.
   - **Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.

   När du har valt villkoret visas en motsvarande listruta med rutan **Någon av dessa.**

   - Klicka i rutan och bläddra igenom listan med värden att välja.
   - Klicka i rutan och börja skriva för att filtrera listan och välj ett värde.
   - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
   - Om du vill ta bort enskilda poster klickar du på **Ikonen Ta bort** ta bort i ![ ](../../media/scc-remove-icon.png) värdet.
   - Om du vill ta bort hela villkoret klickar du på **Ikonen Ta bort** ta bort på ![ ](../../media/scc-remove-icon.png) villkoret.

   Om du vill lägga till ytterligare ett villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **Tillämpat om**.

   Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under Förutom **om**. Inställningarna och beteendet är likadana som villkoren.

   När du är klar klickar du på **Nästa**.

5. Granska **inställningarna** på sidan Granska dina inställningar som visas. Du kan klicka på **Redigera** på varje inställning för att ändra den.

   När du är klar klickar du på **Skapa den här principen**.

6. Klicka på **OK** i bekräftelsedialogrutan som visas.

När du har skapat principen mot nätfiske med de här allmänna principinställningarna använder du instruktionerna i nästa avsnitt för att konfigurera skyddsinställningarna i principen.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Använda Security & Compliance Center för att ändra anti-phishing-principer

Använd följande procedurer för att ändra anti-phishing-principer: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.

1. Om du inte redan är där öppnar du Security & Compliance **Threat management** Center och går till \> **Policy** \> **Anti-phishing för**hothanteringspolicy .

2. Välj den anpassade anti-phishing-principen som du vill ändra. Om den redan är markerad avmarkerar du den och markerar den igen.

3. **Den Redigera \<name\> din princip** utfällbara visas. Om du klickar på **Redigera** i ett avsnitt får du tillgång till inställningarna i det avsnittet.

   - Följande steg visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).

   - När du har **klickat** på Redigera i ett avsnitt visas de tillgängliga inställningarna i ett guideformat, men du kan hoppa inom sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Ikonen Avbryt** eller **Stäng** avsluta för att återgå till sidan Redigera ![ din ](../../media/scc-remove-icon.png) **princip \<name\> ** (du behöver inte besöka den sista sidan i guiden för att spara eller lämna).

4. **Principinställning**: Klicka på **Redigera** om du vill ändra samma inställningar som var tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-anti-phishing-policies) i föregående avsnitt:

   - **Name**
   - **Beskrivning**
   - **Tillämpas på**
   - **Granska dina inställningar**

   När du är klar klickar du på **Spara** på valfri sida.

5. **Spoof**: Klicka på **Redigera** om du vill aktivera eller inaktivera falska underrättelser, inaktivera oautentiserade avsändande avsändare i Outlook på eller inaktivera och konfigurera åtgärden så att den gäller för meddelanden från blockerade förfalskade avsändare. Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).

   Observera att samma inställningar också är tillgängliga i ATP:s principer för phishing.Note that these same settings are also available in ATP anti-phishing policies.

   - **Spoofing filterinställningar:** Standardvärdet är **På**, och vi rekommenderar att du lämnar den på. Om du vill stänga av den drar du växlingsknappen till **Av**. Mer information finns [i Konfigurera falska underrättelser i EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Du behöver inte inaktivera förfalskningsskydd om MX-posten inte pekar på Microsoft 365. du aktiverar utökad filtrering för kontakter i stället. Instruktioner finns i [Förbättrad filtrering för anslutningsappar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Aktivera funktionen Oautentiserad avsändare**: Standardvärdet är **På**. Om du vill stänga av den drar du växlingsknappen till **Av**.

   - **Åtgärder**: Ange vilken åtgärd som ska vidtas för meddelanden som inte innehåller falska underrättelser:

     **Om e-post skickas av någon som inte får förfalska din domän:**

     - **Flytta meddelande till mottagarnas skräppostmappar**
     - **Karantän meddelandet**

   - **Granska dina inställningar**: I stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till den relevanta sidan.
     - Du kan växla följande inställningar **På** eller **Av** direkt på den här sidan:

       - **Aktivera skydd mot förfalskning**
       - **Aktivera funktionen Oautentiserad avsändare**

   När du är klar klickar du på **Spara** på valfri sida.

6. Tillbaka på **sidan \<Name\> Redigera din princip,** granska dina inställningar och klicka sedan på **Stäng**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Använd Security & Compliance Center för att ändra standardpolicyn mot nätfiske

Standardprincipen mot nätfiske heter Office365 AntiPhish Default och visas inte i listan över principer. Så här ändrar du standardpolicyn mot nätfiske:

1. Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .

2. Klicka på **Standardprincip**på sidan **Anti-phishing.**

3. Sidan **Redigera din princip office365 AntiPhish Standard** visas. Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip](#use-the-security--compliance-center-to-modify-anti-phishing-policies).

   - **Personifiering**
   - **Spolat**
   - **Avancerade inställningar**

   Följande inställningar är inte tillgängliga när du ändrar standardprincipen:

   - Du kan se avsnittet **Principinställning** och värden, men det finns ingen **redigera** länk, så du kan inte ändra inställningarna (principnamn, beskrivning och vem principen gäller för (den gäller för alla mottagare)).
   - Du kan inte ta bort standardprincipen.
   - Du kan inte ändra prioriteten för standardprincipen (den tillämpas alltid sist).

4. På sidan **Redigera din princip office365 AntiPhish Standard** granskar du dina inställningar och klickar sedan på **Stäng**.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aktivera eller inaktivera anpassade principer för nätfiske

1. Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .

2. Lägg märke till värdet i kolumnen **Status:**

   - Dra växlingsknappen till **Av** för att inaktivera principen.

   - Dra växlingsknappen till **På** för att aktivera principen.

Du kan inte inaktivera standardpolicyn mot nätfiske.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Ange prioritet för anpassade principer mot nätfiske

Som standard ges anti-phishing-principer en prioritet som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Två principer kan inte ha samma prioritet.

Anpassade principer mot nätfiske visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0). Standardprincipen mot nätfiske med namnet Office365 AntiPhish Default har det anpassade prioritetsvärdet **Lägsta**och du kan inte ändra det.

 **I**Security & Compliance Center kan du bara ändra prioriteten för anti-phishing-principen när du har skapat den. I PowerShell kan du åsidosätta standardprioriteten när du skapar anti-phish-regeln (vilket kan påverka prioriteten för befintliga regler).

Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i principens egenskaper (du kan inte direkt ändra **prioritetsnumret** i säkerhets- & compliance center). Det är bara meningsfullt att ändra prioriteten för en princip om du har flera principer.

1. Gå till **Threat management** \> **Policy** \> **ATP-anti-nätfiske**i Security & Compliance Center .

2. Markera den princip som du vill ändra. Om den redan är markerad avmarkerar du den och markerar den igen.

3. **Den Redigera \<name\> din princip** utfällbara visas.

   - Den anpassade anti-phishing-principen med **prioritetsvärde** **0** har bara knappen **Minska prioritet** tillgänglig.

   - Den anpassade anti-phishing-principen med det lägsta **prioritetsvärdet** (till exempel **3)** har bara knappen **Öka prioritet** tillgänglig.

   - Om du har tre eller flera anpassade anti-phishing-principer har principer mellan de högsta och lägsta prioritetsvärdena både knapparna **Öka prioritet** och **Minska prioritet** tillgängliga.

4. Klicka på **Öka prioritet** eller **Minska prioritet** om du vill ändra **prioritetsvärdet.**

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Använda Security & Compliance Center för att visa principer för nätfiske

1. I Security & Compliance Center och gå till **Policy** \> **Policy** \> **anti-phishing**för hothanteringspolicy .

2. Gör något av följande:

   - Välj en anpassad anti-phishing-princip som du vill visa. Om den redan är markerad avmarkerar du den och markerar den igen.

   - Klicka på **Standardprincip** om du vill visa standardpolicyn mot nätfiske.

3. Den **Redigera \<name\> din princip** utfällbara visas, där du kan visa inställningar och värden.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Använda Security & Compliance Center för att ta bort principer för nätfiske

1. Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center .

2. Markera den princip som du vill ta bort. Om den redan är markerad avmarkerar du den och markerar den igen.

3. Klicka på **Ta bort princip**i utfällningen redigera din **princip \<name\> ** och klicka sedan på **Ja** i varningsdialogrutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Använda Exchange Online PowerShell för att konfigurera principer mot nätfiske

Följande procedurer är inte tillgängliga i fristående EOP-organisationer.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Använda PowerShell för att skapa principer mot nätfiske

Att skapa en anti-phishing-policy i PowerShell är en tvåstegsprocess:

1. Skapa anti-phish-principen.

2. Skapa anti-phish-regeln som anger den anti-phish-princip som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny anti-phish-regel och tilldela den en befintlig, oassocierad anti-phish-princip. En anti-phish regel kan inte associeras med mer än en anti-phish politik.

- Du kan konfigurera följande inställningar för nya anti-phish-principer i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:

  - Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny anti-AntiPhishRule).**

  - Ange prioritet för principen när du skapar (_Prioritet_ _\<Number\>_ ) på cmdleten **Ny antiphishRule).**

- En ny anti-phish-princip som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en anti-phish-regel.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Steg 1: Använd PowerShell för att skapa en anti-phish-policy

Om du vill skapa en anti-phish-princip använder du den här syntaxen:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

I det här exemplet skapas anti-phish-principen Research Quarantine med följande inställningar:

- Principen är aktiverad (vi använder inte parametern _Aktiverad_ och standardvärdet är `$true` ).
- Beskrivningen är: Forskningsavdelningens policy.
- Ändrar standardåtgärden för förfalskning till karantän.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Detaljerad syntax- och parameterinformation finns i [Ny AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

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

Detaljerad syntax- och parameterinformation finns i [Ny anti-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

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

Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

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

Detaljerad syntax- och parameterinformation finns i [Hämta-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Använda PowerShell för att ändra anti-phish-principer

Andra än följande objekt är samma inställningar tillgängliga när du ändrar en anti-phish-princip i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett anti-phish-principavsnitt](#step-1-use-powershell-to-create-an-anti-phish-policy) tidigare i det här avsnittet.

- _Den MakeDefault-växel_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid **lägsta** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en anti-phish-princip i PowerShell.

- Du kan inte byta namn på en anti-phish-princip **(cmdleten Set-AntiPhishPolicy** har ingen _namnparameter)._ När du byter namn på en anti-phishing-princip i Security & Compliance Center byter du bara namn på _anti-phish-regeln_.

Om du vill ändra en anti-phish-princip använder du den här syntaxen:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Använda PowerShell för att ändra anti-phish-regler

Den enda inställning som inte är tillgänglig när du ändrar en anti-phish-regel i PowerShell är parametern _Aktiverad_ som gör att du kan skapa en inaktiverad regel. Information om hur du aktiverar eller inaktiverar befintliga anti-phish-regler finns i nästa avsnitt.

Annars är inga ytterligare inställningar tillgängliga när du ändrar en anti-phish-regel i PowerShell. Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett anti-phish-regelavsnitt](#step-2-use-powershell-to-create-an-anti-phish-rule) tidigare i det här avsnittet.

Om du vill ändra en anti-phish-regel använder du den här syntaxen:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Detaljerad syntax- och parameterinformation finns i [Ange-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

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

Detaljerad syntax- och parameterinformation finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) och [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).

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

- Standardanti-phish-principen har inte en motsvarande anti-phish-regel, och den har alltid det omodifierbara prioritetsvärdet **Lägsta**.

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

Detaljerad syntax- och parameterinformation finns i [Ta bort AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Använda PowerShell för att ta bort anti-phish-regler

När du använder PowerShell för att ta bort en anti-phish-regel tas inte motsvarande anti-phish-princip bort.

Om du vill ta bort en anti-phish-regel i PowerShell använder du den här syntaxen:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

I det här exemplet tas anti-phish-regeln med namnet Marknadsavdelningen bort.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Så här kontrollerar du att du har konfigurerat ATP:s principer för phishing:er:

- Gå till **Threat management** \> **Policy** \> **Anti-phishing**i Security & Compliance Center . Verifiera listan över principer, deras **statusvärden** och deras **prioritetsvärden.** Så här visar du mer information:

  - Välj principen i listan och visa informationen i utfällbara.
  - Klicka på **Standardprincip** och visa informationen i utfällbara.

- I Exchange Online PowerShell ersätter du \<Name\> med namnet på principen eller regeln och kör följande kommando och verifiera inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
