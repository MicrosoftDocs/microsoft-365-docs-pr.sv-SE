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
description: Administratörer kan lära sig att visa, skapa, ändra och ta bort principer för utgående skräppost i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c2f68cac05f296771fc56d400e95d014811fe03a
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793010"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Konfigurera utgående skräppostfiltrering i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kontrolleras automatiskt utgående e-postmeddelanden som skickas via EOP för aktivitet som skräppost och ovanlig sändning.

Utgående skräppost från en användare i organisationen anger vanligtvis ett komprometterat konto. Misstänkta utgående meddelanden märks som skräppost (oavsett konfidensnivå för skräppost eller SCL) och dirigeras genom högriskleveranspoolen för att skydda tjänstens rykte (det vill säga hålla [Microsoft 365-käll-e-postservrarna](high-risk-delivery-pool-for-outbound-messages.md) borta från IP-blockeringslistor). Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [aviseringsprinciper.](../../compliance/alert-policies.md)

EOP använder principer för utgående skräppost som en del av organisationens totala skydd mot skräppost. Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för utgående skräppost. För större detaljnivå kan du också skapa anpassade principer för utgående skräppost som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera principer för utgående skräppost i säkerhetscentret i Microsoft 365 eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

De grundläggande elementen i en princip för utgående skräppost i EOP är:

- **Principen för utgående skräppostfilter:** Anger åtgärderna för utgående skräppostfiltrering av bedömningsutskick och aviseringsalternativen.
- **Regeln för utgående skräppostfilter:** Anger prioritet och mottagarfilter (som principen gäller för) för en princip för utgående skräppostfilter.

Skillnaden mellan dessa två element är inte uppenbara när du hanterar utgående skräppost-faktorer på säkerhetscentret:

- När du skapar en princip skapar du faktiskt en utgående skräppostfilterregel och samtidigt den associerade policyn för utgående skräppostfilter med samma namn för båda.
- När du ändrar en princip ändrar inställningar för namn, prioritet, aktiverade eller inaktiverade samt mottagarfilter regeln för skräppostfilter för utgående trafik. Alla andra inställningar ändrar den associerade policyn för skräppostfilter.
- När du tar bort en princip tas regeln för utgående skräppostfilter och tillhörande princip för utgående skräppostfilter bort.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) för att konfigurera principer för utgående skräppost längre fram i den här artikeln.

Alla organisationer har en inbyggd policy för utgående skräppost med namnet Standard, som har följande egenskaper:

- Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon utgående skräppostfilterregel (mottagarfilter) kopplad till principen.
- Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist). Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.
- Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.

För att göra utgående skräppostfiltrering mer effektiv kan du skapa anpassade principer för utgående skräppost med striktare inställningar som tillämpas på specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Microsoft 365 Säkerhetscenter på <https://security.microsoft.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://security.microsoft.com/antispam>.

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

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a>Använda säkerhetscentret för att skapa principer för utgående skräppost

När du skapar en anpassad utgående skräppostprincip i säkerhetscentret skapas skräppostfilterregeln och den tillhörande skräppostfilterprincipen samtidigt med samma namn för båda.

1. I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skydd mot skräppost** klickar du på Skapa ikon Skapa ![ ](../../media/m365-cc-sc-create-icon.png) **princip** och väljer sedan **Utgående** från listrutan.

3. Principguiden öppnas. Konfigurera följande inställningar på **sidan Namnge principen**:
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

