---
title: Konfigurera principer för skräppostfilter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om hur de visar, skapar, ändrar och tar bort principer för skräppostskydd i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78cfef52988e7da611edc0cc4d475e8a4624bc0e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879102"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Konfigurera principer för skräppostskydd i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor skyddas automatiskt inkommande e-postmeddelanden mot skräppost av EOP. EOP använder principer för skräppostskydd (kallas även för principer för skräppostfilter eller principer för innehållsfilter) som en del av organisationens övergripande försvar mot skräppost. Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för skräppostskydd. För mer detaljerad kontroll kan du också skapa egna principer för skräppostskydd som gäller för vissa användare, grupper eller domäner i din organisation. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera principer för skräppostskydd i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

De grundläggande delarna av en anti-spam-policy är:

- **Principen för skräppostfilter**: anger åtgärderna för utfall av skräppostfiltrering och aviseringsalternativen.
- **Regeln för skräppostfilter**: anger prioritets- och mottagarfilter (vem principen gäller för) för en princip för skräppostfilter.

Skillnaden mellan dessa två element är inte uppenbar när du hanterar principer för skräppostskydd i Microsoft 365 Defender-portalen:

- När du skapar en anti-spam policy skapar du faktiskt en spamfilterregel och tillhörande spamfilterpolicy samtidigt som du använder samma namn för båda.
- När du ändrar en anti-spam-policy ändrar inställningar relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagarfilter spamregeln. Alla andra inställningar ändrar den associerade principen för skräppostfilter.
- När du tar bort en anti-spam-policy tas spam-filterregeln och tillhörande spamfilterpolicy bort.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i [Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera avsnittet om antispampolicy](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) senare i det här ämnet.

Alla organisationer har en inbyggd princip för skräppostskydd som heter Standard och som har följande egenskaper:

- Principen tillämpas på alla mottagare i organisationen, även om det inte finns någon regel om skräppostfilter (mottagarfilter) associerade med policyn.
- Principen har det anpassade prioritetsvärdet **Lägsta** som du inte kan ändra (policyn tillämpas alltid sist). Alla anpassade policyer som du skapar har alltid högre prioritet.
- Politik är standardpolicyn (egenskapen **IsDefault** har värdet `True`) och du kan inte ta bort standardpolicyn.

