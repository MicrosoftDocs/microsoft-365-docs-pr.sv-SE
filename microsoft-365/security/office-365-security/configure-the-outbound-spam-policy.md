---
title: Konfigurera utgående skräppostfiltrering
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa om hur de visar, skapar, ändrar och tar bort principer för utgående skräppost i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2448bb7942f7694d2a6d6e9b98537a2b7ccb14d1
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331676"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Konfigurera utgående skräppostfiltrering i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kontrolleras automatiskt utgående e-postmeddelanden som skickas via EOP efter skräppost och ovanlig sändningsaktivitet.

Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto. Misstänkta utgående meddelanden markeras som skräppost (oavsett konfidensnivå för skräppost eller [](high-risk-delivery-pool-for-outbound-messages.md) SCL) och dirigeras genom högriskleveranspoolen för att skydda tjänstens rykte (det vill säga hålla Microsoft 365-käll-e-postservrarna borta från IP-blockeringslistor). Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [aviseringsprinciper.](../../compliance/alert-policies.md)

EOP använder principer för utgående skräppost som en del av organisationens totala skydd mot skräppost. Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost. För större detaljnivå kan du också skapa anpassade principer för utgående skräppost som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera principer för utgående skräppost i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

De grundläggande elementen i en princip för utgående skräppost i EOP är:

- **Principen för utgående skräppostfilter:** Anger åtgärderna för utgående skräppostfiltrering av bedömningsutskick och aviseringsalternativen.
- **Regeln för utgående skräppostfilter:** Anger prioritet och mottagarfilter (som principen gäller för) för en princip för utgående skräppostfilter.

Skillnaden mellan dessa två element är inte uppenbara när du hanterar utgående skräppost-faktorer i Säkerhets- och & Efterlevnadscenter:

- När du skapar en princip skapar du faktiskt en utgående skräppostfilterregel och samtidigt den associerade policyn för utgående skräppostfilter med samma namn för båda.
- När du ändrar en princip ändrar inställningar för namn, prioritet, aktiverade eller inaktiverade samt mottagarfilter regeln för skräppostfilter för utgående trafik. Alla andra inställningar ändrar den associerade policyn för skräppostfilter.
- När du tar bort en princip tas regeln för utgående skräppostfilter och tillhörande princip för utgående skräppostfilter bort.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i avsnittet [Använda Exchange Online PowerShell eller fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) för att konfigurera principer för utgående skräppost längre fram i den här artikeln.

Alla organisationer har en inbyggd policy för utgående skräppost med namnet Standard, som har följande egenskaper:

- Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon utgående skräppostfilterregel (mottagarfilter) kopplad till principen.
- Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist). Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.
- Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.

För att göra utgående skräppostfiltrering mer effektiv kan du skapa anpassade principer för utgående skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill lägga till, ändra och ta bort utgående skräppostprinciper måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** 
  - För skrivskyddad åtkomst till principer för utgående skräppost måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Våra rekommenderade inställningar för principer för utgående skräppost finns i Principinställningar för [utgående skräppostfilter i EOP.](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)