5. Konfigurera **följande inställningar** på sidan Skyddsinställningar som öppnas:
   - **Meddelandegränser:** Inställningarna i det här avsnittet konfigurerar gränserna för utgående e-postmeddelanden **Exchange Online** postlådor:
     - **Ange en gräns för externa** meddelanden: Det maximala antalet externa mottagare per timme.
     - **Ange en gräns för interna** meddelanden: Det maximala antalet interna mottagare per timme.
     - **Ange en daglig meddelandegräns:** Det maximala totala antalet mottagare per dag.

     Ett giltigt värde är 0 till 10000. Standardvärdet är 0, vilket betyder att tjänstens standardinställningar används. Mer information finns i Skicka [begränsningar](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

    Ange ett värde i rutan eller använd pilarna för att öka/minska i rutan.

   - **Begränsning som gjorts för användare som** når meddelandegränsen: Välj en åtgärd i  listrutan när någon av begränsningarna i avsnittet Skyddsinställningar överskrids.

     För alla åtgärder får de  mottagare som angetts i användarens  inställning för begränsad e-postavisering (och i den nu redundanta aviseringen Meddela dessa användare och grupper om en avsändare blockeras på grund av att du skickat utgående skräppost senare på den här sidan) e-postmeddelanden.

     - **Hindra användaren från att skicka e-post till följande** dag: Det här är standardvärdet. E-postaviseringar skickas och användaren kan inte skicka fler meddelanden förrän nästa dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.
       - Aktivitetsaviseringen med **namnet Användare begränsad från att skicka e-postmeddelanden** till administratörer (via e-post och på sidan **Visa** aviseringar).
       - Alla mottagare som anges i inställningen Meddela specifika personer om en avsändare blockeras på grund av att skicka **utgående** skräppost i principen meddelas också.
       - Användaren kan inte skicka fler meddelanden förrän nästa dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.
     - **Hindra** användaren från att skicka e-post: E-postaviseringar skickas, användaren läggs till i Begränsade användare i säkerhetscentret och användaren kan inte skicka e-post förrän han eller hon har tagits bort från Begränsade användare av en  <https://security.microsoft.com/restrictedusers> administratör.  När en administratör tar bort användaren från listan begränsas inte användaren på nytt under den dagen. Instruktioner finns i Ta [bort en användare från portalen begränsade användare efter att ha skickat skräppost.](removing-user-from-restricted-users-portal-after-spam.md)
     - **Ingen åtgärd, endast avisering:** E-postaviseringar skickas.

   - **Regler för vidarebefordran:** Använd inställningarna i det här avsnittet för att styra automatisk vidarebefordran av **e Exchange Online postlådor** till externa avsändare. Mer information finns i Kontrollera [automatisk vidarebefordran av extern e-post i Microsoft 365](external-email-forwarding.md).

     > [!NOTE]
     > När automatisk vidarebefordran är inaktiverat får mottagaren en rapport om utebliven leverans (kallas även NDR-rapport eller icke-leveranskända meddelanden) om externa avsändare skickar e-post till en postlåda som har vidarebefordran på plats. Om meddelandet skickas av en  intern avsändare och vidarebefordransmetoden är vidarebefordran av postlåda [(kallas](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) även SMTP-vidarebefordran) får den interna avsändaren NDR-meddelandet.  Den interna avsändaren får ingen NDR om vidarebefordran inträffade på grund av en inkorgsregel.

     Välj någon av följande åtgärder i **listrutan Automatiska vidare** vidarebefordransregler:

     - **Automatiskt – Systemkontrollerat:** Tillåter utgående skräppostfiltrering att styra automatisk extern vidarebefordran av e-post. Det här är standardvärdet.
     - **På:** Automatisk vidarebefordran av extern e-post är inte inaktiverat av principen.
     - **Av:** All automatisk vidarebefordran av extern e-post är inaktiverad enligt principen.

   - **Meddelanden:** Använd inställningarna i avsnittet för att konfigurera ytterligare mottagare som ska få kopior och aviseringar om misstänkta utgående e-postmeddelanden:

     - **Skicka en kopia av misstänkta utgående** e-postmeddelanden som överskrider dessa gränser för dessa användare och grupper: Den här inställningen lägger till de angivna mottagarna i fältet Hemlig kopia i misstänkta utgående meddelanden.

       > [!NOTE]
       > Den här inställningen fungerar bara i standardprincipen för utgående skräppost. Det fungerar inte i anpassade principer för utgående skräppost som du skapar.

       Markera kryssrutan om du vill aktivera den här inställningen. I rutan som visas klickar du i rutan, anger en giltig e-postadress och trycker sedan på Retur eller väljer det fullständiga värde som visas under rutan.

       Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

   - **Meddela dessa användare och grupper om en avsändare är blockerad på grund av utgående skräppost**

     > [!IMPORTANT]
     >
     > - Den här inställningen håller på att tas bort från policyn för utgående skräppost.
     >
     > - [Standardaviseringsprincipen](../../compliance/alert-policies.md)  med namnet Användare som inte kan skicka e-post skickar redan e-postmeddelanden till medlemmar i **gruppen TenantAdmins** (globala administratörer) när användare **blockeras** på grund av att de överskrider gränserna i avsnittet **Mottagargränser.** **Vi rekommenderar starkt att du använder aviseringsprincipen i stället** för den här inställningen i policyn för utgående skräppost för att meddela administratörer och andra användare. Anvisningar finns i [Verifiera aviseringsinställningarna för begränsade användare.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

   Klicka på **Nästa** när du är klar.

6. Granska inställningarna på sidan **Granska** som visas. Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Du kan också klicka **på** Bakåt eller välja en specifik sida i guiden.

   Klicka på **Skapa** när du är klar.

7. På bekräftelsesidan som visas klickar du på **Klar**.

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a>Använda säkerhetscentret för att visa principer för utgående skräppost

1. I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Princip för skräppostskydd** letar du efter något av följande värden:
   - Värdet **för Type** är **Policyn för anpassad utgående skräppost**
   - **Namnvärdet** är **utgående policy mot skräppost (standard)**

   Följande egenskaper visas i listan över principer för skräppostskydd:

   - **Namn**
   - **Status**
   - **Prioritet**
   - **Typ**

3. När du väljer en princip för utgående skräppost genom att klicka på namnet visas principinställningarna i en utfällmapp.

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a>Använda säkerhetscentret för att ändra principer för utgående skräppost

1. I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skräppostskydd** väljer du en utgående policy för skräppost i listan genom att klicka på namnet:
   - En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad utgående skräppostprincip.**
   - Standardprincipen med namnet **Utgående policy mot skräppost (standard).**

3. I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Mer information om inställningarna finns i föregående Använda säkerhetscentret för att skapa principer för [utgående skräppost](#use-the-security-center-to-create-outbound-spam-policies) i den här artikeln.

   I standardprincipen för utgående skräppost är **avsnittet** Tillämpas på inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.

Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>Aktivera eller inaktivera anpassade principer för utgående skräppost

Du kan inte inaktivera standardprincipen för utgående skräppost.

1. I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skydd mot** skräppost  väljer du en princip med värdet Typ av policy för anpassad **utgående skräppost** i listan genom att klicka på namnet.

3. Högst upp i den utfällda menyn principinformation ser du något av följande värden:
   - **Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .
   - **Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.

4. I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.

5. Klicka **Stäng** i den utfällda menyn principinformation.

Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Ange prioritet för anpassade principer för utgående skräppost

Som standard prioriteras principer för utgående skräppost baserat på i vilken ordning de skapas (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Säkerhetscenter). Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.

 **Anmärkningar**:

- I säkerhetscentret kan du bara ändra prioriteten för policyn för utgående skräppost efter att du har skapat den. I PowerShell kan du åsidosätta standardprioriteten när du skapar regeln för skräppostfilter (vilket kan påverka prioriteringen för befintliga regler).
- Principer för utgående skräppost bearbetas i den ordning som de visas (den första principen har **prioritetsvärdet** 0). Standardprincipen för utgående skräppost har prioritetsvärdet **Lägsta** och du kan inte ändra det.

1. I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skydd mot skräppost** väljer  du en princip med värdet Typ av anpassad **utgående skräppost-policy** i listan genom att klicka på namnet.

3. Högst upp i den utfällda menyn principinformation som visas ser du **Öka prioritet** eller **Minska prioritet** baserat på det aktuella prioritetsvärdet och antalet anpassade principer:
   - Policyn för utgående skräppost med **prioritetsvärdet** **0** har endast alternativet **Minska** prioritet tillgängligt.
   - Policyn för utgående skräppost med det **lägsta prioritetsvärdet** (till exempel **3)** har endast **alternativet Öka** prioritet tillgängligt.
   - Om du har tre eller fler principer för utgående skräppost har  principer mellan de högsta och lägsta prioritetsvärdena både alternativen Öka prioritet och **Minska** prioritet tillgängliga.

   Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.

4. Klicka **Stäng** i den utfällda menyn principinformation när du är klar.

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a>Använda säkerhetscentret för att ta bort anpassade principer för utgående skräppost

När du använder säkerhetscentret för att ta bort en anpassad policy för utgående skräppost tas både skräppostfilterregeln och motsvarande policy för skräppostfilter bort. Du kan inte ta bort standardprincipen för utgående skräppost.

1. I säkerhetscentret går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skydd mot** skräppost  väljer du en princip med värdet Typ av policy för anpassad **utgående skräppost** i listan genom att klicka på namnet. Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.

3. I bekräftelsedialogrutan som visas klickar du på **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för utgående skräppost

Som tidigare beskrivits består en princip för utgående skräppost av en utgående skräppostfilterprincip och en regel för utgående skräppostfilter.

I Exchange Online PowerShell eller fristående EOP PowerShell syns skillnaden mellan principer för utgående skräppostfilter och utgående skräppostfilter. Du hanterar principer för utgående skräppostfilter med hjälp av cmdletarna **\* -HostedOutboundSpamFilterPolicy** och du hanterar filterregler för utgående skräppost med hjälp av cmdletarna **\* -HostedOutboundSpamFilterRule.**

- I PowerShell skapar du först principen för utgående skräppostfilter och sedan skapar du den utgående skräppostfilterregeln som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna i filterprincipen för utgående skräppost och separat på filterregeln för utgående skräppost.
- När du tar bort en princip för utgående skräppostfilter från PowerShell tas inte motsvarande utgående skräppostfilterregel bort automatiskt, och tvärtom.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Använda PowerShell för att skapa principer för utgående skräppost

Det krävs två steg för att skapa en princip för utgående skräppost i PowerShell:

1. Skapa policyn för utgående skräppostfilter.
2. Skapa den utgående skräppostfilterregel som anger den utgående skräppostfilterprincip som regeln gäller för.

   **Anmärkningar**:

   - Du kan skapa en ny regel för utgående skräppostfilter och tilldela en befintlig, oassocierad utgående skräppostfilterprincip till den. En utgående skräppostfilterregel kan inte associeras med mer än en princip för utgående skräppostfilter.
   - Du kan konfigurera följande inställningar för nya principer för skräppostfilter i PowerShell som inte är tillgängliga i säkerhetscentret förrän du har skapat principen:
     - Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på cmdleten **New-HostedOutboundSpamFilterRule).**
     - Ange prioritet för principen vid skapande (_Prioritet_ ) på _\<Number\>_ cmdleten **New-HostedOutboundSpamFilterRule).**
   - En ny princip för utgående skräppostfilter som du skapar i PowerShell visas inte i säkerhetscentret förrän du tilldelar principen till en regel för utgående skräppostfilter.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Steg 1: Använda PowerShell för att skapa en princip för utgående skräppostfilter

Använd följande syntax för att skapa en princip för utgående skräppostfilter:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas en ny policy för utgående skräppostfilter med namnet Contoso Executives med följande inställningar:

- Mottagarens ratebegränsningar är begränsade till mindre värden som är standardvärdena. Mer information finns i Skicka [begränsningar över Microsoft 365 alternativ.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

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
> Du kan inte byta namn på en utgående policy för skräppostfilter **(cmdleten Set-HostedOutboundSpamFilterPolicy** har ingen _namnparameter)._ När du byter namn på en utgående skräppostprincip i säkerhetscentret byter du bara namn på regeln för utgående _skräppostfilter._

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

**Anmärkningar**:

- Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i stället för cmdleten **New-HostedOutboundSpamFilterRule.**
- Standardprincipen för utgående skräppostfilter har inte en motsvarande regel för skräppostfilter, och den har alltid det omoderbara prioritetsvärdet **Lägsta.**

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
