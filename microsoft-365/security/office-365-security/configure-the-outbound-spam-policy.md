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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa, skapa, ändra och ta bort utgående skräp post principer i Exchange Online Protection (EOP).
ms.openlocfilehash: 1e25d687ea22c70ba36f7c183b1fd8e578f7fa13
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683337"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Konfigurera utgående skräp post filtrering i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kontrol leras automatiskt utgående e-postmeddelanden som skickas via EOP för skräp post och ovanliga meddelanden.

Utgående skräp post från en användare i din organisation indikerar vanligt vis ett komprometterat konto. Misstänkta utgående meddelanden markeras som skräp post (oavsett säkerhets nivån för skräp post eller SCL) och dirigeras via poolen med [hög risk](high-risk-delivery-pool-for-outbound-messages.md) för att skydda tjänstens rykte (det vill säga Microsoft 365 Source e-postservrar med IP-adressblock). Administratörer meddelas automatiskt om misstänkt utgående e-postaktivitet och blockerade användare via [aviserings principer](../../compliance/alert-policies.md).

EOP använder utgående spam-principer som en del av organisationens allmänna försvar mot skräp post. Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standard princip för utgående e-post. För högre precision kan du också skapa anpassade principer för utgående skräp post som gäller för specifika användare, grupper eller domäner i organisationen. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera regler för utgående skräp post i säkerhets & efterföljandekrav eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

De grundläggande delarna i en regel för utgående e-post i EOP är:

- **Filter policy för utgående e-post**: anger åtgärderna för utgående spam-filtrering verdicts och meddelande alternativen.
- **Filter regeln för utgående e-post**: anger de prioritets-och mottagar filter (som principen gäller för) för en utgående filter policy för skräp post.

Skillnaden mellan dessa två element är inte uppenbar när du hanterar utgående spam-principer i säkerhets & Compliance Center:

- När du skapar en princip skapar du verkligen en utgående filter regel för skräp post och den associerade principen för skräp post filter samtidigt med samma namn för båda.
- När du ändrar en princip kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra regeln för utgående skräp post filter. Alla andra inställningar ändrar den associerade filtret för skräp post filter.
- När du tar bort en princip tas regeln för utgående skräp post bort och den associerade filtrerings principen för utgående e-post raderas.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i [använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera avsnittet för principer för skräp post](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) senare i den här artikeln.

Varje organisation har inbyggd princip för skräp post som heter standard och har följande egenskaper:

- Principen tillämpas på alla användare i organisationen, även om det inte finns någon utgående filter regel (mottagar filter) som är kopplad till principen.
- Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist). Alla anpassade principer som du skapar har alltid högre prioritet än principen som heter Standard.
- Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.

