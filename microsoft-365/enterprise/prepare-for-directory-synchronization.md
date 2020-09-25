---
title: Förbereda för Active Directory-synkronisering till Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Här beskrivs hur du förbereder användare till Microsoft 365 med hjälp av profilsynkronisering och de långsiktiga fördelarna med den här metoden.
ms.openlocfilehash: c9d4368d1939b9c6feedf5146f9d168f18d5d5b1
ms.sourcegitcommit: 96b4593becc9450af136c528844e858c6e88b5a9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269423"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Förbereda för Active Directory-synkronisering till Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Fördelarna med hybrid identitet och katalog synkronisering i din organisation inkluderar:

- Reducera administrativa program i organisationen
- Om du vill aktivera enkel inloggnings scenario
- Automatisera konto ändringar i Microsoft 365

Mer information om fördelarna med att använda katalog synkronisering finns i [Översikt över katalog synkronisering]( https://go.microsoft.com/fwlink/p/?LinkId=525398) och [hybrid identitet för Microsoft 365](plan-for-directory-synchronization.md).

För att katalog synkroniseringen ska fungera måste planering och förberedelse för att säkerställa att Active Directory Domain Services (AD DS) synkroniseras med Azure Active Directory (Azure AD)-klient organisationen för Microsoft 365-prenumerationen med minst fel.

Följ de här stegen för bästa resultat.

## <a name="1-directory-cleanup-tasks"></a>1. katalog rensnings uppgifter

Innan du synkroniserar AD DS till din Azure AD-klient organisation måste du rensa AD DS.

> [!IMPORTANT]
> Om du inte utför AD DS-rensning innan du synkroniserar kan distributions processen vara en väsentlig negativ effekt. Det kan ta några dagar, eller till och med veckor, att gå igenom Active Directory-synkroniseringen, identifiera fel och synkronisera igen.

I din AD DS utför du följande rensnings aktiviteter för varje användar konto som tilldelas en Microsoft 365-licens:

1. Kontrol lera en giltig och unik e-postadress i **proxyAddresses** -attributet.

2. Ta bort alla dubblettvärden i attributet **proxyAddresses** .

3. Kontrol lera om möjligt ett giltigt och unikt värde för attributet **userPrincipalName** i användarens **användar** objekt. För att den bästa synkroniseringen ska fungera bör du kontrol lera att AD DS UPN stämmer överens med Azure AD-UPN. Om en användare inte har ett värde för **userPrincipalName** -attributet måste **användarobjektet** innehålla ett giltigt och unikt värde för **sAMAccountName** -attributet. Ta bort alla dubblettvärden i **userPrincipalName** -attributet.

4. För optimal användning av den globala adress listan (GAL) kontrollerar du att informationen i följande attribut för AD DS-användarkontot är korrekt:

   - givenName
   - efter namn
   - visningsNamn
   - Befattning
   - Department
   - Office
   - Telefonnr till arbetet
   - Mobiltelefon
   - Fax nummer
   - Gatuadress
   - Ort
   - Region
   - Post nummer
   - Land eller region

## <a name="2-directory-object-and-attribute-preparation"></a>2. katalog objekt och filförberedelse

Om du har gjort en katalog synkronisering mellan AD DS och Microsoft 365 måste dina AD DS-attribut vara korrekt för beredda. Du måste till exempel se till att specifika tecken inte används i vissa attribut som synkroniseras med Microsoft 365-miljön. Oväntade tecken gör inte att Active Directory-synkroniseringen Miss lyckas men en varning kan visas. Ogiltiga tecken gör att synkroniseringen Miss lyckas.

Katalog synkronisering fungerar också om vissa av dina AD DS-användare har en eller flera dubbletter. Varje användare måste ha unika attribut.

De attribut som du måste förbereda finns här:

- **visningsNamn**

  - Om attributet finns i användarobjektet synkroniseras det med Microsoft 365.
  - Om det finns ett objekt i användarobjektet måste det vara ett värde för det. Attributet får inte vara tomt.
  - Maximalt antal tecken: 256

- **givenName**

  - Om attributet finns i användarobjektet synkroniseras det med Microsoft 365, men Microsoft 365 behöver inte eller använda det.
  - Maximalt antal tecken: 64

- **mail**

  - Attributvärdet måste vara unikt i katalogen.

    > [!NOTE]
    > Om det finns dubblettvärden synkroniseras den första användaren med värdet. Efterföljande användare visas inte i Microsoft 365. Du måste ändra värdet i Microsoft 365 eller ändra båda värdena i AD DS för att båda användarna ska visas i Microsoft 365.

- **smek namn** (Exchange-alias)

  - Attributvärdet får inte börja med en punkt (.).
  - Attributvärdet måste vara unikt i katalogen.

    > [!NOTE]
    > Under streck ("_") i det synkroniserade namnet anger att det ursprungliga värdet för det här attributet innehåller ogiltiga tecken. Mer information om det här attributet finns i [attribut för Exchange-alias](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).
    >

- **proxyAddresses**

  - Attribut med flera värden
  - Maximalt antal tecken per värde: 256
  - Attributvärdet får inte innehålla blank steg.
  - Attributvärdet måste vara unikt i katalogen.
  - Ogiltiga tecken: \< \> ();, [] "'

    Observera att ogiltiga tecken gäller de tecken som följer efter typ avgränsaren och ":", till exempel att SMTP:User@contso.com är tillåtet, men SMTP:user:M@contoso.com inte är det.

    > [!IMPORTANT]
    > Alla SMTP-adresser (Simple Mail Transport Protocol) ska överensstämma med e-poststandarderna. Om det finns dubbletter eller oönskade adresser, se hjälp avsnittet [ta bort dubbletter och oönskade proxyadresser i Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).

- **sAMAccountName**

  - Maximalt antal tecken: 20
  - Attributvärdet måste vara unikt i katalogen.
  - Ogiltiga tecken: [\ "|,/: \< \> + =;? \* ']
  - Om en användare har ett ogiltigt **sAMAccountName** -attribut men har ett giltigt **userPrincipalName** -attribut skapas användar kontot i Microsoft 365.
  - Om både **sAMAccountName** och **userPrincipalName** är ogiltiga måste du uppdatera AD DS **userPrincipalName** -attributet.

- **SN** (efter namn)

  - Om attributet finns i användarobjektet synkroniseras det med Microsoft 365, men Microsoft 365 behöver inte eller använda det.

- **targetAddress**

    Det krävs att attributet **targetAddress** (till exempel SMTP:Tom@contoso.com) som är ifyllt för användaren måste finnas med i Microsoft 365 gal. I scenarier med överföring av meddelanden från tredje part måste detta kräva Microsoft 365-schema för AD DS. Med schema tillägget Microsoft 365 kan du också lägga till andra användbara attribut för att hantera Microsoft 365-objekt som är ifyllda med ett verktyg för katalogbläddring från AD DS. **MsExchHideFromAddressLists** -attributet för att hantera dolda post lådor eller distributions grupper läggs till exempel till.

  - Maximalt antal tecken: 256
  - Attributvärdet får inte innehålla blank steg.
  - Attributvärdet måste vara unikt i katalogen.
  - Ogiltiga tecken: \ \< \> ();, [] "
  - Alla SMTP-adresser (Simple Mail Transport Protocol) ska överensstämma med e-poststandarderna.

- **userPrincipalName**

  - **UserPrincipalName** -attributet måste finnas i Internet-stilens inloggnings format där användar namnet följs av snabel-a (@) och ett domän namn: till exempel user@contoso.com. Alla SMTP-adresser (Simple Mail Transport Protocol) ska överensstämma med e-poststandarderna.
  - Det maximala antalet tecken för **userPrincipalName** -attributet är 113. Ett visst antal tecken tillåts före och efter snabel-a (@) enligt följande:
  - Maximalt antal tecken för det användar namn som ligger före at-tecknet (@): 64
  - Maximalt antal tecken för domän namnet efter snabel-a (@): 48
  - Ogiltiga tecken: \% &amp; \* +/=? { } | \< \> ( ) ; : , [ ] " '
  - En omljud är också ett ogiltigt tecken.
  - Tecknet @ är obligatoriskt i varje **userPrincipalName** -värde.
  - Tecknet @ får inte vara det första tecknet i varje **userPrincipalName** -värde.
  - Användar namnet får inte avslutas med en punkt (.), ett et-tecken ( &amp; ), ett blank steg eller ett snabel-a (@).
  - Användar namnet får inte innehålla blank steg.
  - Dirigerade domäner måste användas; lokala eller interna domäner kan till exempel inte användas.
  - Unicode omvandlas till understryknings tecken.
  - **userPrincipalName** får inte innehålla dubblettvärden i katalogen.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. förbereda attributet userPrincipalName

Active Directory är utformat för att tillåta slutanvändarna i din organisation att logga in på katalogen med antingen **sAMAccountName** eller **userPrincipalName**. På liknande sätt kan slutanvändare logga in på Microsoft 365 med hjälp av användarens huvud namn (UPN) på sitt arbets-eller skol konto. Med katalog-synkronisering görs ett försök att skapa nya användare i Azure Active Directory med samma UPN som finns i AD DS. UPN-filen är formaterad som en e-postadress.

I Microsoft 365 är UPN det standardattribut som används för att skapa e-postadressen. Det är enkelt att få **userPrincipalName** (i AD DS och Azure AD) och den primära e-postadressen i **proxyAddresses** ange olika värden. Om de har olika värden kan de vara förvirrande för administratörer och slutanvändare.

Det bästa är att justera dessa attribut för att minska förvirring. För att uppfylla kraven för enkel inloggning med AD FS (Active Directory Federation Services) 2,0 måste du se till att UPN i Azure Active Directory och AD DS matchar och använder ett giltigt domän namn område.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Lägg till ett alternativt UPN-suffix i AD DS

Du kan behöva lägga till ett alternativt UPN-suffix för att koppla användarens företags referenser till Microsoft 365-miljön. Ett UPN-suffix är en del av ett UPN till höger om @-tecknet. UPN-värden som används för enkel inloggning kan innehålla bokstäver, siffror, punkter, streck och under streck, men inga andra typer av tecken.

Mer information om hur du lägger till ett alternativt UPN-suffix i Active Directory finns i [förbereda för]( https://go.microsoft.com/fwlink/p/?LinkId=525430)Active Directory-synkronisering.

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. matcha AD DS-UPN med Microsoft 365-UPN

Om du redan har konfigurerat profilsynkronisering kanske användarens UPN för Microsoft 365 inte stämmer överens med användarens AD DS-UPN som har definierats i din AD DS. Det här kan inträffa när en användare tilldelas en licens innan domänen verifierades. Det här kan du lösa genom att använda [PowerShell för att korrigera dubblett-UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) för att uppdatera användarens UPN så att Microsoft 365 UPN matchar företagets användar namn och domän. Om du uppdaterar UPN i AD DS och vill att det ska synkroniseras med Azure Active Directory-identiteten, måste du ta bort användarens licens i Microsoft 365 innan du utför ändringarna i AD DS.

Se även [hur du förbereder en icke-dirigerbart domän (till exempel. lokal domän) för Active Directory-synkronisering](prepare-a-non-routable-domain-for-directory-synchronization.md).

## <a name="next-steps"></a>Nästa steg

Om du har gjort steg 1 till 5 ovan läser du [Konfigurera katalog synkronisering](set-up-directory-synchronization.md).