- Standardprinciperna för avisering med namnet Begränsning av e-postutskick har [](../../compliance/alert-policies.md) **överskridits,** mönster för misstänkta e-postutskick och Användaren har begränsats från att skicka e-post, som redan har skickat e-postmeddelanden till medlemmar i **gruppen TenantAdmins** **(globala** administratörer) om ovanliga utgående e-postaktiviteter och blockerade användare på grund av utgående skräppost.  Mer information finns i [Verifiera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Vi rekommenderar att du använder dessa aviseringsprinciper i stället för alternativen för meddelanden i principer för utgående skräppost.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Använd säkerhets- & för att skapa principer för utgående skräppost

När du skapar en anpassad utgående skräppostprincip i Säkerhets- och efterlevnadscenter för & skapas samtidigt skräppostfilterregeln och den tillhörande skräppostfilterprincipen med samma namn för båda.

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Anti-spam settings** klickar du på **Create an outbound policy**.

3. I **policyn för utgående skräppostfilter** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

4. (Valfritt) Expandera avsnittet **Meddelanden för** att konfigurera ytterligare användare som ska ta emot kopior och aviseringar om misstänkta utgående e-postmeddelanden:

   - **Skicka en kopia av misstänkta utgående** e-postmeddelanden till vissa personer : Den här inställningen lägger till de angivna användarna som mottagare av hemlig kopia i de misstänkta utgående meddelandena.

     > [!NOTE]
     > Den här inställningen fungerar bara i standardprincipen för utgående skräppost. Det fungerar inte i anpassade principer för utgående skräppost som du skapar.

     Så här aktiverar du den här inställningen:

     1. Markera kryssrutan för att aktivera inställningen.

     1. Klicka **på Lägg till personer.** I den **utfällna plats där Lägg till eller** ta bort mottagare visas:

     1. Ange avsändarens e-postadress. Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.

     1. Klicka på ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) för att lägga till mottagarna.

        Upprepa de här stegen så många gånger det behövs.

        De mottagare du lagt till visas i **avsnittet Mottagarlista** i den utfällade listrutan. Om du vill ta bort en mottagare klickar du ![ på Knappen Ta ](../../media/scc-remove-icon.png) bort.

     1. Klicka på **Spara** när du är klar.

        Om du vill inaktivera den här inställningen avmarkerar du kryssrutan.

   - **Meddela specifika personer om en avsändare är blockerad på grund av utgående skräppost:**

     > [!IMPORTANT]
     >
     > - Den här inställningen håller på att tas bort från policyn för utgående skräppost.
     >
     > - [Standardaviseringsprincipen](../../compliance/alert-policies.md)  med namnet Användare som inte kan skicka e-post skickar redan e-postmeddelanden till medlemmar i **gruppen TenantAdmins** (globala administratörer) när användare **blockeras** på grund av att de överskrider gränserna i avsnittet **Mottagargränser.** **Vi rekommenderar starkt att du använder aviseringsprincipen i stället** för den här inställningen i policyn för utgående skräppost för att meddela administratörer och andra användare. Anvisningar finns i [Verifiera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

5. (Valfritt) Expandera avsnittet **Mottagargränser** om du vill konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden:

   > [!NOTE]
   > De här inställningarna gäller endast för molnbaserade postlådor.

   - **Maximalt antal mottagare per användare**

     Ett giltigt värde är 0 till 10000. Standardvärdet är 0, vilket betyder att tjänstens standardinställningar används. Mer information finns i Skicka [begränsningar](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

     - **Gräns för extern timme:** Det maximala antalet externa mottagare per timme.

     - **Gräns för intern timme:** Det maximala antalet interna mottagare per timme.

     - **Daglig gräns:** Det maximala totala antalet mottagare per dag.

   - **Åtgärd när en användare överskrider gränserna ovan:** Konfigurera åtgärden som ska vidtas när någon av **mottagarbegränsningarna** överskrids. För alla åtgärder anger mottagarna  i användarens princip för begränsad e-postavisering (och i den nu redundanta Informerar du vissa personer om en avsändare blockeras på grund av inställningen för utgående skräppost i principen för utgående skräppost får du e-postmeddelanden. 

     - **Hindra användaren från att skicka e-post till följande** dag: Det här är standardvärdet. E-postaviseringar skickas och användaren kan inte skicka fler meddelanden förrän nästa dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.

       - Aktivitetsaviseringen med **namnet Användare begränsad från att skicka e-postmeddelanden** till administratörer (via e-post och på sidan **Visa** aviseringar).

       - Alla mottagare som anges i inställningen Meddela specifika personer om en avsändare blockeras på grund av att skicka **utgående** skräppost i principen meddelas också.

       - Användaren kan inte skicka fler meddelanden förrän nästa dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.

     - Hindra användaren från att skicka e-post: E-postaviseringar skickas, användaren läggs till på **portalen [Begränsade <https://sip.protection.office.com/restrictedusers> användare]** i säkerhets- och  efterlevnadscentret för & och användaren kan inte skicka e-post förrän han eller hon har tagits bort från portalen Begränsade användare av en administratör.  När en administratör tar bort användaren från listan begränsas inte användaren på nytt under den dagen. Instruktioner finns i Ta [bort en användare från portalen begränsade användare efter att ha skickat skräppost.](removing-user-from-restricted-users-portal-after-spam.md)

     - **Ingen åtgärd, endast avisering:** E-postaviseringar skickas.

6. (Valfritt) Expandera **avsnittet Automatisk vidarebefordran** om du vill styra automatisk vidarebefordran av e-post av användare till externa avsändare. Mer information finns i Styra [automatisk vidarebefordran av extern e-post i Microsoft 365.](external-email-forwarding.md)

   > [!NOTE]
   >
   > - Före september 2020 är de här inställningarna tillgängliga men inte tvingade.
   >
   > - De här inställningarna gäller endast för molnbaserade postlådor.
   >
   > - När automatisk vidarebefordran är inaktiverat får mottagaren en rapport om utebliven leverans (kallas även NDR-rapport eller icke-leveranskända meddelanden) om externa avsändare skickar e-post till en postlåda som har vidarebefordran på plats. Om meddelandet skickas av en  intern avsändare och vidarebefordransmetoden är vidarebefordran av postlåda [(kallas](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) även SMTP-vidarebefordran) får den interna avsändaren NDR-meddelandet.  Den interna avsändaren får ingen NDR om vidarebefordran inträffade på grund av en inkorgsregel.

   De tillgängliga värdena är:

   - **Automatiskt – Systemkontrollerat:** Tillåter utgående skräppostfiltrering att styra automatisk extern vidarebefordran av e-post. Det här är standardvärdet.
   - **På:** Automatisk vidarebefordran av extern e-post är inte inaktiverat av principen.
   - **Av:** All automatisk vidarebefordran av extern e-post är inaktiverad enligt principen.

7. (Obligatoriskt) Expandera avsnittet **Används för** för att identifiera de interna avsändare som principen gäller för.

    Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<sender1\>_ eller _\<sender2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<sender1\>_ och _\<member of group 1\>_).

    Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor. Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).

    - **Avsändardomänen** är: Anger avsändare i en eller flera av de konfigurerade godkända domänerna i organisationen. Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän. Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.

    - **Avsändaren är:** Anger en eller flera användare i organisationen. Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan. Klicka igen i **rutan Lägg till en** tagg om du vill välja fler avsändare.

    - **Avsändaren är medlem i**: Anger en eller flera grupper i organisationen. Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan. Klicka igen i **rutan Lägg till en** tagg om du vill välja fler avsändare.

    - **Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag. Inställningarna och beteendet är likadana som villkoren.

8. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att visa principer för utgående skräppost

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Anti-spam settings klickar** du på ![ Expand-ikonen ](../../media/scc-expand-icon.png) för att expandera en policy för utgående skräppost:

   - Standardprincipen med namnet **Utgående skräppostfilterprincip.**

   - En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad utgående skräppostprincip.**

3. Principinställningarna visas i den utökade principinformationen som visas, eller så kan du klicka på **Redigera princip.**

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Använda säkerhets- & för att ändra principer för utgående skräppost

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Anti-spam settings klickar** du på ![ Expand-ikonen ](../../media/scc-expand-icon.png) för att expandera en policy för utgående skräppost:

   - Standardprincipen med namnet **Utgående skräppostfilterprincip.**

   - En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad utgående skräppostprincip.**

3. Klicka på **Redigera princip**.

För anpassade principer för utgående skräppost är de tillgängliga inställningarna i den utfällsamma som beskrivs i avsnittet Use the Security & Compliance Center för att skapa [utgående](#use-the-security--compliance-center-to-create-outbound-spam-policies) skräppostprinciper.

I standardprincipen för utgående skräppost med  namnet Utgående skräppostfilter är avsnittet Används på inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.

Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.

### <a name="enable-or-disable-outbound-spam-policies"></a>Aktivera eller inaktivera principer för utgående skräppost

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Anti-spam settings klickar** du på Expand-ikonen för att expandera en anpassad princip som du skapat (värdet i kolumnen Typ är ![ Custom ](../../media/scc-expand-icon.png) **outbound spam policy**). 

3. Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.

   Flytta växlingsknappen åt vänster om du vill inaktivera principen: ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   Flytta växlingsknappen åt höger om du vill aktivera principen: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)

Du kan inte inaktivera standardprincipen för utgående skräppost.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Ange prioritet för anpassade principer för utgående skräppost

Som standard prioriteras principer för utgående skräppost utifrån den ordning de skapades (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

Anpassade principer för utgående skräppost visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0). Standardprincipen för utgående skräppost med namnet **Utgående skräppostfilterprincip** har prioritetsvärdet **Lägsta** och du kan inte ändra den.

Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Anti-spam settings** hittar du principerna där värdet i kolumnen **Typ** är **Custom outbound spam policy**. Kontrollera värdena i kolumnen **Prioritet**:

   - Den anpassade policyn för utgående skräppost med högsta prioritet har värdet ![ nedåtpilikonen ](../../media/ITPro-EAC-DownArrowIcon.png) **0.**

   - Den anpassade policyn för utgående skräppost med lägst prioritet har värdet ![ Uppåtpil ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (till exempel ![ Uppåtpil-ikonen ](../../media/ITPro-EAC-UpArrowIcon.png) **3).**

   - Om du har tre eller fler anpassade principer för utgående skräppost har principerna mellan högsta och lägsta prioritet värdena Uppåtpil-ikonen Nedåtpil-ikon n (till exempel uppåtpilikonen Nedåtpil ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ikon ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2).**

3. Klicka på ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) eller ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) för att flytta den anpassade policyn för utgående skräppost uppåt eller nedåt i prioritetslistan.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Använda Säkerhets- och & för att ta bort principer för utgående skräppost

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Anti-spam settings klickar** du på Expand icon för att expandera den anpassade princip som du vill ta bort (kolumnen Type är ![ Custom ](../../media/scc-expand-icon.png) **outbound spam policy**). 

3. I den utökade principinformationen som visas klickar du på **Ta bort princip**.

4. Klicka på **Ja** i varningsrutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för utgående skräppost

Som tidigare beskrivits består en princip för utgående skräppost av en utgående skräppostfilterprincip och en regel för utgående skräppostfilter.

I Exchange Online PowerShell eller fristående EOP PowerShell visar sig skillnaden mellan principer för utgående skräppostfilter och utgående skräppostfilter. Du hanterar principer för utgående skräppostfilter med hjälp av cmdletarna **\* -HostedOutboundSpamFilterPolicy** och du hanterar filterregler för utgående skräppost med hjälp av cmdletarna **\* -HostedOutboundSpamFilterRule.**

- I PowerShell skapar du först principen för utgående skräppostfilter och sedan skapar du den utgående skräppostfilterregeln som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna i filterprincipen för utgående skräppost och separat på filterregeln för utgående skräppost.
- När du tar bort en princip för utgående skräppostfilter från PowerShell tas inte motsvarande utgående skräppostfilterregel bort automatiskt, och tvärtom.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Använda PowerShell för att skapa principer för utgående skräppost

Det krävs två steg för att skapa en princip för utgående skräppost i PowerShell:

1. Skapa policyn för utgående skräppostfilter.
2. Skapa den utgående skräppostfilterregel som anger den utgående skräppostfilterprincip som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny regel för utgående skräppostfilter och tilldela en befintlig, oassocierad utgående skräppostfilterprincip till den. En utgående skräppostfilterregel kan inte associeras med mer än en princip för utgående skräppostfilter.

- Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Säkerhets- och &-efterlevnadscenter förrän du har skapat principen:

  - Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på cmdleten **New-HostedOutboundSpamFilterRule).**
  - Ange prioritet för principen vid skapande (_Prioritet_ ) på _\<Number\>_ cmdleten **New-HostedOutboundSpamFilterRule).**