Om du vill öka effektiviteten för utgående skräp post filtrering kan du skapa anpassade principer för utgående e-post med striktare inställningar som tillämpas på specifika användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - För att lägga till, ändra och ta bort regler för utgående skräp post måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .
  - Om du vill ha skrivskyddad åtkomst till skräp post principer måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- De rekommenderade inställningarna för utgående skräp post finns i [EOP utgående filter princip inställningar för skräp post](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- Standard [aviserings principerna](../../compliance/alert-policies.md) med **begränsning för e-postutskick har överskridits**, **misstänkt e-post som skickar mönster** och **användare hindras från att skicka e-post** till medlemmar i gruppen **TenantAdmins** (**globala administratörer**) om ovanliga utgående e-postaktiviteter och blockerade användare på grund av utgående skräp post. Mer information finns i [Verifiera aviserings inställningarna för användare med begränsad åtkomst](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Vi rekommenderar att du använder dessa aviserings principer i stället för meddelande alternativen i principer för utgående skräp post.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Använda säkerhets & Compliance Center för att skapa principer för utgående skräp post

Om du skapar en anpassad princip för utgående e-post i säkerhets & Compliance Center skapas skräp post filter regeln och den associerade skräp post filter principen samtidigt med samma namn för båda.

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräp post** klickar du på **skapa en utgående princip**.

3. I **principen utgående skräp post filter** lägger du till följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

4. Skriver Expandera avsnittet **meddelanden** för att konfigurera ytterligare användare som ska få kopior och meddelanden om misstänkta utgående e-postmeddelanden:

   - **Skicka en kopia av misstänkta utgående e-postmeddelanden till vissa personer**: den här inställningen lägger till angivna användare som hemlig kopia för de misstänkta utgående meddelandena.

     > [!NOTE]
     > Den här inställningen fungerar bara i standard principen för utgående e-post. Den fungerar inte i anpassade principer för utgående e-post som du skapar.

     Så här aktiverar du inställningen:

     1. Markera kryss rutan om du vill aktivera inställningen.

     1. Klicka på **Lägg till personer**. I **Lägg till eller ta bort** utfällda mottagare visas:

     1. Ange avsändarens e-postadress. Du kan ange flera e-postadresser avgränsade med semikolon (;) eller en mottagare per rad.

     1. Klicka på ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) för att lägga till mottagarna.

        Upprepa de här stegen så många gånger det behövs.

        Mottagarna som du lägger till visas i avsnittet **mottagar lista** på utfällda objekt. Om du vill ta bort en mottagare klickar du på ![ knappen Ta bort ](../../media/scc-remove-icon.png) .

     1. Klicka på **Spara** när du är klar.

        Om du vill inaktivera den här inställningen avmarkerar du kryss rutan.

   - **Meddela specifika personer om en avsändare blockeras på grund av inkommande skräp post**:

     > [!IMPORTANT]
     >
     > - Den här inställningen används för att utgå från principer för utgående skräp post.
     >
     > - Standard [aviserings principen](../../compliance/alert-policies.md) med **användare som är begränsad från att skicka e-post skickar inte** e-postmeddelanden till medlemmar i gruppen **TenantAdmins** (**globala administratörer**) när användare blockeras på grund av begränsningarna i området för **mottagar gränser** . **Vi rekommenderar starkt att du använder notifieringsregeln i stället för den här inställningen i principen för utgående skräp post för att meddela administratörer och andra användare**. Anvisningar finns i [Verifiera aviserings inställningarna för användare med begränsad](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)åtkomst.

5. Skriver Expandera avsnittet **mottagar gränser** för att konfigurera begränsningar och åtgärder för misstänkta utgående e-postmeddelanden:

   > [!NOTE]
   > De här inställningarna gäller endast för molnbaserade post lådor.

   - **Maximalt antal mottagare per användare**

     Ett giltigt värde är 0 till 10000. Standardvärdet är 0, vilket innebär att tjänstens standardinställningar används. Mer information finns i avsnittet om att [Skicka gränser](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

     - **Extern Tim gräns**: maximalt antal externa mottagare per timme.

     - **Intern gräns för varje timme**: det högsta antalet interna mottagare per timme.

     - **Daglig gräns**: det högsta antalet mottagare per dag.

   - **Åtgärd när en användare överskrider ovanstående gränser**: Konfigurera den åtgärd som ska vidtas när någon av de **mottagande gränserna** överskrids. För alla åtgärder är mottagarna angivna i **användarens begränsade från att skicka e-** postaviserings princip (och i det **här meddelandet om att en avsändare har blockerats på grund av att den utgående skräp posten** avinstalleras.

     - **Hindra användaren från att skicka e-post till följande dag**: Detta är standardvärdet. E-postaviseringar skickas och användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.

       - Aktivitets aviseringen som heter **användare begränsad från att skicka e-post till** administratörer (via e-post och på sidan **Visa aviseringar** ).

       - Alla mottagare som anges i **meddela vissa personer om en avsändare blockeras på grund av utskick av utgående skräp post** i principen informeras också.

       - Användaren kan inte skicka fler meddelanden förrän följande dag, baserat på UTC-tid. Det finns inget sätt för administratören att åsidosätta det här blocket.

     - **Hindra användaren från att skicka e-post**: e-postaviseringar skickas, användaren läggs till i gruppen **[ <https://sip.protection.office.com/restrictedusers> begränsade användare]** i säkerhets & Compliance Center och användaren kan inte skicka e-post förrän de tas bort från portalen för **begränsade användare** av en administratör. När en administratör tar bort användaren från listan kommer användaren inte att begränsas till den dagen. Anvisningar finns i [ta bort en användare från portalen med begränsade användare när du skickar skräp post](removing-user-from-restricted-users-portal-after-spam.md).

     - **Ingen åtgärd, endast meddelande**: e-postaviseringar skickas.

6. Skriver Expandera avsnittet **Automatic Forwarding** för att styra automatisk vidarebefordran av e-post till externa avsändare. Mer information finns i [styra automatisk extern e-postvidarebefordran i Microsoft 365](external-email-forwarding.md).

   > [!NOTE]
   >
   > - Före den september 2020 är de här inställningarna tillgängliga men inte tvingande.
   >
   > - De här inställningarna gäller endast för molnbaserade post lådor.
   >
   > - När automatisk vidarebefordran är inaktive rad kommer mottagaren att få en rapport om utebliven leverans (kallas även för ett NDR-eller studs meddelande) om externa avsändare skickar e-post till en post låda som har vidarebefordran. Om meddelandet skickas av en intern avsändare **och** metoden för vidarebefordran av [e-post](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (kallas även för SMTP- _vidarebefordran_) kommer den interna avsändaren att få NDR-rapporten. Intern avsändaren får inte en NDR om vidarebefordran skedde på grund av en regel för Inkorgen.

   De tillgängliga värdena är:

   - **Automatisk Systemstyrd**: tillåter utgående skräp post filtrering för automatisk överföring av externa e-postmeddelanden. Det här är standardvärdet.
   - **Den**: automatisk överföring av externa e-post är inte inaktive rad av principen.
   - **Av** den här principen är inaktive rad för automatisk vidarebefordring av externa e-postmeddelanden.

7. Kunna Expandera avsnittet **används** för att identifiera de interna avsändare som principen gäller för.

    Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<sender1\>_ eller _\<sender2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<sender1\>_ och _\<member of group 1\>_).

    Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor. Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).

    - **Avsändarens domän är**: anger avsändare i en eller flera av de konfigurerade godkända domänerna i organisationen. Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän. Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.

    - **Avsändare är**: anger en eller flera användare i organisationen. Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan. Klicka på rutan **Lägg till en tagg** för att välja fler avsändare.

    - **Avsändaren är medlem i**: anger en eller flera grupper i din organisation. Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan. Klicka på rutan **Lägg till en tagg** för att välja fler avsändare.

    - **Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag. Inställningarna och beteendet är likadana som villkoren.

8. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Använd säkerhets & Compliance Center för att visa principer för utgående skräp post

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att expandera en princip för utgående skräp post:

   - Standard principen med namnet **utgående skräp post filter princip**.

   - En anpassad princip som du skapade där värdet i kolumnen **Type** är anpassat för **utgående skräp post**.

3. Princip inställningarna visas i den utökade princip informationen som visas, eller så kan du klicka på **Redigera princip**.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Använda inställningarna för säkerhets & efterlevnad för att ändra principer för utgående skräp post

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att expandera en princip för utgående skräp post:

   - Standard principen med namnet **utgående skräp post filter princip**.

   - En anpassad princip som du skapade där värdet i kolumnen **Type** är anpassat för **utgående skräp post**.

3. Klicka på **Redigera princip**.

För anpassade principer för utgående e-post är de tillgängliga inställningarna i utfällning som visas identiska med de som beskrivs i avsnittet [använda säkerhets & efterlevnad för att skapa regler för utgående skräp post](#use-the-security--compliance-center-to-create-outbound-spam-policies) .

För den utgående standardinställningen för skräp post **filtrerings** principen är alternativet **tillämpa på** inte tillgängligt (principen gäller för alla) och du kan inte byta namn på principen.

Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.

### <a name="enable-or-disable-outbound-spam-policies"></a>Aktivera och inaktivera principer för utgående skräp post

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att expandera en anpassad princip som du har skapat (värdet i kolumnen **Type** är **anpassad princip för utgående skräp post**).

3. Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.

   Flytta växlingsknappen åt vänster om du vill inaktivera principen: ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   Flytta växlingsknappen åt höger om du vill aktivera principen: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)

Det går inte att inaktivera standard principen för utgående e-post.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Ange prioritet för anpassade principer för utgående skräp post

Som standard ges principer för utgående skräp post en prioritet som baseras på den ordning de skapades (nyare policys är lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

Anpassade principer för utgående skräp post visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0). Standardvärdet för utgående skräp post **filtrerings princip** har värdet **lägst** och kan inte ändras.

Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. Leta reda på de principer där värdet i kolumnen **typ** är **anpassat för utgående skräp post** på sidan **Inställningar för skräp post** . Kontrollera värdena i kolumnen **Prioritet**:

   - Den anpassade principen för utgående skräp post med den högsta prioriteten har ikonen för värde ![ nedpilen ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Den anpassade principen för utgående skräp post med lägst prioritet har ![ ikonen för värde uppåt ](../../media/ITPro-EAC-UpArrowIcon.png)  (till exempel uppåtpil ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Om du har tre eller fler anpassade principer för utgående e-post har principerna mellan den högsta och lägsta prioriteten ikonen för att hålla ned en nedåtpil (till exempel ikonen nedåtpil ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Klicka på ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) eller ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) för att flytta den anpassade principen för utgående skräp post uppåt eller nedåt i prioritets listan.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Använda tjänsten säkerhets & efterlevnad för att ta bort principer för utgående skräp post

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att expandera den anpassade princip som du vill ta bort (kolumnen **Type** är **anpassad princip för utgående skräp post**).

3. I den utökade principinformationen som visas klickar du på **Ta bort princip**.

4. Klicka på **Ja** i varningsrutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för utgående skräp post

Som du redan har beskrivit innehåller en utgående skräp post princip och en regel för utgående skräp post filter.

I Exchange Online PowerShell eller fristående EOP PowerShell är skillnaden mellan utgående filter principer för skräp post och filter regler för utgående e-post synlig. Du hanterar principer för utgående skräp post filter genom att använda cmdletarna **\* -HostedOutboundSpamFilterPolicy** och du hanterar utgående filter regler för skräp post genom att använda cmdlet **\* -HostedOutboundSpamFilterRule** .

- I PowerShell skapar du principen för utgående skräp post filter först och sedan skapar du regeln för utgående skräp post filter som identifierar den princip som regeln gäller för.
- I PowerShell ändrar du inställningarna för filtrering av skräp post filter och regeln för utgående skräp post filter separat.
- När du tar bort en regel för utgående skräp post från PowerShell tas den motsvarande filtret för skräp post filter inte bort automatiskt och vice versa.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Använda PowerShell för att skapa regler för utgående skräp post

Det är en process i två steg:

1. Skapa filtret för utgående skräp post.
2. Skapa filter regeln för utgående e-post som anger vilken regel för utgående skräp post som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny regel för utgående skräp post filter och koppla en befintlig, otilldelad filter princip för utgående e-post till den. En regel för utgående skräp post kan inte kopplas till fler än en utgående filter policy för skräp post.

- Du kan konfigurera följande inställningar på nya utgående filter principer för skräp post i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän efter att du har skapat principen:

  - Skapa den nya principen som inaktive rad (_aktive rad_ `$false` på **New-HostedOutboundSpamFilterRule-** cmdleten).
  - Ange prioriteten för principen när den skapas (_prioritet_ _\<Number\>_ ) på den **nya HostedOutboundSpamFilterRule-** cmdleten.

- En ny regel för utgående skräp post som du skapar i PowerShell visas inte i säkerhets & Compliance Center förrän du tilldelar principen till en skräp post filter.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Steg 1: använda PowerShell för att skapa en utgående filter policy för skräp post

Använd den här syntaxen om du vill skapa en regel för utgående skräp post filter:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas en ny regel för utgående skräp post som heter Contoso Executives med följande inställningar:

- Värdet för mottagarens hastighet är begränsat till lägre värden. Mer information finns i [Skicka begränsningar mellan Microsoft 365-alternativ](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- När en av gränserna nås förhindras användaren från att skicka meddelanden.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Steg 2: använda PowerShell för att skapa en regel för utgående skräp post filter

Om du vill skapa en regel för utgående skräp post använder du följande syntax:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

I det här exemplet skapas en ny regel för utgående skräp post som heter Contoso Executives med dessa inställningar:

- Filtret för utgående skräp post som heter Contoso-chefer är associerat med regeln.

- Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Detaljerad information om syntax och parametrar finns i [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Använda PowerShell för att visa filter principer för utgående e-post

Kör det här kommandot för att returnera en sammanfattande lista över alla filter principer för utgående e-post:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Använd den här syntaxen om du vill returnera detaljerad information om en viss regel för utgående skräp post filter:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

I det här exemplet returneras alla egenskaps värden för principen utgående skräp post filter med namnet chefer.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Använda PowerShell för att visa regler för utgående skräp post filter

Om du vill visa befintliga regler för skräp post filter använder du följande syntax:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Om du vill returnera en sammanfattnings lista över alla regler för utgående skräp post filter kör du det här kommandot:

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

Om du vill returnera detaljerad information om en viss regel för utgående skräp post filter använder du följande syntax:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

I det här exemplet returneras alla egenskaps värden för regel regeln för utgående e-post som heter Contoso-chefer.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Använda PowerShell för att ändra principer för utgående skräp post filter

Samma inställningar är tillgängliga när du ändrar en filter princip för skadlig kod i PowerShell som när du skapar principen enligt beskrivningen i [steg 1: använda PowerShell för att skapa en regel för utgående skräp post filter](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) tidigare i den här artikeln.

> [!NOTE]
> Du kan inte byta namn på en filter princip för utgående e-post (cmdleten **set-HostedOutboundSpamFilterPolicy** , saknar _namn_ parameter). När du byter namn på en utgående skräp post policy i säkerhets & Compliance Center byter du bara namn på _regeln_ för utgående skräp post filter.

Om du vill ändra en regel för utgående skräp post använder du följande syntax:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Använda PowerShell för att ändra regler för utgående skräp post filter

Den enda inställning som inte är tillgänglig när du ändrar en utgående regel för skräp post filter i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel. Information om hur du aktiverar eller inaktiverar befintliga regler för skräp post filter finns i nästa avsnitt.

Annars är inga ytterligare inställningar tillgängliga när du ändrar en utgående filter regel för skräp post i PowerShell. Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en regel för utgående skräp post filter](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) i den här artikeln.

Om du vill ändra en regel för utgående skräp post använder du följande syntax:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för utgående skräp post filter

När du aktiverar eller inaktiverar en regel för utgående skräp post i PowerShell aktive ras eller inaktive ras hela principen för utgående skräp post (regeln för utgående skräp post filter och den kopplade filter principen för utgående e-post). Du kan inte aktivera eller inaktivera standard principen för utgående skräp post (det gäller alltid alla mottagare).

Använd den här syntaxen om du vill aktivera eller inaktivera en regel för utgående skräp post filter i PowerShell:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

I det här exemplet inaktive ras filter regeln för utgående skräp post.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Aktivera-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) och [disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Använda PowerShell för att ställa in prioriteten för utgående skräp post filter

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Om du vill ange prioritet för en regel för utgående skräp post i PowerShell använder du följande syntax:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - Om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-HostedOutboundSpamFilterRule** cmdlet i stället.
>
> - Standard policyn för skräp post filter har ingen motsvarande filter regel för skräp post, och den har alltid det värde som är **lägst**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Använda PowerShell för att ta bort principer för skräp post filter

När du använder PowerShell för att ta bort en regel för utgående skräp post tas den motsvarande regeln för skräp post filter inte bort.

Använd den här syntaxen om du vill ta bort en regel för utgående skräp post i PowerShell:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

Det här exemplet tar bort filtret för utgående skräp post som heter marknadsförings avdelningen.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Använda PowerShell för att ta bort regler för utgående skräp post

När du använder PowerShell för att ta bort en regel för utgående skräp post tas inte motsvarande filter policy för utgående e-post bort.

Om du vill ta bort en regel för utgående skräp post i PowerShell använder du följande syntax:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

I det här exemplet tas regeln för utgående skräp post bort med namnet marknadsförings avdelning.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Mer information

[Ta bort blockerade användare från portalen med åtkomstbegränsade användare](removing-user-from-restricted-users-portal-after-spam.md)

[Pool med hög riskleverans för utgående meddelanden](high-risk-delivery-pool-for-outbound-messages.md)

[Vanliga frågor och svar om skydd mot skräppost](anti-spam-protection-faq.md)

[Rapporten Automatiskt vidarebefordrade meddelanden](mfi-auto-forwarded-messages-report.md)
