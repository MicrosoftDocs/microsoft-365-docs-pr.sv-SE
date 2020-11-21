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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om hur de visar, skapar, ändrar och tar bort principer för skräppostskydd i Exchange Online Protection (EOP).
ms.openlocfilehash: 34e0f3cf1ae382dcb256887557af18556d52a7df
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357893"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Konfigurera principer för skräppostskydd i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor skyddas automatiskt inkommande e-postmeddelanden mot skräppost av EOP. EOP använder principer för skräppostskydd (kallas även för principer för skräppostfilter eller principer för innehållsfilter) som en del av organisationens övergripande försvar mot skräppost. Mer information finns i [Skydd mot skräppost](anti-spam-protection.md).

Administratörer kan visa, redigera och konfigurera (men inte ta bort) standardprincipen för skräppostskydd. För mer detaljerad kontroll kan du också skapa egna principer för skräppostskydd som gäller för vissa användare, grupper eller domäner i din organisation. Anpassade principer har alltid företräde framför standardprincipen, men du kan ändra prioriteten (löpande ordning) för dina anpassade principer.

Du kan konfigurera principer för skräppostskydd i Säkerhets- och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

De grundläggande delarna av en anti-spam-policy är:

- **Principen för skräppostfilter**: anger åtgärderna för utfall av skräppostfiltrering och aviseringsalternativen.
- **Regeln för skräppostfilter**: anger prioritets- och mottagarfilter (vem principen gäller för) för en princip för skräppostfilter.

