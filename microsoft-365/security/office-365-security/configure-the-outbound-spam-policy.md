---
title: Konfigurera utgående skräppostfiltrering
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om hur du konfigurerar principer för skräppost som skickas ut och ut och som gäller för specifika användare, grupper eller domäner i organisationen.
ms.openlocfilehash: 644ffb51c92f4d71d3ae2cde1eba408289573f48
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036794"
---
# <a name="configure-outbound-spam-filtering"></a>Konfigurera utgående skräppostfiltrering

Om du är en Microsoft 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection (EOP)-kund utan Exchange Online-postlådor kontrolleras utgående e-postmeddelanden som skickas via EOP automatiskt efter skräppost och ovanlig sändningsaktivitet.

Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto. Misstänkta utgående meddelanden markeras som skräppost (oavsett skräppostförtroendenivå eller SCL) och dirigeras genom [högriskleveranspoolen](high-risk-delivery-pool-for-outbound-messages.md) för att skydda tjänstens rykte (det vill än microsoft 365-källe-postservrar borta från IP-blockeringslistor). Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [varningsprinciper](../../compliance/alert-policies.md).

EOP använder utgående skräppostpolicyer som en del av organisationens övergripande försvar mot skräppost. Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost. För större granularitet kan du också skapa anpassade principer för skräppost som är tillämpliga på specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera principer för skräppost från utgående företag i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-kunder. Exchange Online Protection PowerShell för fristående EOP-kunder).

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a>Principer för utgående skräppost i Security & Compliance Center vs Exchange Online PowerShell eller Exchange Online Protection PowerShell

De grundläggande inslagen i en utgående spam-policy i EOP är:

- **Principen för skräppostfilter:** Anger åtgärder för utgående skräppostfiltreringsutslag och meddelandealternativen.

- **Regeln för skräppostfilter:** Anger prioritets- och mottagarfilter (vem principen gäller för) för en utgående skräppostfilterprincip.

Skillnaden mellan dessa två element är inte uppenbar när du hanterar utgående skräppostpoliser i Security & Compliance Center:

- När du skapar en utgående skräppostprincip i Security & Compliance Center skapar du faktiskt en utgående skräppostfilterregel och den tillhörande principen för skräppostfilter samtidigt som du använder samma namn för båda.

- När du ändrar en utgående skräppostprincip i Security & Compliance Center ändrar inställningarna som är relaterade till namn, prioritet, aktiverad eller inaktiverad och mottagarfilter regeln för skräppost. Alla andra inställningar ändrar den associerade principen för skräppostfilter.

- När du tar bort en utgående skräppostprincip från Security & Compliance Center tas regeln för skräppostfilter och den tillhörande principen för skräppost från skräppost bort.

I Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell är skillnaden mellan utgående skräppostfilterprinciper och utgående skräppostfilterregler uppenbar. Du hanterar principer för skräppostutgående skräppost med cmdlets ** \*-HostedContentFilterPolicy** och du hanterar utgående skräppostfilterregler med hjälp av ** \*cmdlets -HostedContentFilterRule.**

- I PowerShell skapar du först principen för skräppostfilter och skapar först den utgående skräppostfilterregeln som identifierar den princip som regeln gäller för.

- I PowerShell ändrar du inställningarna i principen för skräppost och regeln för skräppostfilter separat.

- När du tar bort en utgående skräppostfilterprincip från PowerShell tas inte motsvarande utgående skräppostfilterregel automatiskt bort och vice versa.

### <a name="default-outbound-spam-policy"></a>Standardpolicy för utgående skräppost

Varje organisation har en inbyggd utgående skräppostprincip med namnet Standard som har följande egenskaper:

- Den utgående skräppostfilterprincipen Standard tillämpas på alla mottagare i organisationen, även om det inte finns någon regel för utgående skräppostfilter (mottagarfilter) som är associerad med principen.

- Principen med namnet Standard har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (principen tillämpas alltid sist). Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.

- Principen som heter Standard är standardprincipen (egenskapen **IsDefault** har värdet `True`), och du kan inte ta bort standardprincipen.

Om du vill öka effektiviteten i skräppostfiltrering kan du skapa anpassade principer för skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Om du vill lägga till, ändra och ta bort principer för skräppost måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** För skrivskyddad åtkomst till principer för skräppost med utgående skräppost måste du vara medlem i rollgruppen **Säkerhetsläsare.** Mer information om rollgrupper i säkerhets- och efterlevnadscentret finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

