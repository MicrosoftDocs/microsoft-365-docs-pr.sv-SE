---
title: Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du skapar, ändrar och tar bort de avancerade AntiPhishing-principer som är tillgängliga i organisationer med Microsoft Defender för Office 365.
ms.openlocfilehash: ae8c87a0bfb7f975328d8283f0b62aa12c1d5e2b
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572411"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Anti-nätfiske-principer i [Microsoft Defender för Office 365](office-365-atp.md) skyddar din organisation från illasinnade nätfiske-attacker och andra typer av nät fiske attacker. Mer information om skillnaderna mellan anti-nätfiske-principer i Exchange Online Protection (EOP) och anti-nätfiske-principer i Microsoft Defender för Office 365 finns i [skydd mot nätfiske](anti-phishing-protection.md).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standard policyn för skydd mot nätfiske. Om du vill ha större precision kan du även skapa anpassade AntiPhishing-principer som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera anti-nätfiske-principer i säkerhets & efterlevnads Center eller i Exchange Online PowerShell.

Information om hur du konfigurerar de begränsade begränsningarna för nätfiske-principer som är tillgängliga i Exchange Online Protection-organisationer (det vill säga organisationer utan Microsoft Defender för Office 365) finns i [Konfigurera Antinätfiske-principer i EOP](configure-anti-phishing-policies-eop.md).

De grundläggande delarna i en Antivirus policy är:

- **Policyn för Phish**: anger skydds alternativen för nätfiske för att aktivera eller inaktivera och åtgärderna för att tillämpa alternativ.
- **Regeln för Phish**: anger de prioritets-och mottagar filter (som principen gäller för) för en policy mot anti-Phish.

Skillnaden mellan dessa två element är inte uppenbar när du hanterar skydd mot nätfiske i säkerhets & Compliance Center:

- När du skapar en princip skapar du verkligen en Phish regel och tillhör ande policy för anti-Phish med samma namn för båda.
- När du ändrar en princip kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra Phish regel. Alla andra inställningar ändra den associerade policyn för Phish.
- När du tar bort en princip tas Phish-regeln och den associerade anti-Phish-principen bort.

I Exchange Online PowerShell hanterar du policyn och regeln separat. Mer information finns i [använda Exchange Online PowerShell för att konfigurera skydd mot nätfiske-principer i avsnittet Microsoft Defender för Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) längre ned i det här avsnittet.

Alla Microsoft Defender för Office 365-organisationer har en inbyggd policy för anti-nätfiske som heter Office365 AntiPhish standard och har följande egenskaper:

- Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon anti-Phish-regel (mottagar filter) som är kopplade till principen.
- Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist). Alla anpassade policyer som du skapar har alltid högre prioritet.
- Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.

För att öka effektiviteten för skydd mot nätfiske i Microsoft Defender för Office 365 kan du skapa anpassade skydds principer med striktare inställningar som tillämpas på specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd om du vill gå direkt till sidan **ATP-nätfiske** <https://protection.office.com/antiphishing> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste tilldelas behörigheter i säkerhets & Compliance Center innan du kan göra det i den här artikeln:
  - För att lägga till, ändra och ta bort skydd mot nätfiske måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .
  - Om du vill ha skrivskyddad åtkomst till principer mot nätfiske måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** <sup>\*</sup> .

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Om du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Roll gruppen **organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen <sup>\*</sup> .
  - <sup>\*</sup> I säkerhets & Compliance Center är skrivskyddad åtkomst tillåta användare att Visa inställningar för anpassade skydds principer. Skrivskyddade användare kan inte se inställningarna i standard policyn för skydd mot nätfiske.