Skillnaden mellan dessa två element är inte uppenbar när du hanterar principer för skräppostskydd i Säkerhets- och efterlevnadscenter:

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

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:

  - Om du vill lägga till, ändra och ta bort skydd mot skräppost måste du vara medlem i någon av följande rollgrupper:

    - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - För skrivskyddad behörighet till principer för skräppostskydd måste du vara medlem i någon av följande rollgrupper:

    - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
    - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- De rekommenderade inställningarna för skräppostprinciper finns i avsnittet om [inställningar för EOP-principer för skräppostskydd](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd

När du skapar en anpassad princip för skräppostskydd i Säkerhets- och efterlevnadscenter skapar du samtidigt en regel för skräppostfilter och den associerade principen för skräppostfilter med samma namn för båda två.

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräppostskydd** klickar du på **Skapa en princip**.

3. I den utfällbara rutan **Ny princip för skräppostfilter** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn på principen. Använd inte följande tecken: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.

      Om du tidigare har skapat principer för skräppostskydd i administrationscenter för Exchange (EAC) som innehåller dessa tecken bör du byta namn på principen för skräppostskydd i PowerShell. Instruktioner finns i avsnittet [Använda PowerShell för att ändra regler för skräppostfilter](#use-powershell-to-modify-spam-filter-rules) längre ner i den här artikeln.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

4. (Valfritt) Utöka avsnittet **Åtgärder för skräppost och massutskick** och verifiera eller konfigurera följande inställningar:

   - **Välj vad som ska göras med skräppost och massutskick**: Välj eller granska åtgärden som ska vidtas för meddelanden baserat på följande utfall av skräppostfiltreringen:

     - **Skräppost**
     - **Skräppost med hög konfidens**
     - **Nätfiske-e-post**
     - **Nätfiske via e-post med hög konfidens**
     - **Massutskick**

     Tillgängliga åtgärder för utfall av skräppostfiltrering beskrivs i följande tabell.

     - En bockmarkering ( ![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) anger att åtgärden är tillgänglig (alla åtgärder är inte tillgängliga för alla utfall av skräppostfiltrering).
     - En asterisk ( <sup>\*</sup> ) efter bockmarkeringen anger standardåtgärden för utfallet av skräppostfiltreringen.

     ****

     |Åtgärd|Skräppost|Högsta<br/>konfidens<br/>skräppost|Fiske<br/>e-post|Högsta<br/>konfidens<br/>fiske<br/>e-post|Massutskick<br/>e-post|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Flytta meddelandet till mappen skräppost**: Meddelandet levereras till postlådan och flyttas till mappen Skräppost.<sup>1</sup>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**Lägg till X-rubrik**: Lägger till ett X-huvud i meddelandehuvudet och levererar meddelandet till postlådan. <p> Du anger fältnamnet för X-huvudet (inte värdet) senare i rutan **Lägg till följande X-sidhuvudtext**. <p> Om utfallet är **Skräppost** eller **Skräppost med hög konfidens** flyttas meddelandet till mappen Skräppost.<sup>1,2</sup>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**Lägg till text i ämnesraden**: Lägger till text i början av meddelandets ämnesrad. Meddelandet levereras till postlådan och flyttas till mappen Skräppost.<sup>1,2</sup> <p> Du anger texten senare i rutan **Lägg till den här texten i ämnesraden**.|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Omdirigera meddelandet till e-postadressen**: Skickar meddelandet till andra mottagare istället för till avsedda mottagare. <p> Du anger mottagarna senare i rutan **Omdirigera till den här e-postadressen**.|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Ta bort meddelande**: Hela meddelandet tas tyst bort, inklusive alla bifogade filer.|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Sätt meddelandet i karantän**: Skickar meddelandet till karantän istället för till avsedda mottagare. <p> Du anger senare hur länge meddelandet ska hållas kvar i karantänen i rutan **Karantän**.|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Ingen åtgärd**|||||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     <sup>1</sup> I Exchange Online flyttas meddelandet till mappen Skräppost om regeln för skräppost har aktiverats för postlådan (den är aktiverad som standard). Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).

     I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

     <sup>2</sup> Du kan använda det här värdet som ett villkor i e-postflödesregler (kallas även transportregler) för att filtrera eller dirigera meddelandet.

   - **Välj tröskelvärde**: Anger klagomålsnivån på massutskick (BCL) för ett meddelande som utlöser angiven åtgärd för utfallet **Massutskick** av skräppostfiltreringen (större än det angivna värdet, inte större än eller lika med). Ett högre värde innebär att meddelandet är mindre önskvärt (mer troligt att det liknar skräppost). Standardvärdet är 7. Mer information finns i [Massklagomålsnivå (BCL) i EOP](bulk-complaint-level-values.md) och [Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     Som standard är PowerShell-inställningen _MarkAsSpamBulkMail_ `On` (På) i principer för skräppostskydd. Den här inställningen påverkar dramatiskt resultatet av filtreringsutfallet **Massutskick**:

     - **_MarkAsSpamBulkMail_ är på**: En BCL som är större än tröskelvärdet konverteras till en SCL 6 som motsvarar filtreringsutfallet **Skräppost**, och åtgärden för filtreringsutfallet **Massutskick** vidtas för meddelandet.

     - **_MarkAsSpamBulkMail_ är av**: Meddelandet stämplas med BCL:n, men _ingen åtgärd_ vidtas för filtreringsutfallet **Massutskick**. I praktiken innebär det att BCL-tröskelvärdet och åtgärden för filtreringsutfallet **Massutskick** är irrelevanta.

   - **Karantän**: Anger hur lång tid meddelandet ska behållas i karantän om du har valt **Sätt meddelandet i karantän** som åtgärd för ett utfall av skräppostfiltreringen. När tidsperioden går ut tas meddelandet bort. Standardvärdet är 30 dagar. Giltiga värden är 1 till 30 dagar. Mer information om karantän finns i artiklarna om följande ämnen:

     - [Meddelanden i karantän i EOP](quarantine-email-messages.md)
     - [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)
     - [Hitta och släppa meddelanden i karantän som användare i EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Lägg till följande X-sidhuvudtext**: Den här rutan krävs och är endast tillgänglig om du har valt **Lägg till X-rubrik** som åtgärd för ett utfall av skräppostfiltreringen. Värdet du anger är *namnet* på huvudfältet som läggs till i meddelandehuvudet. Huvudfältets *värde* är alltid `This message appears to be spam` (Det här meddelandet verkar vara skräppost).

     Den maximala längden är 255 tecken och värdet får inte innehålla blanksteg eller kolon (:).

     Om du till exempel anger värdet `X-This-is-my-custom-header` är X-huvudet som läggs till i meddelandet `X-This-is-my-custom-header: This message appears to be spam.`

     Om du anger ett värde som innehåller blanksteg eller kolon (:) ignoreras det värde du anger och standardtexten för X-huvudet läggs till i meddelandet (`X-This-Is-Spam: This message appears to be spam.`).

   - **Lägg till den här texten i ämnesraden**: Den här rutan krävs och är endast tillgänglig om du har valt **Lägg till text i ämnesraden** som åtgärd för ett utfall av skräppostfiltreringen. Skriv texten som ska läggas till i början av meddelandets ämnesrad.

   - **Omdirigera till den här e-postadressen**: Den här rutan krävs och är endast tillgänglig om du har valt **Omdirigera meddelandet till e-postadressen** som åtgärd för ett utfall av skräppostfiltreringen. Ange den e-postadress dit du vill leverera meddelandet. Du kan ange flera värden avgränsade med semikolon (;).

   - **Säkerhetstips**: Säkerhetstips är aktiverade som standard, men du kan inaktivera dem genom att avmarkera kryssrutan **På**. Mer information om säkerhetstips finns i [Säkerhetstips i e-postmeddelanden](safety-tips-in-office-365.md).

   Inställningar för **Automatisk rensning**: Automatisk rensning identifierar och vidtar åtgärder för meddelanden som redan har levererats till Exchange Online-postlådor. Mer information om automatisk rensning finns i [Automatisk rensning – skydd mot skräppost och skadlig kod](zero-hour-auto-purge.md).

   - **Automatisk rensning av skräppost**: Automatisk rensning är aktiverat som standard för upptäckt av skräppost, men du kan inaktivera det genom att avmarkera kryssrutan **På**.

   - **Automatisk rensning av nätfiske**: Automatisk rensning är aktiverat som standard för upptäckt av nätfiske, men du kan inaktivera det genom att avmarkera kryssrutan **På**.

5. (Valfritt) Utöka avsnittet **Tillståndslistor** om du vill konfigurera meddelandeavsändare efter e-postadress eller e-postdomän som får hoppa över skräppostfiltrering:

   > [!CAUTION]
   >
   > - Tänk efter noga innan du lägger till domäner här. Mer information finns i [Skapa listor över betrodda avsändare i EOP](create-safe-sender-lists-in-office-365.md).
   >
   > - Lägg aldrig till godkända domäner (domäner som du äger) eller vanliga domäner (till exempel microsoft.com eller office.com) i listan över tillåtna domäner. Då skulle angripare kunna skicka e-post till din organisation som kringgår skräppostfiltreringen.

   - **Tillåt avsändare**: Klicka på **Redigera**. I den utfällbara rutan **Lista över tillåtna avsändare** som visas gör du följande:

      a. Ange avsändarens e-postadress. Du kan ange flera e-postadresser avgränsade med semikolon (;).

      b. Klicka på ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) och lägg till avsändarna.

      Upprepa de här stegen så många gånger det behövs.

      Avsändarna du har lagt till visas i avsnittet **Tillåten avsändare** i den utfällbara rutan. Om du vill ta bort en avsändare klickar du på ![ikonen Ta bort](../../media/scc-remove-icon.png).

      Klicka på **Spara** när du är klar.

   - **Tillåt domän**: Klicka på **Redigera**. I den utfällbara rutan **Lista över tillåtna domäner** som visas gör du följande steg:

      a. Ange domänen. Du kan ange flera domäner avgränsade med semikolon (;).

      b. Klicka på ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) och lägg till domänerna.

      Upprepa de här stegen så många gånger det behövs.

      Domänerna du har lagt till visas i avsnittet **Tillåten domän** i den utfällbara rutan. Om du vill ta bort en domän klickar du på ![ikonen Ta bort](../../media/scc-remove-icon.png).

      Klicka på **Spara** när du är klar.

6. (Valfritt) Utöka avsnittet **Blockeringslistor** om du vill konfigurera meddelandeavsändare efter e-postadress eller e-postdomän som alltid ska markeras som skräppost med hög konfidens:

   > [!NOTE]
   > Manuell blockering av domäner är inte farligt, men det kan öka mängden administrativt arbete. Mer information finns i artikeln om att [skapa listor över blockerade avsändare i EOP](create-block-sender-lists-in-office-365.md).

   - **Blockera avsändare**: Klicka på **Redigera**. I den utfällbara rutan **Lista över blockerade avsändare** som visas gör du följande steg:

      a. Ange avsändarens e-postadress. Du kan ange flera e-postadresser avgränsade med semikolon (;). Jokertecken (*) är inte tillåtna.

      b. Klicka på ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) och lägg till avsändarna.

      Upprepa de här stegen så många gånger det behövs.

      Avsändarna du har lagt till visas i avsnittet **Blockerad avsändare** i den utfällbara rutan. Om du vill ta bort en avsändare klickar du på ![knappen Ta bort](../../media/scc-remove-icon.png).

      Klicka på **Spara** när du är klar.

   - **Blockera domän**: Klicka på **Redigera**. I den utfällbara rutan **Lista över blockerade domäner** som visas gör du följande:

      a. Ange domänen. Du kan ange flera domäner avgränsade med semikolon (;). Jokertecken (*) är inte tillåtna.

      b. Klicka på ![Ikonen Lägg till](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) och lägg till domänerna.

      Upprepa de här stegen så många gånger det behövs.

      Domänerna du har lagt till visas i listan **Blockerad domän** i den utfällbara rutan. Om du vill ta bort en domän klickar du på ![knappen Ta bort](../../media/scc-remove-icon.png).

      Klicka på **Spara** när du är klar.

7. (Valfritt) Utöka avsnittet **Internationell skräppost** om du vill konfigurera e-postspråk eller källänder som blockeras av skräppostfiltrering:

   - **Filtrera e-postmeddelanden skrivna på följande språk**: Den här inställningen är inaktiverad som standard (**Status: AV**). Klicka på **Redigera**. I den utfällbara rutan **Inställningar för internationell skräppost** som visas konfigurerar du följande inställningar:

     - **Filtrera e-postmeddelanden skrivna på följande språk**: Markera kryssrutan om du vill aktivera den här inställningen. Avmarkera kryssrutan om du vill inaktivera inställningen.

     - Klicka i rutan och börja skriva *namnet* på språket. En filtrerad lista över språk som stöds visas, tillsammans med motsvarande ISO 639-2-språkkod. När du hittar det språk du letar efter väljer du det. Upprepa det här steget så många gånger det behövs.

       Listan över språk som du har valt visas i den utfällbara rutan. Om du vill ta bort ett språk klickar du ![Knappen Ta bort](../../media/scc-remove-icon.png).

     Klicka på **Spara** när du är klar.

   - **Filtrera e-postmeddelanden skickade från följande länder eller regioner**: Den här inställningen är inaktiverad som standard (**Status: AV**). Om du vill aktivera den klickar du på **Redigera**. I den utfällbara rutan **Inställningar för internationell skräppost** som visas konfigurerar du följande inställningar:

     - **Filtrera e-postmeddelanden skickade från följande länder eller regioner**: Markera kryssrutan om du vill aktivera den här inställningen. Avmarkera kryssrutan om du vill inaktivera inställningen.

     - Klicka i rutan och börja skriva *namnet* på landet eller regionen. En filtrerad lista över länder och regioner som stöds visas, tillsammans med motsvarande ISO 3166-1-landskod med två bokstäver. När du hittar landet eller regionen du söker efter väljer du det. Upprepa det här steget så många gånger det behövs.

       Listan över länder som du har valt visas i den utfällbara rutan. Om du vill ta bort ett land eller en region klickar du på ![Knappen Ta bort](../../media/scc-remove-icon.png).

     Klicka på **Spara** när du är klar.

8. Det valfria avsnittet **Egenskaper för skräppost** innehåller inställningar för avancerat skräppostfilter (ASF) som är inaktiverade som standard. ASF-inställningar håller på att fasas ut och deras funktioner läggs till i andra delar av filtreringsstacken. Vi rekommenderar att du låter alla dessa ASF-inställningar vara inaktiverade i dina principer för skräppostskydd.

   Mer information om inställningarna finns i artikeln om [inställningar för avancerat skräppostfilter (ASF) i EOP](advanced-spam-filtering-asf-options.md).

9. (Obligatoriskt) Utöka avsnittet **Tillämpas på** och ange vilka interna mottagare som principen gäller för.

    Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

    Det är enklast att klicka på **Lägg till ett villkor** tre gånger för att visa alla tillgängliga villkor. Om du vill ta bort villkor som du inte vill konfigurera kan du klicka på ![knappen Ta bort](../../media/scc-remove-icon.png).

    - **Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation. Klicka i rutan **Lägg till en tagg** om du vill visa och välja en domän. Klicka igen i rutan **Lägg till en tagg** och välj fler domäner om fler än en domän är tillgänglig.

    - **Mottagaren är**: Anger en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen. Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan. Klicka igen i rutan **Lägg till en tagg** om du vill välja fler mottagare.

    - **Mottagaren är medlem i**: Anger en eller flera grupper i organisationen. Klicka i rutan **Lägg till en tagg** och börja skriva för att filtrera listan. Klicka igen i rutan **Lägg till en tagg** om du vill välja fler mottagare.

    - **Förutom om**: Om du vill lägga till undantag för regeln klickar du på **Lägg till ett villkor** tre gånger, så visas alla tillgängliga undantag. Inställningarna och beteendet är likadana som villkoren.

10. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>Använda Säkerhets- och efterlevnadscenter för att visa principer för skräppostskydd

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:

   - Standardprincipen med namnet **Standardprincip för skräppostfilter**.

   - En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.

3. De viktiga principinställningarna visas i den utökade principinformationen som visas. Visa mer information genom att klicka på **Redigera princip**.

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>Använda Säkerhets- och efterlevnadscenter för att ändra principer för skräppostskydd

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:

   - Standardprincipen med namnet **Standardprincip för skräppostfilter**.

   - En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.

3. Klicka på **Redigera princip**.

För anpassade principer för skräppostskydd är de tillgängliga inställningarna i den utfällbara rutan som visas identiska med de som beskrivs i avsnittet [Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd](#use-the-security--compliance-center-to-create-anti-spam-policies).

För standardprincipen för skräppostskydd med namnet **Standardprincip för skräppostfilter** är avsnittet **Tillämpas på** inte tillgängligt (principen tillämpas på alla), och du kan inte byta namn på principen.

Läs mer i följande avsnitt om du vill aktivera eller inaktivera en princip, ange prioritetsordningen för principerna eller konfigurera karantänaviseringar för slutanvändare.

### <a name="enable-or-disable-anti-spam-policies"></a>Aktivera eller inaktivera principer för skräppostskydd

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas en anpassad princip som du har skapat (värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**).

3. Kontrollera värdet i kolumnen **På** i den utökade principinformationen som visas.

   Flytta växlingsknappen åt vänster om du vill inaktivera principen: ![Växlingsknapp inaktiverad](../../media/scc-toggle-off.png)

   Flytta växlingsknappen åt höger om du vill aktivera principen: ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

Du kan inte inaktivera standardprincipen för skräppostskydd.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Ange prioritet för anpassade principer för skräppostskydd

Som standard tilldelas principer för skräppostskydd en prioritet baserat på den ordning de har skapats i (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Anpassade principer för skräppostskydd visas i den ordning som de bearbetas (den första principen har värdet 0 för **Prioritet**). Standardprincipen för skräppostskydd med namnet **Standardprincip för skräppostfilter** har prioritetsvärdet **Lägsta**, och du kan inte ändra det.

 **Obs**! I Säkerhets- och efterlevnadscenter kan du bara ändra prioriteten för principen för skräppostskydd efter att du har skapat den. I PowerShell kan du åsidosätta standardprioriteten när du skapar regeln för skräppostfilter (vilket kan påverka prioriteringen för befintliga regler).

Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräppostskydd** hittar du principerna där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**. Kontrollera värdena i kolumnen **Prioritet**:

   - Den anpassade principen för skräppostskydd med den högsta prioriteten har värdet ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Den anpassade principen för skräppostskydd med den lägsta prioriteten har värdet ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) **n** (till exempel ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) **3**.)

   - Om du har tre eller fler anpassade principer för skräppostskydd har principerna mellan den högsta och lägsta prioriteten värdena ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png)![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **n** (till exempel ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png)![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Klicka på ![ikonen Uppåtpil](../../media/ITPro-EAC-UpArrowIcon.png) eller ![ikonen Nedåtpil](../../media/ITPro-EAC-DownArrowIcon.png) om du vill flytta den anpassade principen för skräppostskydd uppåt eller nedåt i prioritetslistan.

### <a name="configure-end-user-spam-notifications"></a>Konfigurera skräppostaviseringar för slutanvändare

När ett utfall av skräppostfiltreringen sätter ett meddelande i karantän kan du konfigurera skräppostaviseringar för slutanvändare så att mottagare får veta vad som har hänt med meddelanden som skickats till dem. Mer information om aviseringarna finns i artikeln om [skräppostaviseringar för slutanvändare i EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas principen för skräppostskydd:

   - Standardprincipen med namnet **Standardprincip för skräppostfilter**.

   - En anpassad princip som du har skapat där värdet i kolumnen **Typ** är **Anpassad princip för skräppostskydd**.

3. I den utökade principinformationen som visas klickar du på **Konfigurera skräppostaviseringar för slutanvändare**.

4. Konfigurera följande inställningar i dialogrutan **\<Policy Name\>** som öppnas:

   - **Aktivera aviseringar om skräppost för slutanvändare**: Markera kryssrutan om du vill aktivera aviseringar. Avmarkera kryssrutan om du vill inaktivera aviseringar.

   - **Skicka skräppostaviseringar till slutanvändare varje (dagar)**: Välj hur ofta aviseringar ska skickas. Standardvärdet är 3 dagar. Du kan ange 1 till 15 dagar.

     Det finns tre cykler för skräppostaviseringar för användare inom en 24-timmarsperiod som startar vid följande tidpunkter: 01:00 UTC, 08:00 UTC och 16:00 UTC.

     > [!NOTE]
     > Om vi missade en avisering under en tidigare cykel skickas aviseringen under nästföljande cykeln. Det här kan få det att verka som om flera aviseringar skickas ut samma dag.

   - **Aviseringsspråk**: Klicka på listrutan och välj ett tillgängligt språk i listan. Standardvärdet är **Standard**, vilket innebär engelska.

   Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>Använda Säkerhets- och efterlevnadscenter för att ta bort principer för skräppostskydd

1. I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.

2. På sidan **Inställningar för skräppostskydd** klickar du på ![ikonen Visa](../../media/scc-expand-icon.png), så visas den anpassade principen du vill ta bort (kolumnen **Typ** har värdet **Anpassad princip för skräppostskydd**).

3. I den utökade principinformationen som visas klickar du på **Ta bort princip**.

4. Klicka på **Ja** i varningsrutan som visas.

Du kan inte ta bort standardprincipen.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för skräppostskydd

Som tidigare beskrivits består en anti-spam policy av en policy för spamfilter och en regel för spamfilter.

I Exchange Online PowerShell eller fristående EOP PowerShell är skillnaden mellan principer för skräppostfilter och regler för skräppostfilter uppenbar. Du hanterar principer för skräppostfilter genom att använda cmdletarna **\*-HostedContentFilterPolicy**, och du hanterar regler för skräppostfilter genom att använda cmdletarna **\*-HostedContentFilterRule**.

- I PowerShell skapar du först principen för skräppostfilter. Sedan skapar du regeln för skräppostfilter som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna för principen för skräppostfilter och regeln för skräppostfilter separat.
- När du tar bort en princip för skräppostfilter från PowerShell tas motsvarande regel för skräppostfilter inte automatiskt bort och tvärtom.

Följande inställningar för principer för skräppostskydd är endast tillgängliga i PowerShell:

- Parametern _MarkAsSpamBulkMail_ som är `On` (På) som standard. Effekterna av den här inställningen beskrevs i avsnittet [Använda Säkerhets- och efterlevnadscenter för att skapa principer för skräppostskydd](#use-the-security--compliance-center-to-create-anti-spam-policies) tidigare i den här artikeln.

- Följande inställningar för skräppostaviseringar för slutanvändare:

  - Parametern _DownloadLink_ som visar eller döljer länken till rapporteringsverktyget för skräppost för Outlook.

  - Parametern _EndUserSpamNotificationCustomSubject_ som du kan använda för att anpassa ämnesraden i aviseringen.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Använda PowerShell för att skapa principer för skräppostskydd

Du skapar en princip för skräppostskydd i PowerShell i två steg:

1. Skapa principen för skräppostfilter.
2. Skapa regeln för skräppostfilter som anger den princip för skräppostfilter som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny regel för skräppostfilter och tilldela en befintlig princip för skräppostfilter som inte har associerats till den. En regel för skräppostfilter kan inte associeras med fler än en princip för skräppostfilter.

- Du kan konfigurera följande inställningar i nya principer för skräppostfilter i PowerShell som inte är tillgängliga i Säkerhets- och efterlevnadscenter förrän du har skapat principen:

  - Skapa den nya principen som inaktiverad (_Enabled_ `$false` i cmdleten **New-HostedContentFilterRule**).
  - Ange prioriteten för principen när du skapar den (_Priority_ _\<Number\>_) i cmdleten **New-HostedContentFilterRule**).

- En ny princip för skräppostfilter som du skapar i PowerShell är inte synlig i Säkerhets- och efterlevnadscenter förrän du tilldelar principen till en regel för skräppostfilter.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter

Om du vill skapa en princip för skräppostfilter använder du följande syntax:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

I det här exemplet skapas en princip för skräppostfilter med namnet Contoso Executives med följande inställningar:

- Karantänmeddelanden när utfallet av skräppostfiltreringen är skräppost eller skräppost med hög konfidens.

- BCL 6 utlöser åtgärden för filtreringsutfallet Massutskick.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-HostedContentFilterPolicy** och **Set-HostedContentFilterPolicy** innehåller en äldre _ZapEnabled_-parameter, samt nyare _PhishZapEnabled_- och _SpamZapEnabled_-parametrar. Parametern _ZapEnabled_ blev inaktuell i februari 2020. Parametrarna _PhishZapEnabled_ och _SpamZapEnabled_ brukade ärva sina värden från parametern _ZapEnabled_. Men om du använder parametrarna _PhishZapEnabled_ och _SpamZapEnabled_ i ett kommando eller om du använder inställningarna för **Automatisk rensning av skräppost** eller **Automatisk rensning av nätfiske** i principen för skräppostskydd i Säkerhets- och efterlevnadscentret ignoreras värdet för parametern _ZapEnabled_. Använd med andra ord inte parametern _ZapEnabled_. Använd istället parametrarna _PhishZapEnabled_ och _SpamZapEnabled_.

Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).

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

Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).

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

Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).

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

Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Använda PowerShell för att ändra principer för skräppostfilter