- Våra rekommenderade inställningar för utgående skräppostpolicyer finns i [EOP:s policyinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)för skräppostfilter .

- [Standardvarningsprinciperna](../../compliance/alert-policies.md) **e-postöverföringsgränsen överskred**, **Misstänkta e-postsändningsmönster har upptäckts**och användaren har begränsat till att **skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) om ovanlig utgående e-postaktivitet och blockerade användare på grund av utgående skräppost. Mer information finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Vi rekommenderar att du använder dessa aviseringsprinciper i stället för meddelandealternativen i principer för skräppost.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Använd Security & Compliance Center för att skapa principer för skräppost för utgående

Om du skapar en anpassad utgående skräppostprincip i Security & Compliance Center skapas skräppostfilterregeln och den tillhörande skräppostfilterprincipen samtidigt med samma namn för båda.

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. Klicka på **Skapa en utgående princip**på sidan Inställningar för **skräppost.**

3. Konfigurera följande inställningar i **principen För skräppostutgående skräppost** som öppnas:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

4. (Valfritt) Expandera avsnittet **Meddelanden** om du vill konfigurera ytterligare användare som ska ta emot kopior och meddelanden om misstänkta utgående e-postmeddelanden:

   - **Skicka en kopia av misstänkta utgående e-postmeddelanden till specifika personer:** Den här inställningen lägger till de angivna användarna som mottagare av hemlig kopia i de misstänkta utgående meddelandena. Så här aktiverar du den här inställningen:

     a. Markera kryssrutan om du vill aktivera inställningen.

     b. Klicka på **Lägg till personer**. I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**

     c. Ange avsändarens e-postadress. Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.

     d. Klicka på ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) för att lägga till mottagarna.

        Upprepa de här stegen så många gånger det behövs.

        Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** i det utfällbara fältet. Om du vill ![ta](../../media/scc-remove-icon.png)bort en mottagare klickar du på Knappen Ta bort .

     e. Klicka på **Spara** när du är klar.

     Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.

   - **Meddela specifika personer om en avsändare blockeras på grund av att skicka skräppost som skickas:**

     > [!NOTE]
     > [Standardvarningsprincipen](../../compliance/alert-policies.md) **Användaren har begränsats från att skicka e-post** skickar redan e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**Global admins**) när användare blockeras på grund av att de överskrider gränserna i avsnittet **Mottagargränser.** Vi rekommenderar att du använder aviseringsprincipen i stället för den här inställningen i principen för utgående skräppost för att meddela administratörer och andra användare. Instruktioner finns i [Verifiera varningsinställningarna för begränsade användare](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).

     Så här aktiverar du den här inställningen:

     a. Markera kryssrutan om du vill aktivera inställningen.

     b. Klicka på **Lägg till personer**. I det utfällbara antalet mottagare som visas i utfällbara mottagare eller **ta bort mottagare:**

     c. Ange avsändarens e-postadress. Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.

     d. Klicka på ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) för att lägga till mottagarna.

        Upprepa de här stegen så många gånger det behövs.

        Mottagarna som du har lagt till visas i avsnittet **Mottagarlista** i det utfällbara fältet. Om du vill ![ta](../../media/scc-remove-icon.png)bort en mottagare klickar du på Knappen Ta bort .

     e. Klicka på **Spara** när du är klar.

     Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.