- För våra rekommenderade inställningar för skydd mot nätfiske i Microsoft Defender för Office 365, se [AntiPhishing-principer i inställningar för Defender för Office 365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

- Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.

- Information om var anti-nätfiske-principer tillämpas i filtrerings pipeline finns i [order och prioritetsordning för e-postskydd](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använda säkerhets & Compliance Center för att skapa skydd mot nätfiske-principer i Microsoft Defender för Office 365

Om du skapar en anpassad skydds princip i säkerhets & Compliance Center skapar regeln mot Phish och tillhör ande policy mot Phish med samma namn för båda.

När du skapar en AntiPhishing-princip kan du bara ange princip namnet, beskrivningen och det mottagar filter som identifierar vem principen gäller för. När du har skapat den här principen kan du ändra principen för att ändra eller granska standardinställningarna för nät fiske inställningar.

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.

2. Klicka på **skapa** på sidan **mot nätfiske** .

3. Guiden **skapa en ny policy för skydd mot nätfiske** öppnas. På sidan **namnge din policy** konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   När du är klar klickar du på **Nästa**.

4. **På sidan som** visas anger du vilka interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

   Klicka på **Lägg till ett villkor**. I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om**:

   - **Mottagaren är**: anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.
   - **Mottagaren är medlem i**: anger en eller flera grupper i din organisation.
   - **Mottagar domänen är**: anger mottagare i en eller flera av de konfigurerade godkända domänerna i organisationen.

   När du har valt villkoret visas en motsvarande listruta med en **av dessa** rutor.

   - Klicka i rutan och bläddra igenom listan med värden att välja.
   - Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.
   - Om du vill lägga till fler värden klickar du i ett tomt område i rutan.
   - Om du vill ta bort enskilda poster klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.
   - Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .

   Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **används om**.

   Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under **utom om**. Inställningarna och beteendet är likadana som villkoren.

   När du är klar klickar du på **Nästa**.

5. Granska inställningarna på sidan **Granska inställningar** som visas. Du kan klicka på **Redigera** på varje inställning för att ändra den.

   När du är klar klickar du på **skapa den här principen**.

6. Klicka på **OK** i bekräftelse dialog rutan som visas.

När du har skapat AntiPhishing-principen med dessa allmänna inställningar följer du anvisningarna i nästa avsnitt för att konfigurera skydds inställningarna i principen.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använda säkerhets & Compliance Center för att ändra anti-nätfiske-principer i Microsoft Defender för Office 365

Använd följande procedurer för att ändra anti-nätfiske-principer: en ny princip som du har skapat eller befintliga principer som du redan har anpassat.

1. Om du inte redan har gjort det öppnar du säkerhets & efterlevnad och går till **hot Management** \> **policy** \> **ATP-nätfiske**.

2. Välj den anpassade Antivirus princip som du vill ändra. Om det redan är markerat avmarkerar du det och väljer det igen.

3. **Redigera den utfällbara \<name\> principen** visas. Om du klickar på **Redigera** i ett avsnitt får du till gång till inställningarna i det avsnittet.

   - Följande anvisningar visas i den ordning som avsnitten visas, men de är inte sekventiella (du kan markera och ändra avsnitten i valfri ordning).

   - När du har klickat på **Redigera** i ett avsnitt visas de tillgängliga inställningarna i ett guide format, men du kan hoppa mellan sidorna i valfri ordning och du kan klicka på **Spara** på valfri sida (eller **Avbryt** eller **Stäng** Stäng-ikonen om du vill ![ ](../../media/scc-remove-icon.png) gå tillbaka till sidan **Redigera din policy \<name\>** ).

4. **Princip inställning**: Klicka på **Redigera** om du vill ändra samma inställningar som fanns tillgängliga när du [skapade principen](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) i föregående avsnitt:

   - **Name**
   - **Beskrivning**
   - **Tillämpas på**
   - **Granska dina inställningar**

   När du är klar klickar du på **Spara** på valfri sida.

5. **Personifiering**: Klicka på **Redigera** för att ändra de skyddade avsändarna och de skyddade domänerna i principen. Dessa inställningar är ett villkor för den princip som identifierar falska avsändare att leta efter (individuellt eller efter domän) i från-adressen för inkommande meddelanden. Mer information finns i [Inställningar för personifiering i principer för nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Lägg till användare att skydda**: standardvärdet är **inaktiverat**. Aktivera **den genom att dra den till den** och sedan klicka på knappen **Lägg till användare** som visas.

     I **Lägg till** utfällda användare som visas konfigurerar du följande värden:

     - **E-post adress**:

       - Klicka i rutan och bläddra igenom listan med användare som ska markeras.
       - Klicka i rutan och börja skriva för att filtrera listan och välja en användare.
       - Om du vill ta bort en post klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .

     - **Namn**: det här värdet fylls i baserat på e-postadressen du valde, men du kan ändra det.

     När du är klar klickar du på **Spara** på valfri sida.

     Om du vill redigera en befintlig post markerar du den skyddade användaren i listan.

     > [!NOTE]
     >
     > - I varje skydds princip kan du ange högst 60 skyddade användare (avsändarens e-postadress). Du kan inte ange samma skyddade användare i flera principer.
     >
     > - Användarautentisering fungerar inte om avsändaren och mottagaren tidigare kommunicerat via e-post. Om avsändaren och mottagaren aldrig har kommunicerat via e-post identifieras meddelandet som ett personifierings försök.

   - **Lägg till domäner att skydda**: Konfigurera en eller båda av följande inställningar:

     - **Inkludera automatiskt de domäner jag äger**: standardvärdet är **inaktiverat**. Aktivera den genom att dra den till **på**.
     - **Inkludera anpassade domäner**: standardvärdet är **inaktiverat**. Om du vill aktivera funktionen drar du växlings knappen till **på på** och anger sedan domän namnet (till exempel contoso.com) i rutan **Lägg till domäner** , trycker på RETUR och upprepar efter behov.

     > [!NOTE]
     > Du kan ha högst 50 domäner i alla nät fiske principer.

   - **Åtgärder**: Klicka på **Redigera**

     - **Om e-post skickas av en personifierad användare**: Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren är en av de skyddade användare som du har angett i **Lägg till användare att skydda**:

       - **Tillämpa inte någon åtgärd**
       - **Omdirigera meddelanden till andra e-postadresser**
       - **Flytta meddelandet till mappen skräp post**
       - **Sätt i karantän meddelandet**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

     - **Om e-post skickas av en domänkontrollant**: Konfigurera en av följande åtgärder för meddelanden där den falska avsändaren finns i en av de skyddade domänerna som du har angett i **Lägg till domäner för att skydda**:

       - **Tillämpa inte någon åtgärd**
       - **Omdirigera meddelanden till andra e-postadresser**
       - **Flytta meddelandet till mappen skräp post**
       - **Sätt i karantän meddelandet**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

   - Klicka på **Aktivera säkerhets tips för personifiering** och konfigurera något av följande inställningar:

     - **Visa tips för personifierade användare**: standardvärdet är **inaktiverat**. Aktivera den genom att dra den till **på**.
     - **Visa tips för personifierade domäner**: standardvärdet är **inaktiverat**. Aktivera den genom att dra den till **på**.
     - **Visa tips för ovanliga tecken**: standardvärdet är **inaktiverat**. Aktivera den genom att dra den till **på**.

     Klicka på **Spara** när du är klar.

   - **Post låda**:

     - **Aktivera post lådans intelligens?**: standardvärdet är **på**. Inaktivera växlings knappen för att **stänga av den.**

     - **Aktivera post låde baserat personifieringstoken?**: den här inställningen är endast tillgänglig om **Aktivera post låda-intelligens?** är **på**.

       I **om e-post skickas av en personifierad användare** kan du ange någon av följande åtgärder som ska vidtas för meddelanden som inte har post lådans intelligens (samma åtgärder som är tillgängliga för skyddade användare och skyddade domäner):

       - **Tillämpa inte någon åtgärd**
       - **Omdirigera meddelanden till andra e-postadresser**
       - **Flytta meddelandet till mappen skräp post**
       - **Sätt i karantän meddelandet**
       - **Leverera meddelandet och lägga till andra adresser på raden Hemlig kopia**
       - **Ta bort meddelandet innan det levereras**

   - **Lägga till betrodda avsändare och domäner**: ange undantag för principen:

     - **Betrodda avsändare**:

       - Klicka i rutan och bläddra igenom listan med användare som ska markeras.
       - Klicka i rutan och börja skriva för att filtrera listan och välja en användare.
       - Om du vill ta bort en post klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .

     - **Betrodda domäner**: ange domän namnet (till exempel contoso.com), tryck på RETUR och upprepa vid behov.

   - **Granska dina inställningar**: i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.
     - Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:

       - **Skyddade användare**
       - **Skyddade domäner** \> **Lägga till domäner som jag äger**
       - **Skyddade domäner** \> **Skyddade domäner** (anpassade domäner)
       - **Post lådans intelligens**

   När du är klar klickar du på **Spara** på valfri sida.

6. **Falska** användare: Klicka på **Redigera** för att aktivera eller inaktivera förfalsknings intelligens, aktivera och inaktivera overifierad avsändare i Outlook och konfigurera åtgärden så att den gäller för meddelanden från blockerade avsändare. Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).

   Observera att dessa inställningar också är tillgängliga i principer för nätfiske i EOP.

   - **Inställningar för förfalsknings filter**: standardvärdet är **på** och vi rekommenderar att du lämnar det. Inaktivera växlings knappen för att **stänga av den.** Mer information finns i [Konfigurera förfalsknings information i EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Du behöver inte inaktivera skydd mot förfalskning om din MX-post inte pekar på Microsoft 365; du aktiverar bättre filtrering för kopplingar i stället. Anvisningar finns i [utökad filtrering för kopplingar i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Aktivera overifierad avsändare**: standardvärdet är **på**. Inaktivera växlings knappen för att **stänga av den.**

   - **Åtgärder**: ange vilken åtgärd som ska vidtas för meddelanden som saknar förfalsknings information:

     **Om e-post skickas av någon som inte har tillåtelse att imitera din domän**:

     - **Flytta meddelandet till mottagarnas skräp post mappar**
     - **Sätt i karantän meddelandet**

   - **Granska dina inställningar**: i stället för att klicka på varje enskilt steg visas inställningarna i en sammanfattning.

     - Du kan klicka på **Redigera** i varje avsnitt för att gå tillbaka till relevant sida.
     - Du kan aktivera eller **inaktivera** följande inställningar **direkt på den** här sidan:
       - **Aktivera skydd mot förfalskning**
       - **Aktivera ej autentiserad avsändare**

   När du är klar klickar du på **Spara** på valfri sida.

7. **Avancerade inställningar**: Klicka på **Redigera** för att konfigurera de avancerade gräns värdena för nät fiske tjänsten. Mer information finns i [avancerade nät fiske trösklar i principer för nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Avancerade nät fiske gränser**: Välj något av följande värden:

   - **1 – standard** (det här är standardvärdet).
   - **2 – aggressivt**
   - **3 – mer aggressivt**
   - **4-mest aggressivt**

   - **Granska dina inställningar**: Klicka på **Redigera** för att gå tillbaka till sidan för **avancerade nät fiske gränser** .

   När du är klar klickar du på **Spara** på valfri sida.

8. Gå tillbaka till sidan **Redigera din \<Name\> policy** och granska inställningarna och klicka sedan på **Stäng**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a>Använda säkerhets & Compliance Center för att ändra standard policy för skydd mot nätfiske i Microsoft Defender för Office 365

Standard policyn för anti-phishing i Microsoft Defender för Office 365 heter Office365 AntiPhish default och visas inte i listan över principer. Gör så här om du vill ändra standard principen för anti-nätfiske:

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.

2. Klicka på **standard princip** på sidan **mot nätfiske** .

3. **Standard sidan Redigera policyn för Office365 AntiPhish** visas. Följande avsnitt är tillgängliga, som innehåller identiska inställningar för när du [ändrar en anpassad princip](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):

   - **Falsk identitet**
   - **Falskt**
   - **Avancerade inställningar**

   Följande inställningar är inte tillgängliga när du ändrar standard princip:

   - Du kan se avsnitt och värden för **princip inställningar** , men det finns inga **redigerings** länkar, så du kan inte ändra inställningarna (princip namn, beskrivning och vem principen gäller för (gäller alla mottagare)).
   - Du kan inte ta bort standard principen.
   - Du kan inte ändra prioriteten för standard principen (den används alltid sist).

4. På **standard sidan Redigera en Office365 AntiPhish** du på Inställningar och klickar sedan på **Stäng**.

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Aktivera eller inaktivera anpassade skydds principer i Microsoft Defender för Office 365

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.

2. Observera värdet i kolumnen **status** :

   - Inaktivera principen genom att dra till **av** .

   - Aktivera principen genom att dra den till **aktiverat** .

Du kan inte inaktivera standard policyn för skydd mot nätfiske.

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Ange prioritet för anpassade anti-nätfiske-principer i Microsoft Defender för Office 365

Som standard får anti-nätfiske-principer en prioritet som baseras på den ordning de skapades i (nyare principer är lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Anpassade principer för anti-nätfiske visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0). Standard policyn för anti-phishing med namnet Office365 AntiPhish standard har värdet **lägst** och kan inte ändras.

 **Obs!** i säkerhets & Compliance Center kan du bara ändra prioriteten för skydd mot nätfiske när du har skapat den. I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln mot Phish (vilket kan påverka prioriteten för befintliga regler).

Om du vill ändra prioriteten för en princip klickar du på **öka prioriteten** eller **minska prioriteten** i egenskaperna för principen (du kan inte direkt ändra **prioritets** numret i säkerhets & Compliance Center). Det är bara att ändra prioriteten för en princip om du har flera principer.

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.

2. Välj den princip som du vill ändra. Om det redan är markerat avmarkerar du det och väljer det igen.

3. **Redigera den utfällbara \<name\> principen** visas.

   - Den anpassade AntiPhishing-principen med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.

   - Den anpassade AntiPhishing-principen med lägst **prioritet** (till exempel **3**) har bara knappen **öka prioritet** tillgänglig.

   - Om du har tre eller fler anpassade nät fiske principer har de värden mellan de högsta och lägsta prioriteterna både knappen **öka prioritet** och knappen **minska prioritet** tillgänglig.

4. Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använd säkerhets & Compliance Center för att Visa anti-nätfiske-principer i Microsoft Defender för Office 365

1. I säkerhets & Compliance Center och gå till **hot Management** \> **policy** \> **ATP-nätfiske**.

2. Gör något av följande:

   - Välj en anpassad Antivirus policy som du vill visa. Om det redan är markerat avmarkerar du det och väljer det igen.

   - Klicka på **standard princip** för att Visa standard policyn för skydd mot nätfiske.

3. **Redigera den utfällbara \<name\> principen** visas, där du kan visa inställningar och värden.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använda säkerhets & Compliance Center för att ta bort skydd mot nätfiske-principer i Microsoft Defender för Office 365

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**.

2. Välj den princip som du vill ta bort. Om det redan är markerat avmarkerar du det och väljer det igen.

3. I redigera den utfällbara **princip \<name\>** som visas klickar du på **ta bort princip** och sedan på **Ja** i varnings dialog rutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Använda Exchange Online PowerShell för att konfigurera AntiPhishing-principer i Microsoft Defender för Office 365

Som du redan har beskrivt består en policy mot skräp post och en Phish policy.

I Exchange Online PowerShell är skillnaden mellan policyer för Phish och Phish regler uppenbar. Du hanterar policyn för Phish genom att använda cmdletarna **\* -AntiPhishPolicy** och du hanterar anti-Phish-regler med hjälp av cmdlet **\* -AntiPhishRule** .

- I PowerShell skapar du policyn för Phish först och sedan skapar du regeln mot Phish som identifierar den princip som regeln gäller för.
- I PowerShell ändrar du inställningarna i policyn för Phish och anti-Phish-regeln separat.
- När du tar bort en policy för Phish från PowerShell tas motsvarande antiphish-regel inte bort automatiskt och vice versa.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Använda PowerShell för att skapa skydd mot nätfiske

Att skapa en skydds policy i PowerShell är en process i två steg:

1. Skapa policyn för Phish.
2. Skapa en regel för Phish som anger den policy för anti-Phish som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny Phish regel och koppla en befintlig, icke associerad policy mot anti-Phish-princip till den. En antiphish-regel kan inte kopplas till fler än en anti-Phish princip.

- Du kan konfigurera följande inställningar i nya principer mot Phish i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:

  - Skapa den nya principen som inaktive rad (_aktive rad_ `$false` på **New-AntiPhishRule-** cmdleten).
  - Ange prioriteten för principen när den skapas (_prioritet_ _\<Number\>_ ) på den **nya AntiPhishRule-** cmdleten.

- En ny policy för Phish som du skapar i PowerShell visas inte i fönstret säkerhets & efterlevnad förrän du tilldelar principen en antiphish-regel.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Steg 1: använda PowerShell för att skapa en policy för Phish

Använd följande syntax för att skapa en policy för Phish:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas policy för Phish forsknings karantän med följande inställningar:

- Principen är aktive rad (vi använder inte den _aktiverade_ parametern och standardvärdet `$true` ).
- Beskrivningen är: policy för forsknings avdelningen.
- Gör att organisationer-domäner skyddas för alla godkända domäner och riktade domäner för fabrikam.com.
- Anger Mai Fujito (mfujito@fabrikam.com) som användaren skyddar dig mot.
- Aktiverar post lådans intelligens.
- Aktiverar post lådans informations skydd och anger karantän åtgärden.
- Möjliggör säkerhets tips.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Detaljerad information om syntax och parametrar finns i [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Steg 2: använda PowerShell för att skapa en regel för Phish

Använd följande syntax för att skapa en Phish-regel:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

I det här exemplet skapas en Phish regel som heter Research Department med följande villkor:

- Regeln associeras med policyn för Phish med namnet forsknings karantän.
- Regeln gäller för medlemmar i gruppen Research avdelning.
- Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Detaljerad information om syntax och parametrar finns i [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Använda PowerShell för att visa principer mot Phish

Använd följande syntax för att visa befintliga principer för Phish:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

I det här exemplet returneras en sammanfattande lista över alla Phish-principer tillsammans med angivna egenskaper.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

I det här exemplet returneras alla egenskapsvärde för Phish policy med namnet chefer.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Detaljerad information om syntax och parametrar finns i [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Använda PowerShell för att visa regler för Phish

Använd följande syntax för att visa befintliga regler för Phish:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

I det här exemplet returneras en sammanfattande lista över alla Phish regler tillsammans med angivna egenskaper.

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

I det här exemplet returneras alla egenskaps värden för Phish regeln contoso-chefer.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns i [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Använda PowerShell för att ändra policyn för Phish

Förutom följande objekt är samma inställningar tillgängliga när du ändrar en policy för Phish i PowerShell som när du skapar policyn enligt beskrivningen i [steg 1: använda PowerShell för att skapa ett princip policy för Phish](#step-1-use-powershell-to-create-an-anti-phish-policy) .

- _MakeDefault_ -växeln som aktiverar den angivna principen till standard principen (tillämpas på alla, alltid **lägst** prioritet och du kan inte ta bort den) är bara tillgänglig när du ändrar en policy mot Phish i PowerShell.

- Du kan inte byta namn på en policy mot Phish ( **set-AntiPhishPolicy** -cmdleten har ingen _namn_ parameter). När du byter namn på en skydds princip i säkerhets & Compliance Center byter du bara namn på _regeln_ mot Phish.

Använd följande syntax för att ändra en policy för Phish:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Använda PowerShell för att ändra regler för Phish

Den enda inställning som inte är tillgänglig när du ändrar en anti-Phish-regel i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel. Information om hur du aktiverar eller inaktiverar befintliga regler för Phish finns i nästa avsnitt.

Annars är inga ytterligare inställningar tillgängliga när du ändrar en Phish-regel i PowerShell. Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en antiphish regel](#step-2-use-powershell-to-create-an-anti-phish-rule) -avsnitt tidigare i det här avsnittet.

Om du vill ändra en Phish regel använder du följande syntax:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Använda PowerShell för att aktivera eller inaktivera Phish regler

Aktivering eller inaktive ring av en Phish regel i PowerShell aktiverar eller inaktiverar hela AntiPhishing-principen (anti-Phish-regeln och den tilldelade anti-Phish-principen). Du kan inte aktivera eller inaktivera standard policyn för skydd mot nätfiske (det gäller alltid alla mottagare).

Så här aktiverar eller inaktiverar du en Phish-regel i PowerShell:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

I det här exemplet inaktive ras den Phish marknadsförings avdelningen.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Aktivera-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) och [disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Använd PowerShell för att ange prioriteten för antiphish-regler

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Använd följande syntax för att ange prioriteten för en anti-Phish-regel i PowerShell:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Anmärkningar**:

- Om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-AntiPhishRule** cmdlet i stället.

- Standard policyn för Phish har ingen motsvarande anti-Phish-regel och har alltid det icke ändrings bara prioritet svärdet **lägst**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Använda PowerShell för att ta bort principer för Phish

När du använder PowerShell för att ta bort en policy för Phish, tas inte motsvarande antiphish-regel bort.

Använd följande syntax för att ta bort en policy för Phish i PowerShell:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

I det här exemplet tas policyn för Phish bort från marknadsförings avdelningen.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Använda PowerShell för att ta bort Phish regler

När du använder PowerShell för att ta bort en antiphish-regel tas motsvarande policy mot Phish inte bort.

Om du vill ta bort en Phish regel i PowerShell använder du följande syntax:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

Det här exemplet tar bort regeln marknadsförings avdelning för Phish.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Gör något av följande för att kontrol lera att du har konfigurerat skydd mot nätfiske i Microsoft Defender för Office 365:

- I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP-nätfiske**. Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden. Gör något av följande om du vill visa mer information:

  - Välj en princip i listan och visa detaljerna i den utfällbara informationen.
  - Klicka på **standard policy** och se informationen i utfällbar form.

- I Exchange Online PowerShell ersätter du \<Name\> med namnet på principen eller regeln och kör följande kommando och kontrollerar inställningarna:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