Förutom följande objekt är samma inställningar tillgängliga när du ändrar en princip för skräppostfilter i PowerShell som när du skapar principen enligt beskrivningen i avsnittet [Steg 1: Använd PowerShell för att skapa en princip för skräppostfilter](#step-1-use-powershell-to-create-a-spam-filter-policy) tidigare i den här artikeln.

- Switchparametern _MakeDefault_ som omvandlar den angivna principen till standardprincipen (tillämpas på alla, alltid prioriteten **Lägsta** och du kan inte ta bort den) är endast tillgänglig när du ändrar en princip för skräppostfilter i PowerShell.

- Du kan inte byta namn på en princip för skräppostfilter (cmdleten **Set-HostedContentFilterPolicy** har ingen _Name_-parameter). När du byter namn på en princip för skräppostskydd i Säkerhets- och efterlevnadscenter byter du bara namn på _regeln_ för skräppostfiltret.

Om du vill ändra en princip för skräppostfilter använder du följande syntax:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Använda PowerShell för att ändra regler för skräppostfilter

Den enda inställningen som inte är tillgänglig när du ändrar en regel för skräppostfilter i PowerShell är parametern _Enabled_ som gör att du kan skapa en regel som är inaktiverad. Om du vill aktivera eller inaktivera befintliga regler för skräppostfilter läser du mer i nästa avsnitt.

Annars är inga ytterligare inställningar tillgängliga när du ändrar en regel för skräppostfilter i PowerShell. Samma inställningar är tillgängliga när du skapar en regel enligt beskrivningen i avsnittet [Steg 2: Använd PowerShell för att skapa en regel för skräppostfilter](#step-2-use-powershell-to-create-a-spam-filter-rule) tidigare i den här artikeln.

Om du vill ändra en regel för skräppostfilter använder du följande syntax:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

I det här exemplet ändras namnet på den befintliga regeln för skräppostfilter som heter `{Fabrikam Spam Filter}` som kan orsaka problem i Säkerhets- och efterlevnadscenter.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).

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

Detaljerad information om syntax och parametrar finns i [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) och [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).

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

Detaljerad information om syntax och parametrar finns i [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).

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

Detaljerad information om syntax och parametrar finns i [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Skicka ett GTUBE-meddelande för att testa inställningarna för skräppostprinciperna

> [!NOTE]
> De här stegen fungerar bara om e-postorganisationen som du skickar GTUBE-meddelandet från inte söker igenom efter utgående skräppost. Om organisationen söker igenom går det inte att skicka testmeddelandet.

GTUBE (Generic Test for Unsolicited Bulk Email – Generiskt test för oönskade massutskick) är en textsträng som du lägger till i ett test meddelande för att verifiera organisationens inställningar för skräppostskydd. Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.

Lägg till följande GTUBE text i ett e-postmeddelande på en enskild rad, utan blanksteg eller radbrytningar:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>Listor över blockerade eller tillåtna

Det kommer att finnas tillfällen när våra filter missar meddelandet eller då det tar tid för våra system att komma ifatt det. I de här fallen har principen för skräppostskydd en lista över Tillåtna och en lista över Blockerade tillgängliga för att åsidosätta den aktuella bedömningen. Det här alternativet ska bara användas sparsamt eftersom listor kan bli svåra att hantera, och bara tillfälligt eftersom vår filtreringsstack borde göra vad den ska göra.

> [!TIP]
> Det kan finnas situationer där din organisation kanske inte håller med om den bedömning tjänsten tillhandahåller. I det här fallet kanske du vill behålla listan över tillåtna eller blockerade permanent. Men om du kommer att lägga till en domän i listan över tillåtna för en längre tid bör du be avsändaren att kontrollera att avsändarens domän har autentiserats och ange den som DMARC-avvisa (reject) om den inte är det.