- En ny utgående policy för skräppostfilter som du skapar i PowerShell visas inte i säkerhets- och efterlevnadscentret för & förrän du tilldelar principen till en regel för skräppostfilter.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Steg 1: Använda PowerShell för att skapa en princip för utgående skräppostfilter

Använd följande syntax för att skapa en princip för utgående skräppostfilter:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas en ny policy för utgående skräppostfilter med namnet Contoso Executives med följande inställningar:

- Mottagarens ratebegränsningar är begränsade till mindre värden som är standardvärdena. Mer information finns i Skicka [gränser över Microsoft 365-alternativ.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

- När en av begränsningarna har nåtts hindras användaren från att skicka meddelanden.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Steg 2: Använda PowerShell för att skapa en regel för utgående skräppostfilter

Använd följande syntax för att skapa en utgående skräppostfilterregel:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

I det här exemplet skapas en ny utgående skräppostfilterregel med namnet Contoso Executives med följande inställningar:

- Principen för utgående skräppostfilter med namnet Contoso Executives är kopplad till regeln.
- Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Använda PowerShell för att visa principer för utgående skräppostfilter

Om du vill returnera en sammanfattning av alla principer för utgående skräppostfilter kör du det här kommandot:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Använd följande syntax för att returnera detaljerad information om en viss utgående skräppostfilterprincip:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

Det här exemplet returnerar alla egenskapsvärden för policyn för utgående skräppostfilter med namnet Chefer.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Använda PowerShell för att visa regler för utgående skräppostfilter

Om du vill visa befintliga regler för skräppostfilter för utgående trafik använder du följande syntax:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Kör följande kommando för att returnera en sammanfattningslista över alla utgående skräppostfilterregler:

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

Använd följande syntax för att returnera detaljerad information om en viss utgående skräppostfilterregel:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

Det här exemplet returnerar alla egenskapsvärden för den utgående skräppostfilterregeln Contoso Executives.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterRule.](/powershell/module/exchange/get-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Använda PowerShell för att ändra principer för utgående skräppostfilter

Samma inställningar är tillgängliga när du ändrar en princip för skadlig programvara i PowerShell som när du skapar principen enligt beskrivningen i Steg [1:](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) Använda PowerShell för att skapa en princip för utgående skräppostfilter tidigare i den här artikeln.

> [!NOTE]
> Du kan inte byta namn på en utgående policy för skräppostfilter **(cmdleten Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._ När du byter namn på en utgående skräppostprincip i Säkerhets- och & säkerhets- och efterlevnadscenter byter du bara namn på filterregeln för _utgående skräppost._

Använd följande syntax för att ändra en princip för utgående skräppostfilter:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [Set-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Använda PowerShell för att ändra regler för utgående skräppostfilter

Den enda inställningen som inte är tillgänglig när du ändrar en regel för utgående skräppostfilter i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel. Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för utgående skräppostfilter.

Annars finns det inga ytterligare inställningar tillgängliga när du ändrar en regel för utgående skräppostfilter i PowerShell. Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i steg [2: Använd PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) för att skapa en utgående skräppostfilterregel tidigare i den här artikeln.

Använd följande syntax för att ändra en utgående skräppostfilterregel:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [Set-HostedOutboundSpamFilterRule.](/powershell/module/exchange/set-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för utgående skräppostfilter

Om du aktiverar eller inaktiverar en utgående skräppostfilterregel i PowerShell aktiveras eller inaktiveras principen för hela den utgående skräpposten (regeln för utgående skräppostfilter och policyn för utgående skräppostfilter). Du kan inte aktivera eller inaktivera standardprincipen för utgående skräppost (den används alltid för alla mottagare).

Om du vill aktivera eller inaktivera en utgående skräppostfilterregel i PowerShell använder du följande syntax:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras regeln för utgående skräppostfilter med namnet Marketing Department.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) och [Disable-HostedOutboundSpamFilterRule.](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Använda PowerShell för att ange prioriteten för utgående skräppostfilterregler

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Om du vill ange prioriteten för en utgående skräppostfilterregel i PowerShell använder du följande syntax:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i stället för cmdleten **New-HostedOutboundSpamFilterRule.**
>
> - Standardprincipen för utgående skräppostfilter har inte en motsvarande regel för skräppostfilter, och den har alltid det omoderbara prioritetsvärdet **Lägsta.**

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Använda PowerShell för att ta bort principer för utgående skräppostfilter

När du använder PowerShell för att ta bort en princip för utgående skräppostfilter tas inte motsvarande utgående skräppostfilterregel bort.

Om du vill ta bort en princip för utgående skräppostfilter i PowerShell använder du följande syntax:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

Det här exemplet tar bort policyn för utgående skräppostfilter med namnet Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Använda PowerShell för att ta bort regler för utgående skräppostfilter

När du använder PowerShell för att ta bort en utgående skräppostfilterregel tas inte motsvarande princip för skräppostfilter bort.

Om du vill ta bort en utgående skräppostfilterregel i PowerShell använder du följande syntax:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

Det här exemplet tar bort regeln för utgående skräppostfilter med namnet Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterRule.](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)

## <a name="for-more-information"></a>Mer information

[Ta bort blockerade användare från portalen med åtkomstbegränsade användare](removing-user-from-restricted-users-portal-after-spam.md)

[Pool med hög riskleverans för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md)

[Vanliga frågor och svar om skydd mot skräppost](anti-spam-protection-faq.yml)

[Rapporten Automatiskt vidarebefordrade meddelanden](mfi-auto-forwarded-messages-report.md)