Om du vill öka effektiviteten för filtrering av skräppost kan du skapa anpassade principer för skräppostskydd med striktare inställningar som tillämpas för vissa användare eller grupper av användare.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>. Om du vill gå direkt till sidan **Principer för skräppostskydd** använder du <https://security.microsoft.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill lägga till, ändra och ta bort principer för skräppostskydd måste du vara medlem i rollgruppen **Organisationshantering** eller **Säkerhetsadministratör**.
  - För skrivskyddad behörighet till principer för skräppostskydd måste du vara medlem i rollgruppen **Global läsare** eller **Säkerhetsläsare**.

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Anteckningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- De rekommenderade inställningarna för principer för skräppostskydd finns i avsnittet om [Inställningar för EOP-principer för skräppostskydd](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a>Använda Microsoft 365 Defender-portalen för att skapa principer för skräppostskydd

När du skapar en anpassad princip för skräppostskydd i Microsoft 365 Defender-portalen skapar du samtidigt regeln för skräppostfilter och den associerade principen för skräppostfilter med samma namn för båda två.

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skräppostskydd** klickar du på ikonen ![Skapa](../../media/m365-cc-sc-create-icon.png) **Skapa princip** och väljer sedan **Inkommande** i listrutan.

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

5. Konfigurera följande inställningar på sidan **Tröskel för massutskick och skräppostegenskaper**:

   - **Tröskel för massutskick**: Anger klagomålsnivån på massutskick (BCL) för ett meddelande som utlöser angiven åtgärd för skräppostfiltreringen **Massutskick** som du konfigurerar på nästa sida (större än det angivna värdet, inte större än eller lika med). Ett högre värde innebär att meddelandet är mindre önskvärt (mer troligt att det liknar skräppost). Standardvärdet är 7. Mer information finns i [Massklagomålsnivå (BCL) i EOP](bulk-complaint-level-values.md) och [Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     Som standard är PowerShell-inställningen _MarkAsSpamBulkMail_ `On` (På) i principer för skräppostskydd. Den här inställningen påverkar dramatiskt resultatet av filterbedömningen **Massutskick**:

     - **_MarkAsSpamBulkMail_ är På**: En BCL som är större än tröskelvärdet konverteras till en SCL 6 som motsvarar filterbedömningen **Skräppost**, och åtgärden för filterbedömningen **Massutskick** vidtas för meddelandet.
     - **_MarkAsSpamBulkMail_ är Av**: Meddelandet stämplas med BCL:n, men _ingen åtgärd_ vidtas för filterbedömningen **Massutskick**. I praktiken innebär det att tröskelvärdet för BCL och åtgärden för filterbedömningen **Massutskick** är irrelevanta.

   - **Öka skräppostpoäng**, **Markera som skräppost**<sup>\*</sup> och **Testläge**: Innehåller de ASF-inställningar (Advanced Spam Filter) som är inaktiverade som standard. ASF-inställningar håller på att fasas ut och deras funktioner läggs till i andra delar av filtreringsstacken. Vi rekommenderar att du låter alla dessa ASF-inställningar vara inaktiverade i dina principer för skräppostskydd.

     Mer information om inställningarna finns i artikeln om [inställningar för avancerat skräppostfilter (ASF) i EOP](advanced-spam-filtering-asf-options.md).

      <sup>\*</sup> **Innehåller specifika språk** och **från dessa länder** ingår inte i ASF-inställningarna.

   - **Innehåller specifika språk**: Klicka på rutan och välj **På** eller **Av** i listrutan. Om du aktiverar den visas en ruta. Börja skriva namnet på språket i rutan. En filtrerad lista över språk som stöds visas. När du hittar det språk du letar efter väljer du det. Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du ![ikonen Ta bort](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

   - **Från dessa länder** _: Klicka på rutan och välj *På** eller **Av** i listrutan. Om du aktiverar den visas en ruta. Börja skriva namnet på ett land i rutan. En filtrerad lista över länder som stöds visas. När du hittar landet du söker efter väljer du det. Upprepa det här steget så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du ![ikonen Ta bort](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

   Klicka på **Nästa** när du är klar.

6. På sidan **Åtgärder** som visas kan du konfigurera följande inställningar:

   - **Meddelandeåtgärder**: Välj eller granska åtgärden som ska vidtas för meddelanden baserat på följande bedömning av skräppostfiltreringen:
     - **Skräppost**
     - **Skräppost med hög konfidens**
     - **Nätfiske**
     - **Nätfiske med hög konfidens**
     - **Massutskick**

     Tillgängliga åtgärder för utfall av skräppostfiltrering beskrivs i följande tabell.

     - En bockmarkering ( ![Bockmarkering](../../media/checkmark.png)) anger att åtgärden är tillgänglig (alla åtgärder är inte tillgängliga för alla bedömningar av skräppostfiltrering).
     - En asterisk ( <sup>\*</sup> ) efter bockmarkeringen anger standardåtgärden för utfallet av skräppostfiltreringen.

     <br>

     ****

     |Åtgärd|Skräppost|Högsta<br>konfidens<br>skräppost|Fiske|Högsta<br>konfidens<br>fiske|Massutskick|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Flytta meddelandet till mappen skräppost**: Meddelandet levereras till postlådan och flyttas till mappen Skräppost.<sup>1</sup>|![Bockmarkering](../../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)<sup>\*</sup>|
     |**Lägg till X-rubrik**: Lägger till ett X-huvud i meddelandehuvudet och levererar meddelandet till postlådan. <p> Du anger fältnamnet för X-huvudet (inte värdet) senare i rutan **Lägg till följande X-sidhuvudtext**. <p> Om utfallet är **Skräppost** eller **Skräppost med hög konfidens** flyttas meddelandet till mappen Skräppost.<sup>1,2</sup>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)||![Bockmarkering](../../media/checkmark.png)<sup>\*</sup>|
     |**Lägg till text i ämnesraden**: Lägger till text i början av meddelandets ämnesrad. Meddelandet levereras till postlådan och flyttas till mappen Skräppost.<sup>1,2</sup> <p> Du anger texten senare i rutan **Lägg till den här texten i ämnesraden**.|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)||![Bockmarkering](../../media/checkmark.png)|
     |**Omdirigera meddelandet till e-postadressen**: Skickar meddelandet till andra mottagare istället för till avsedda mottagare. <p> Du anger mottagarna senare i rutan **Omdirigera till den här e-postadressen**.|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
     |**Ta bort meddelande**: Hela meddelandet tas tyst bort, inklusive alla bifogade filer.|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)||![Bockmarkering](../../media/checkmark.png)|
     |**Sätt meddelandet i karantän**: Skickar meddelandet till karantän istället för till avsedda mottagare. <p> Du anger senare hur länge meddelandet ska hållas kvar i karantänen i rutan **Karantän**.|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
     |**Ingen åtgärd**|||||![Bockmarkering](../../media/checkmark.png)|
     |

     > <sup>1</sup> I Exchange Online flyttas meddelandet till mappen Skräppost om regeln för skräppost har aktiverats för postlådan (den är aktiverad som standard). Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).
     >
     > I hybridmiljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).
     >
     > <sup>2</sup> Du kan använda det här värdet som ett villkor i e-postflödesregler för att filtrera eller dirigera meddelandet.

   - **Behåll skräppost i karantän för så här många dagar**: Anger hur lång tid meddelandet ska behållas i karantän om du har valt **Sätt meddelandet i karantän** som åtgärd för en bedömning av skräppostfiltreringen. När tidsperioden går ut tas meddelandet bort. Standardvärdet är 30 dagar. Giltiga värden är 1 till 30 dagar. Mer information om karantän finns i artiklarna om följande ämnen:

     - [Meddelanden i karantän i EOP](quarantine-email-messages.md)
     - [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)
     - [Hitta och släppa meddelanden i karantän som användare i EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Lägg till följande X-sidhuvudtext**: Den här rutan krävs och är endast tillgänglig om du har valt **Lägg till X-rubrik** som åtgärd för ett utfall av skräppostfiltreringen. Värdet du anger är *namnet* på huvudfältet som läggs till i meddelandehuvudet. Huvudfältets *värde* är alltid `This message appears to be spam` (Det här meddelandet verkar vara skräppost).

     Den maximala längden är 255 tecken och värdet får inte innehålla blanksteg eller kolon (:).

     Om du till exempel anger värdet `X-This-is-my-custom-header` är X-huvudet som läggs till i meddelandet `X-This-is-my-custom-header: This message appears to be spam.`

     Om du anger ett värde som innehåller blanksteg eller kolon (:) ignoreras det värde du anger och standardtexten för X-huvudet läggs till i meddelandet (`X-This-Is-Spam: This message appears to be spam.`).

   - **Lägg till den här texten i ämnesraden**: Den här rutan krävs och är endast tillgänglig om du har valt **Lägg till text i ämnesraden** som åtgärd för ett utfall av skräppostfiltreringen. Skriv texten som ska läggas till i början av meddelandets ämnesrad.

   - **Omdirigera till den här e-postadressen**: Den här rutan krävs och är endast tillgänglig om du har valt **Omdirigera meddelandet till e-postadressen** som åtgärd för ett utfall av skräppostfiltreringen. Ange den e-postadress dit du vill leverera meddelandet. Du kan ange flera värden avgränsade med semikolon (;).

   - **Aktivera säkerhetstips**: Säkerhetstips är aktiverade som standard, men du kan inaktivera dem genom att avmarkera kryssrutan. Mer information om säkerhetstips finns i [Säkerhetstips i e-postmeddelanden](safety-tips-in-office-365.md).

   - **Aktivera automatisk rensning**: Automatisk rensning identifierar och vidtar åtgärder för meddelanden som redan har levererats till Exchange Online-postlådor. Mer information finns i [Automatisk rensning – skydd mot skräppost och skadlig kod](zero-hour-auto-purge.md).

     Automatisk rensning är aktiverat som standard. Följande inställningar är tillgängliga när automatisk rensning är aktiverat:

     - **Aktivera automatisk rensning för nätfiskemeddelanden**: Automatisk rensning är aktiverat som standard för upptäckt av nätfiske, men du kan inaktivera det genom att avmarkera kryssrutan.
     - **Aktivera automatisk rensning för skräppostmeddelanden**: Automatisk rensning är aktiverat som standard för upptäckt av skräppost, men du kan inaktivera det genom att avmarkera kryssrutan.

   - **Aktivera skräppostaviseringar för slutanvändare**: Mer information finns i avsnittet [Konfigurera skräppostaviseringar för slutanvändare](#configure-end-user-spam-notifications) längre fram i det här ämnet.

   Klicka på **Nästa** när du är klar.

7. På utfällbara området **Tillståndslistor** som visas kan du konfigurera meddelandeavsändare efter e-postadress eller e-postdomän som får hoppa över skräppostfiltrering.

   I avsnittet **Tillåten** kan du konfigurera tillåtna avsändare och tillåtna domäner. I avsnittet **Blockerade** kan du lägga till blockerade avsändare och blockerade domäner.

   > [!IMPORTANT]
   >
   > Tänk efter noga innan du lägger till domäner på listan över tillåtna domäner. Mer information finns i [Skapa listor över betrodda avsändare i EOP](create-safe-sender-lists-in-office-365.md).
   >
   > Lägg aldrig till egna [godkända domäner](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) eller vanliga domäner (till exempel microsoft.com eller office.com) i listan över tillåtna domäner. Om de här domänerna tillåts kringgå skräppostfiltreringen kan du tillåta att attackerare enkelt skickar e-post till din organisation.
   >
   > Manuell blockering av domäner genom att lägga till domänerna på listan över blockerade domäner är inte farligt, men det kan öka mängden administrativt arbete. Mer information finns i artikeln om att [skapa listor över blockerade avsändare i EOP](create-block-sender-lists-in-office-365.md).
   >
   > Det kommer att finnas tillfällen när våra filter missar ett meddelande, du inte håller med om filterbedömningen eller det tar tid för våra system att komma ifatt det. I dessa fall är listan över listor för tillåtna och blockerade tillgängliga för att åsidosätta den aktuella filterbedömningen. Du bör använda dessa listor sparsamt och tillfälligt eftersom listor kan bli svåra att hantera, och vår filtreringsstack borde göra vad den ska göra. Men om du lägger till en domän i listan över tillåtna för en längre tid bör du be avsändaren att kontrollera att deras domän har autentiserats och ange den som DMARC-avvisa om den inte är det.

   Stegen för att lägga till poster i en av listorna är desamma:

   1. Klicka på länken för listan som du vill konfigurera:
      - **Tillåtna** \> **avsändare**: Klicka på **Hantera (nn) avsändare**.
      - **Tillåtna** \> **domäner**: Klicka på **Tillåt domäner**.
      - **Blockerade** \> **avsändare**: Klicka på **Hantera (nn) avsändare**.
      - **Blockerade** \> **domäner**: Klicka på **Blockera domäner**.

   2. Gör följande på den meny som visas:
      1. Klicka ![ikonen Skapa](../../media/m365-cc-sc-create-icon.png) **Lägg till avsändare** eller **Lägg till domäner**.
      2. Ange avsändarens e-postadress i rutan **Avsändare** eller domänen i rutan **Domän** i den utfällda menyn **Lägg till avsändare** eller **Lägg till domäner** som visas. Medan du skriver visas värdet under rutan. När du har skrivit klart e-postadressen eller domänen väljer du värdet under rutan.
      3. Upprepa föregående steg så många gånger det behövs. Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

      När du är klar klickar du på **Lägg till avsändare** eller **Lägg till domäner**.

      Åter på den utfällda huvudmenyn visas de avsändare eller domäner som du lade till på sidan. Gör följande steg om du vill ta bort en post från den här sidan:

      1. Markera en eller flera poster i listan. Du kan också använda rutan **Sök** för att hitta värden i listan.
      2. När du har valt minst en post visas ikonen Ta bort ![Ta bort-ikon](../../media/m365-cc-sc-delete-icon.png) visas.
      3. Klicka på ikonen Ta bort ![Ta bort-ikon](../../media/m365-cc-sc-delete-icon.png) om du vill ta bort alla de markerade posterna.

      Klicka på **Klar** när du är klar.

      Tillbaka på sidan **Tillåt och blockera lista** klickar du på **Nästa** när du är klar att fortsätta.

8. Granska inställningarna på sidan **Granska** som visas. Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.

   Klicka på **Skapa** när du är klar.

9. På bekräftelsesidan som visas klickar du på **Klar**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a>Använda Microsoft 365 Defender-portalen för att visa principer för skräppostskydd

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Princip för skräppostskydd** letar du efter något av följande värden:
   - Värdet **Typ** är **Anpassad princip för skräppost**
   - Värdet **Namn** är **Princip för inkommande skräppost (standard)**

   Följande egenskaper visas i listan över principer för skräppostskydd:

   - **Namn**
   - **Status**
   - **Prioritet**
   - **Typ**

3. När du väljer en princip för skräppostskydd genom att klicka på namnet visas principinställningarna i en utfälld meny.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a>Använda Microsoft 365 Defender-portalen för att modifiera principer för skräppostskydd

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skräppostskydd** väljer du en princip för skräppostskydd i listan genom att klicka på namnet:
   - En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.
   - Standardprincipen med namnet **Princip för inkommande skräppost (standard)**.

3. I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Mer information om inställningarna finns i föregående avsnittet [Använd Microsoft 365 Defender-portalen för att skapa principer för skräppostskydd](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) i den här artikeln.

   För standardprincipen för skräppostskydd är avsnittet **Tillämpas på** inte tillgängligt (principen tillämpas på alla), och du kan inte byta namn på principen.

Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.

### <a name="enable-or-disable-anti-spam-policies"></a>Aktivera eller inaktivera principer för skräppostskydd

Du kan inte inaktivera standardprincipen för skräppostskydd.

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Princip för skräppostskydd** väljer du en princip med **Typvärde** för **Anpassad princip för skräppostskydd** i listan genom att klicka på namnet.

3. Högst upp i den utfällda menyn principinformation ser du något av följande värden:
   - **Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .
   - **Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.

4. I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.

5. Klicka **Stäng** i den utfällda menyn principinformation.

Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Ange prioritet för anpassade principer för skräppostskydd

Som standard tilldelas principer för skräppostskydd en prioritet baserat på den ordning de har skapats i (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Defender-portalen). Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.

 **Anmärkningar**:

- I Microsoft 365 Defender-portalen kan du bara ändra prioriteten för principen för skräppostskydd efter att du har skapat den. I PowerShell kan du åsidosätta standardprioriteten när du skapar regeln för skräppostfilter (vilket kan påverka prioriteringen för befintliga regler).
- Anpassade principer för skräppostskydd visas i den ordning som de bearbetas (den första principen har värdet 0 för **Prioritet**). Standardprincipen för skräppostskydd har prioritetsvärdet **Lägsta** och du kan inte ändra det.

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skräppostskydd** väljer du en princip med **Typvärde** för **Anpassad princip för skräppostskydd** i listan genom att klicka på namnet.

3. Högst upp i den utfällda menyn principinformation som visas ser du **Öka prioritet** eller **Minska prioritet** baserat på det aktuella prioritetsvärdet och antalet anpassade principer:
   - Princip för skräppostskydd med värdet **Prioritet** **0** har bara alternativet **Minska prioritet** tillgängligt.
   - Princip för skräppostskydd med det lägsta värdet **Prioritet** (till exempel **3**) har bara alternativet **Öka prioritet** tillgängligt.
   - Om du har tre eller fler principer för skräppostskydd har principer mellan de högsta och lägsta prioritetsvärdena både alternativen **Öka prioritet** och **Minska prioritet** tillgängliga.

   Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.

4. Klicka **Stäng** i den utfällda menyn principinformation när du är klar.

### <a name="configure-end-user-spam-notifications"></a>Konfigurera skräppostaviseringar för slutanvändare

När ett utfall av skräppostfiltreringen sätter ett meddelande i karantän kan du konfigurera skräppostaviseringar för slutanvändare så att mottagare får veta vad som har hänt med meddelanden som skickats till dem. Mer information om aviseringarna finns i artikeln om [skräppostaviseringar för slutanvändare i EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skräppostskydd** väljer du en princip för skräppostskydd i listan genom att klicka på namnet:
   - En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.
   - Standardprincipen med namnet **Princip för inkommande skräppost (standard)**.

3. I den utfällda menyn principinformation som visas klickar du på **Redigera** i avsnittet **Åtgärder**. På den utfällda menyn **Åtgärder** som visas kan du konfigurera följande inställningar:

   - **Aktivera aviseringar om skräppost för slutanvändare**: Markera kryssrutan om du vill aktivera aviseringar eller rensa kryssrutan för att inaktivera aviseringar. När du markerar kryssrutan visas följande ytterligare inställningar:

     - **Skicka skräppostaviseringar till slutanvändare varje (dagar)**: Välj hur ofta aviseringar ska skickas. Standardvärdet är 3 dagar. Du kan ange 1 till 15 dagar.

       Det finns tre cykler för skräppostaviseringar för användare inom en 24-timmarsperiod som startar vid följande tidpunkter: 01:00 UTC, 08:00 UTC och 16:00 UTC.

       > [!NOTE]
       > Om vi missade en avisering under en tidigare cykel skickas aviseringen under nästföljande cykeln. Det här kan få det att verka som om flera aviseringar skickas ut samma dag.

     - **Språk**: Klicka på listrutan och välj ett tillgängligt språk i listan. Standardvärdet är **Standard**, vilket innebär engelska.

   Klicka på **Spara** när du är klar.

4. Tillbaka på utfällda menyn principinformation klickar du **Stäng**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a>Använda Microsoft 365 Defender-portalen för att ta bort anpassade principer för skräppostskydd

När du använder Microsoft 365 Defender-portalen för att ta bort en princip för anpassat skräppostskydd, tas både regeln för skräppostfilter och motsvarande princip för skräppostfilter bort. Du kan inte ta bort standardprincipen för skräppostskydd.

1. I Microsoft 365 Defender-portalen går du till **E-post och samarbete** \> **Principer och regler** \> **Principer för hot** \> **Principer** avdelning \> **Skräppostskydd**.

2. På sidan **Principer för skräppostskydd** väljer du en princip med **Typvärde** för **Anpassad princip för skräppostskydd** i listan genom att klicka på namnet. Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.

3. I bekräftelsedialogrutan som visas klickar du på **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för skräppostskydd

Som tidigare beskrivits består en anti-spam policy av en policy för spamfilter och en regel för spamfilter.

I Exchange Online PowerShell eller fristående EOP PowerShell är skillnaden mellan principer för skräppostfilter och regler för skräppostfilter uppenbar. Du hanterar principer för skräppostfilter genom att använda cmdletarna **\*-HostedContentFilterPolicy**, och du hanterar regler för skräppostfilter genom att använda cmdletarna **\*-HostedContentFilterRule**.

- I PowerShell skapar du först principen för skräppostfilter. Sedan skapar du regeln för skräppostfilter som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna för principen för skräppostfilter och regeln för skräppostfilter separat.
- När du tar bort en princip för skräppostfilter från PowerShell tas motsvarande regel för skräppostfilter inte automatiskt bort och tvärtom.

Följande inställningar för principer för skräppostskydd är endast tillgängliga i PowerShell:

- Parametern _MarkAsSpamBulkMail_ som är `On` (På) som standard. Effekterna av den här inställningen beskrevs i avsnittet [Använda Microsoft 365 Defender-portalen för att skapa principer för skräppostskydd](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) tidigare i den här artikeln.

- Följande inställningar för skräppostaviseringar för slutanvändare:
  - Parametern _DownloadLink_ som visar eller döljer länken till rapporteringsverktyget för skräppost för Outlook.
  - Parametern _EndUserSpamNotificationCustomSubject_ som du kan använda för att anpassa ämnesraden i aviseringen.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Använda PowerShell för att skapa principer för skräppostskydd

Du skapar en princip för skräppostskydd i PowerShell i två steg:

1. Skapa principen för skräppostfilter.
2. Skapa regeln för skräppostfilter som anger den princip för skräppostfilter som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny regel för skräppostfilter och tilldela en befintlig princip för skräppostfilter som inte har associerats till den. En regel för skräppostfilter kan inte associeras med fler än en princip för skräppostfilter.
- Du kan konfigurera följande inställningar på nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Microsoft 365 Defender-portalen förrän du har skapat principen:
  - Skapa den nya principen som inaktiverad (_Enabled_ `$false` i cmdleten **New-HostedContentFilterRule**).
  - Ange prioriteten för principen när du skapar den (_Priority_ _\<Number\>_) i cmdleten **New-HostedContentFilterRule**).

- En ny princip för skräppostfilter som du skapar i PowerShell är inte synlig i Microsoft 365 Defender-portalen förrän du tilldelar principen till en regel för skräppostfilter.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter

Om du vill skapa en princip för skräppostfilter använder du följande syntax:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas en princip för skräppostfilter med namnet Contoso Executives med följande inställningar:

- Karantänmeddelanden när utfallet av skräppostfiltreringen är skräppost eller skräppost med hög konfidens.
- BCL 7, 8 eller 9 utlöser åtgärden för filterbedömningen Massutskick.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter

Om du vill skapa en regel för skräppostfilter använder du följande syntax:

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

I det här exemplet skapas en ny regel för skräppostfilter med namnet Contoso Executives med följande inställningar:

- Principen för skräppostfilter med namnet Contoso Executives är associerad med regeln.
- Regeln gäller alla medlemmar i gruppen med namnet Contoso Executives Group.

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).

### <a name="use-powershell-to-view-spam-filter-policies"></a>Använda PowerShell för att visa principer för skräppostfilter

Om du vill returnera en sammanfattningslista över alla principer för skräppostfilter kör du följande kommando:

```PowerShell
Get-HostedContentFilterPolicy
```

Om du vill returnera detaljerad information om en specifik princip för skräppostfilter använder du följande syntax:

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

I det här exemplet returneras alla egenskapsvärden för principen för skräppostfilter med namnet Executives.

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

### <a name="use-powershell-to-view-spam-filter-rules"></a>Använda PowerShell för att visa regler för skräppostfilter

Om du vill visa befintliga regler för skräppostfilter använder du följande syntax:

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Om du vill returnera en sammanfattningslista över alla regler för skräppostfilter kör du följande kommando:

```PowerShell
Get-HostedContentFilterRule
```

Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

Om du vill returnera detaljerad information om en specifik regel för skräppostfilter använder du följande syntax:

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

I det här exemplet returneras alla egenskapsvärden för regeln för skräppostfilter princip med namnet Contoso Executives.

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Använda PowerShell för att ändra principer för skräppostfilter

Förutom följande objekt är samma inställningar tillgängliga när du ändrar en princip för skräppostfilter i PowerShell som när du skapar principen enligt beskrivningen i avsnittet [Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter](#step-1-use-powershell-to-create-a-spam-filter-policy) tidigare i den här artikeln.

- Switchparametern _MakeDefault_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid prioriteten **Lägsta** och du kan inte ta bort den) är endast tillgänglig när du ändrar en princip för skräppostfilter i PowerShell.
- Du kan inte byta namn på en princip för skräppostfilter (cmdleten **Set-HostedContentFilterPolicy** har ingen _Name_-parameter). När du byter namn på en princip för skräppostskydd i Microsoft 365 Defender-portalen byter du bara namn på _regeln_ för skräppostfiltret.

Om du vill ändra en princip för skräppostfilter använder du följande syntax:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Använda PowerShell för att ändra regler för skräppostfilter

Den enda inställningen som inte är tillgänglig när du ändrar en regel för skräppostfilter i PowerShell är parametern _Enabled_ som gör att du kan skapa en regel som är inaktiverad. Om du vill aktivera eller inaktivera befintliga regler för skräppostfilter läser du mer i nästa avsnitt.

Annars är inga ytterligare inställningar tillgängliga när du ändrar en regel för skräppostfilter i PowerShell. Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i avsnittet [Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter](#step-2-use-powershell-to-create-a-spam-filter-rule) tidigare i den här artikeln.

Om du vill ändra en regel för skräppostfilter använder du följande syntax:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

I det här exemplet får den befintliga regeln för skräppostfilter namnet `{Fabrikam Spam Filter}`.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för skräppostfilter

Om du aktiverar eller inaktiverar en regel för skräppostfilter i PowerShell aktiveras eller inaktiveras hela principen för skräppostfilter (regeln för skräppostfilter och den tilldelade principen för skräppostfilter). Du kan inte aktivera eller inaktivera standardprincipen för skräppostskydd (den tillämpas alltid på alla mottagare).

Om du vill aktivera eller inaktivera en regel för skräppostfilter i PowerShell använder du följande syntax:

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras regeln för skräppostfilter som heter Marketing Department.

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) och [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>Använda PowerShell för att ange prioriteten för regler för skräppostfilter

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Om du vill ange prioriteten för en regel för skräppostfilter i PowerShell använder du följande syntax:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**Anmärkningar**:

- Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-HostedContentFilterRule** istället.
- Standardprincipen för skräppostfilter har inte en motsvarande regel för skräppostfilter, och den har alltid prioritetsvärdet **Lägsta** som inte går att ändra.

### <a name="use-powershell-to-remove-spam-filter-policies"></a>Använda PowerShell för att ta bort principer för skräppostfilter

När du använder PowerShell för att ta bort en princip för skräppostfilter tas motsvarande regel för skräppostfilter inte bort.

Om du vill ta bort en princip för skräppostfilter i PowerShell använder du följande syntax:

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

I det här exemplet tas principen för skräppostfilter med namnet Marketing Department bort.

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).

### <a name="use-powershell-to-remove-spam-filter-rules"></a>Använda PowerShell för att ta bort regler för skräppostfilter

När du använder PowerShell för att ta bort en regel för skräppostfilter tas motsvarande princip för skräppostfilter inte bort.

Om du vill ta bort en regel för skräppostfilter i PowerShell använder du följande syntax:

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

I det här exemplet tas regeln för skräppostfilter med namnet Marketing Department bort.

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Skicka ett GTUBE-meddelande för att testa inställningarna för skräppostprinciperna

> [!NOTE]
> De här stegen fungerar bara om e-postorganisationen som du skickar GTUBE-meddelandet från inte söker igenom efter utgående skräppost. Om den söker igenom kan du inte skicka testmeddelandet.

GTUBE (Generic Test for Unsolicited Bulk Email – Generiskt test för oönskade massutskick) är en textsträng som du lägger till i ett test meddelande för att verifiera organisationens inställningar för skräppostskydd. Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.

Lägg till följande GTUBE text i ett e-postmeddelande på en enskild rad, utan blanksteg eller radbrytningar:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