5. (Valfritt) Expandera avsnittet **Mottagargränser** om du vill konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden:

   > [!NOTE]
   > Dessa inställningar gäller endast för molnbaserade postlådor.
     
   - **Maximalt antal mottagare per användare**

     Ett giltigt värde är 0 till 10000. Standardvärdet är 0, vilket innebär att tjänsten som standard används. Mer information finns i [Skicka gränser för Microsoft 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

     - **Extern timgräns**: Det maximala antalet externa mottagare per timme.

     - **Intern timgräns**: Det maximala antalet interna mottagare per timme.

     - **Daglig gräns**: Det maximala totala antalet mottagare per dag.

   - **Åtgärd när en användare överskrider gränserna ovan**: Konfigurera åtgärden så att den vidtas när någon av **mottagarnas gränser** överskrids. För alla åtgärder får mottagarna som anges i **användaren begränsade från att skicka e-postaviseringsprincip** (och i den nu redundanta Meddela specifika personer om en **avsändare blockeras på grund av att skicka utgående skräppost** i principen för utgående skräppost får e-postmeddelanden.

     - **Begränsa användaren från att skicka e-post till följande dag:** Detta är standardvärdet. E-postmeddelanden skickas och användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.

       - Aktivitetsaviseringen **Användaren har begränsats från att skicka e-post** meddelar administratörer (via e-post och på sidan **Visa aviseringar).**

       - Alla mottagare som anges i **meddela specifika personer om en avsändare blockeras på grund av att skicka utgående skräppost** i policyn meddelas också.

       - Användaren kommer inte att kunna skicka fler meddelanden förrän följande dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.

     - **Begränsa användaren från att skicka e-post:** E-postmeddelanden skickas, användaren läggs till i portalen **[Begränsade användare]<https://sip.protection.office.com/restrictedusers> ** i Security & Compliance Center och användaren kan inte skicka e-post förrän de har tagits bort från portalen **Begränsade användare** av en administratör. När en administratör har tagit bort användaren från listan begränsas användaren inte igen för den dagen. Instruktioner finns i [Ta bort en användare från portalen Begränsade användare när](removing-user-from-restricted-users-portal-after-spam.md)du har skickat skräppost.

     - **Ingen åtgärd, endast avisering:** E-postmeddelanden skickas.

6. (Obligatoriskt) Expandera avsnittet **Tillämpat på** för att identifiera de interna avsändare som principen gäller för.

    Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden med samma villkor eller undantag använder ELLER-logik (till exempel _ \<sender1\> _ eller _ \<sender2\>_). Olika villkor eller undantag använder AND-logik (till exempel _ \<sender1\> _ och _ \<medlem i grupp 1\>_).

    Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor. Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).

    - **Avsändarendomänen är**: Anger avsändare i en eller flera av de konfigurerade accepterade domänerna i Office 365. Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän. Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.

    - **Avsändaren är**: Anger en eller flera användare i organisationen. Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan. Klicka igen i rutan **Lägg till en tagg** om du vill markera ytterligare avsändare.

    - **Avsändaren är medlem i**: Anger en eller flera grupper i organisationen. Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan. Klicka igen i rutan **Lägg till en tagg** om du vill markera ytterligare avsändare.

    - **Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag. Inställningarna och beteendet är likadana som villkoren.

7. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Använda Security & Compliance Center för att visa principer för skräppost från utgående

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för** skräppost ![kan](../../media/scc-expand-icon.png) du klicka på Expandera ikonen för att expandera en utgående skräppostpolicy:

   - Standardprincipen **Utgående skräppostfilterprincip**.

   - En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.

3. Principinställningarna visas i den utökade principinformation som visas eller så kan du klicka på **Redigera princip**.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Använda Security & Compliance Center för att ändra principer för skräppost för utgående

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för** skräppost ![kan](../../media/scc-expand-icon.png) du klicka på Expandera ikonen för att expandera en utgående skräppostpolicy:

   - Standardprincipen **Utgående skräppostfilterprincip**.

   - En anpassad princip som du skapade där värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**.

3. Klicka på **Redigera princip**.

För anpassade principer för utgående skräppost är de tillgängliga inställningarna i det utfällbara resultatet som visas identiska med de som beskrivs i avsnittet [Använd säkerhets- & Compliance Center för att skapa utgående skräppostprinciper.](#use-the-security--compliance-center-to-create-outbound-spam-policies)

För standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip**är avsnittet **Tillämpad** på inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.

Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.

### <a name="enable-or-disable-outbound-spam-policies"></a>Aktivera eller inaktivera principer för skräppost från utgående

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för** skräppost ![klickar](../../media/scc-expand-icon.png) du på Expandera ikonen för att expandera en anpassad princip som du har skapat (värdet i kolumnen **Typ** är **principen Anpassad utgående skräppost**).

3. Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.

   Flytta växlingsknappen åt vänster om du vill inaktivera principen: ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   Flytta växlingsknappen åt höger om du vill aktivera principen: ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

Du kan inte inaktivera standardpolicyn för utgående skräppost.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Ange prioritet för anpassade principer för skräppost från utgående

Som standard prioriteras principer för utgående skräppost som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Två principer kan inte ha samma prioritet.

Principer för anpassad skräppost visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0). Standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip** har **prioritetsvärdet Lägsta**och du kan inte ändra det.

Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräppost** hittar du de principer där värdet i kolumnen **Typ** är policy för **anpassad utgående skräppost**. Kontrollera värdena i kolumnen **Prioritet**:

   - Den anpassade utgående skräppostprincipen med ![högst prioritet](../../media/ITPro-EAC-DownArrowIcon.png) har värde nedåtpilen **ikon 0**.

   - Den anpassade utgående skräppostpolicyn med ![den lägsta](../../media/ITPro-EAC-UpArrowIcon.png) prioriteten har ![värdeupppilen **ikon n** (till exempel up arrow-ikonen](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Om du har tre eller flera anpassade utgående skräppostprinciper har ![principerna](../../media/ITPro-EAC-UpArrowIcon.png)![mellan högsta](../../media/ITPro-EAC-DownArrowIcon.png) och lägsta prioritet värden ikon](../../media/ITPro-EAC-DownArrowIcon.png) nedåtpilen **ikon n** (till exempel ![nedåtpilens nedåtpil ikon](../../media/ITPro-EAC-UpArrowIcon.png)![ **2**).

3. Klicka på ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) eller ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) om du vill flytta den anpassade principen för utgående skräppost uppåt eller nedåt i prioritetslistan.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Använd Security & Compliance Center för att ta bort principer för skräppost från utgående

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för** skräppost ![klickar](../../media/scc-expand-icon.png) du på Ikonen Expandera för att expandera den anpassade principen som du vill ta bort (kolumnen **Typ** är **principen Anpassad utgående skräppost**).

3. I den utökade principinformationen som visas klickar du på **Ta bort princip**.

4. Klicka på **Ja** i varningsrutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a>Använda Exchange Online PowerShell eller Exchange Online Protection PowerShell för att konfigurera principer för skräppost för utgående information

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Använda PowerShell för att skapa principer för skräppost än

Att skapa en utgående skräppostprincip i PowerShell är en tvåstegsprocess:

1. Skapa principen för skräppostfiltrets utgående skräppost.

2. Skapa den utgående skräppostfilterregeln som anger den utgående skräppostfilterprincip som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny regel för skräppostfilter och tilldela den en befintlig, oassocierad utgående skräppostfilterprincip. En regel för skräppostfilter kan inte associeras med mer än en utgående skräppostfilterprincip.

- Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Security & Compliance Center förrän du har skapat principen:

  - Skapa den nya principen som inaktiverad (_Aktiverad_ `$false` på cmdleten **Ny värdbaseradOutboundSpamFilterRule).**

  - Ange prioritet för principen när du skapar ( _ \<Prioritetsnummer\>_) på cmdleten **New-HostedOutboundSpamFilterRule).** _Priority_

- En ny princip för skräppostfilter som du skapar i PowerShell visas inte i Security & Compliance Center förrän du tilldelar principen till en skräppostfilterregel.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Steg 1: Använd PowerShell för att skapa en utgående skräppostfilterprincip

Om du vill skapa en princip för skräppostfilter för att skapa ett utgående skräppostfilter använder du den här syntaxen:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas en ny utgående skräppostfilterprincip med namnet Contoso Executives med följande inställningar:

- Mottagarhastighetsgränserna är begränsade till mindre värden som standardvärdena. Mer information finns i [Skicka gränser för Microsoft 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- När en av gränserna har nåtts hindras användaren från att skicka meddelanden.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter

Om du vill skapa en regel för skräppostfilter kan du använda den här syntaxen:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

I det här exemplet skapas en ny regel för skräppostfilter med namnet Contoso Executives med följande inställningar:

- Den utgående skräppostfilterprincipen Contoso Executives är associerad med regeln.

- Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Detaljerad syntax- och parameterinformation finns i [Ny värddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Använda PowerShell för att visa principer för skräppostutgående skräppost

Om du vill returnera en sammanfattningslista över alla principer för skräppostfilter kör du det här kommandot:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Om du vill returnera detaljerad information om en specifik utgående skräppostfilterprincip använder du den här syntaxen:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterprincipen Chefer.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Detaljerad syntax- och parameterinformation finns i [Hämta värddredOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Använda PowerShell för att visa regler för skräppostfilter

Om du vill visa befintliga regler för skräppostfilter använder du följande syntax:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Om du vill returnera en sammanfattningslista över alla regler för skräppostfilter kör du det här kommandot:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Om du vill returnera detaljerad information om en specifik regel för skräppostfilter använder du den här syntaxen:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

I det här exemplet returneras alla egenskapsvärden för den utgående skräppostfilterregeln Contoso Executives.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Detaljerad syntax- och parameterinformation finns i [Hämta VärddredOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Använda PowerShell för att ändra principer för skräppost från skräppost

Samma inställningar är tillgängliga när du ändrar en policy för skadlig kodfilter i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: Använd PowerShell för att skapa ett utgående skräppostfilterprincipavsnitt](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) tidigare i det här avsnittet.

**Du**kan inte byta namn på en utgående skräppostfilterprincip (cmdleten **Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._ När du byter namn på en utgående skräppostprincip i Security & Compliance Center byter du bara namn på _regeln för_skräppostfilter.

Om du vill ändra en utgående skräppostfilterprincip använder du den här syntaxen:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Använda PowerShell för att ändra regler för skräppostfilter

Den enda inställning som inte är tillgänglig när du ändrar en utgående skräppostfilterregel i PowerShell är parametern Aktiverad som gör att du kan skapa en _inaktiverad_ regel. Information om hur du aktiverar eller inaktiverar befintliga regler för skräppostfilter finns i nästa avsnitt.

Annars är inga ytterligare inställningar tillgängliga när du ändrar en utgående skräppostfilterregel i PowerShell. Samma inställningar är tillgängliga när du skapar en regel som beskrivs i [steg 2: Använd PowerShell för att skapa ett utgående skräppostfilterregelavsnitt](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) tidigare i det här avsnittet.

Om du vill ändra en regel för skräppostfilter använder du den här syntaxen:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Detaljerad syntax- och parameterinformation finns i [Ange-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för skräppostfilter

Om du aktiverar eller inaktiverar en regel för skräppostfilter i PowerShell aktiveras eller inaktiveras hela principen om utgående skräppost (regeln för utgående skräppostfilter och den tilldelade principen för skräppostfilter). Du kan inte aktivera eller inaktivera standardprincipen för utgående skräppost (den tillämpas alltid på alla mottagare).

Om du vill aktivera eller inaktivera en utgående skräppostfilterregel i PowerShell använder du den här syntaxen:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras den utgående skräppostfilterregeln med namnet Marknadsavdelningen.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Detaljerad syntax- och parameterinformation finns i [Aktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) och [Inaktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Använda PowerShell för att ange prioritet för regler för skräppostfilter

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Om du vill ange prioritet för en utgående skräppostfilterregel i PowerShell använder du följande syntax:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Anmärkningar**:

- Om du vill ange prioritet för en ny regel när du skapar den använder du parametern _Prioritet_ på cmdleten **New-HostedOutboundSpamFilterRule** i stället.

- Principen för skräppostfilter för utgående har ingen motsvarande skräppostfilterregel och har alltid det omodifierbara prioritetsvärdet **Lägsta**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Använda PowerShell för att ta bort principer för skräppost från skräppost

När du använder PowerShell för att ta bort en utgående skräppostfilterprincip tas inte motsvarande utgående skräppostfilterregel bort.

Om du vill ta bort en princip för skräppostfilter i PowerShell använder du den här syntaxen:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

I det här exemplet tas den utgående skräppostfilterprincipen marknadsföringsavdelningen bort.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort värddyreradOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Använda PowerShell för att ta bort regler för skräppostfilter

När du använder PowerShell för att ta bort en utgående skräppostfilterregel tas inte motsvarande utgående skräppostfilterprincip bort.

Om du vill ta bort en regel för skräppostfilter i PowerShell använder du den här syntaxen:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

I det här exemplet tas den utgående skräppostfilterregeln med namnet Marknadsavdelningen bort.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort värddyreradOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Mer information

[Ta bort blockerade användare från portalen med åtkomstbegränsade användare](removing-user-from-restricted-users-portal-after-spam.md)

[Pool med hög riskleverans för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md)

[Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md)
