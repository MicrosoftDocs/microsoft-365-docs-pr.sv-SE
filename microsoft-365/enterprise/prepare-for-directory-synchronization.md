---
title: Förbereda för katalogsynkronisering till Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
description: Här beskrivs hur du förbereder för att tillhandahålla Microsoft 365 med hjälp av katalogsynkronisering och de långsiktiga fördelarna med den här metoden.
ms.openlocfilehash: ee6cfe9adfe029e620d2465f08a3fbe1e9290503
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229773"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Förbereda för katalogsynkronisering till Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Fördelarna med hybrididentitet och katalogsynkronisering din organisation är:

- Minska administratörsprogrammen i organisationen
- Om du vill aktiverar du scenariot för enkel inloggning
- Automatisera kontoändringar i Microsoft 365

Mer information om fördelarna med att använda katalogsynkronisering finns i hybrididentitet med [Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) och [hybrididentitet för Microsoft 365.](plan-for-directory-synchronization.md)

Men katalogsynkronisering kräver planering och förberedelse för att säkerställa att DIN AD DS (Active Directory Domain Services) synkroniserar till Azure AD-klientorganisationen för Microsoft 365-prenumerationen med så få fel som möjligt.

Följ de här anvisningarna för att uppnå bästa resultat.

## <a name="1-directory-cleanup-tasks"></a>1. Katalogrensningsuppgifter

Innan du synkroniserar DIN AD DS till Azure AD-klientorganisationen måste du rensa dina AD DS.

> [!IMPORTANT]
> Om du inte rensar AD DS innan du synkroniserar kan det leda till en betydande negativ inverkan på distributionsprocessen. Det kan ta dagar eller veckor att gå igenom hela katalogsynkroniseringen, att identifiera fel och omsynkronisering.

Utför följande rensningsuppgifter i AD DS för varje användarkonto som ska tilldelas en Microsoft 365 licens:

1. Kontrollera en giltig och unik e-postadress i **attributet proxyAddresses.**

2. Ta bort alla dubblettvärden i **attributet proxyAddresses.**

3. Om möjligt bör du säkerställa ett giltigt och unikt värde för **attributet userPrincipalName** i användarens **användarobjekt.** För bästa möjliga synkronisering ser du till att AD DS UPN matchar Azure AD UPN. Om en användare inte har något värde för **attributet userPrincipalName** måste användarobjektet innehålla ett giltigt och unikt värde för **attributet sAMAccountName.**  Ta bort alla dubblettvärden i **attributet userPrincipalName.**

4. För optimal användning av den globala adresslistan (GAL) ser du till att informationen i följande attribut för AD DS-användarkontot är korrekt:

   - givenName
   - efternamn
   - visningsNamn
   - Befattning
   - Department
   - Office
   - Telefonnr till arbetet
   - Mobiltelefon
   - Faxnummer
   - Gatuadress
   - Ort
   - Region
   - Postnummer
   - Land eller region

## <a name="2-directory-object-and-attribute-preparation"></a>2. Förberedelse av katalogobjekt och katalogattribut

För att synkroniseringen mellan AD DS och Microsoft 365 ska fungera måste AD DS-attributen förberedas ordentligt. Du måste till exempel se till att inga specifika tecken används i vissa attribut som synkroniseras med den Microsoft 365 miljön. Katalogsynkroniseringen misslyckas inte om oväntade tecken visas, men kan returnera en varning. Ogiltiga tecken leder till att katalogsynkroniseringen misslyckas.

Katalogsynkroniseringen misslyckas också om en del av DINA AD DS-användare har ett eller flera dubblettattribut. Varje användare måste ha unika attribut.

Attributen du behöver förbereda visas här:

- **visningsNamn**

  - Om attributet finns i användarobjektet synkroniseras det med Microsoft 365.
  - Om det här attributet finns i användarobjektet måste det ha ett värde. Det innebär att attributet inte får vara tomt.
  - Maximalt antal tecken: 256

- **givenName**

  - Om attributet finns i användarobjektet synkroniseras det med Microsoft 365 men det Microsoft 365 inte eller använder det.
  - Maximalt antal tecken: 64

- **mail**

  - Attributvärdet måste vara unikt i katalogen.

    > [!NOTE]
    > Om det finns dubblettvärden synkroniseras den första användaren med värdet. Efterföljande användare visas inte i Microsoft 365. Du måste antingen ändra värdet i Microsoft 365 eller ändra båda värdena i AD DS för att båda användarna ska visas i Microsoft 365.

- **mailNickname** (Exchange alias)

  - Attributvärdet kan inte börja med en punkt (.).
  - Attributvärdet måste vara unikt i katalogen.

    > [!NOTE]
    > Understreck ("_") i det synkroniserade namnet anger att det ursprungliga värdet för det här attributet innehåller ogiltiga tecken. Mer information om det här attributet finns i [Exchange aliasattribut](/powershell/module/exchange/set-mailbox).
    >

- **proxyAddresses**

  - Attribut med flera värden
  - Maximalt antal tecken per värde: 256
  - Attributvärdet får inte innehålla blanksteg.
  - Attributvärdet måste vara unikt i katalogen.
  - Ogiltiga tecken: \< \> ( ) ; , [ ] "

    Observera att ogiltiga tecken gäller tecknen som kommer efter avgränsaren och ":", så att SMTP:User@contso.com är tillåtet, men SMTP:user:M@contoso.com är det inte.

    > [!IMPORTANT]
    > Alla SMTP-adresser (Simple Mail Transport Protocol) ska följa e-poststandarderna. Ta bort dubbletter eller oönskade adresser om de finns.

- **sAMAccountName**

  - Maximalt antal tecken: 20
  - Attributvärdet måste vara unikt i katalogen.
  - Ogiltiga tecken: [ \ " | , / : \< \> + = ; ? \* ']
  - Om en användare har ett **ogiltigt sAMAccountName-attribut** men ett giltigt **userPrincipalName-attribut** skapas användarkontot i Microsoft 365.
  - Om både **sAMAccountName** och **userPrincipalName** är ogiltiga måste AD DS-attributet **userPrincipalName** uppdateras.

- **sn** (efternamn)

  - Om attributet finns i användarobjektet synkroniseras det med Microsoft 365 men det Microsoft 365 inte eller använder det.

- **targetAddress**

    Attributet **targetAddress** (till exempel SMTP:tom@contoso.com) som fylls i för användaren måste visas i den Microsoft 365 GAL. Vid migrering av meddelanden från tredje part skulle det kräva Microsoft 365 för AD DS. Tillägget Microsoft 365 skulle också lägga till andra användbara attribut för att hantera Microsoft 365 objekt som fylls i med hjälp av ett katalogsynkroniseringsverktyg från AD DS. Till exempel läggs **attributet msExchHideFromAddressLists** till för att hantera dolda postlådor eller distributionsgrupper.

  - Maximalt antal tecken: 256
  - Attributvärdet får inte innehålla blanksteg.
  - Attributvärdet måste vara unikt i katalogen.
  - Ogiltiga tecken: \ \< \> ( ) ; , [ ] "
  - Alla SMTP-adresser (Simple Mail Transport Protocol) ska följa e-poststandarderna.

- **userPrincipalName**

  - Attributet **userPrincipalName** måste vara i inloggningsformat på Internet, där användarnamnet följs av at-tecknet (@) och ett domännamn: till exempel user@contoso.com. Alla SMTP-adresser (Simple Mail Transport Protocol) ska följa e-poststandarderna.
  - Attributet **userPrincipalName** får ha högst 113 tecken. Ett visst antal tecken tillåts före och efter at-tecknet (@), enligt följande:
  - Maximalt antal tecken för användarnamnet som står framför at-tecknet (@): 64
  - Maximalt antal tecken för domännamnet som följer efter at-tecknet (@): 48
  - Ogiltiga tecken: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - Tillåtna tecken: A – Ö, a - z, 0 – 9, ' . - _ ! # ^ ~
  - Bokstäver med diakritiska tecken som omljud, accenter och tilde är ogiltiga tecken.
  - Tecknet @ krävs i varje **userPrincipalName-värde.**
  - Tecknet @ får inte vara det första tecknet i varje **userPrincipalName-värde.**
  - Användarnamnet får inte sluta med punkt (.), et-tecken ( &amp; ), blanksteg eller at-tecken (@).
  - Användarnamnet får inte innehålla blanksteg.
  - Dirigerbara domäner måste användas. Lokala eller interna domäner kan till exempel inte användas.
  - Unicode konverteras till understreck.
  - **userPrincipalName** får inte innehålla dubblettvärden i katalogen.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Förbereda attributet userPrincipalName

Active Directory har utformats så att slutanvändarna i organisationen ska kunna logga in i katalogen med hjälp av **antingen sAMAccountName** eller **userPrincipalName.** På samma sätt kan slutanvändarna logga in Microsoft 365 med hjälp av huvudnamnet (UPN) för sitt arbets- eller skolkonto. Katalogsynkronisering försöker skapa nya användare i Azure Active Directory med samma UPN som finns i din AD DS. UPN är formaterat som en e-postadress.

I Microsoft 365 är UPN standardattributet som används för att generera e-postadressen. Det är enkelt att ange olika värden för **userPrincipalName** (i AD DS och i Azure AD) och den primära e-postadressen i **proxyAddresses.** De olika värdena kan vara förvirrande för administratörer och slutanvändare.

Därför är det bäst att attributen stämmer överens. För att uppfylla kraven för enkel inloggning med Active Directory Federation Services (AD FS) 2.0 måste du kontrollera att UPN-namn i Azure Active Directory och AD DS stämmer överens och använder ett giltigt domännamnsområde.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Lägg till ett alternativt UPN-suffix i AD DS

Du kan behöva lägga till ett alternativt UPN-suffix för att associera användarens företagsautentiseringsuppgifter med Microsoft 365 miljö. Ett UPN-suffix är den del av ett UPN som står till höger om @-tecknet. UPN-nummer som används för enkel inloggning får innehålla bokstäver, siffror, punkter, bindestreck och understreck, men inga andra typer av tecken.

Mer information om hur du lägger till ett alternativt UPN-suffix i Active Directory finns i [Förbereda katalogsynkronisering.](https://go.microsoft.com/fwlink/p/?LinkId=525430)

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Matcha AD DS UPN med MICROSOFT 365 UPN

Om du redan har konfigurerat katalogsynkronisering kanske användarens UPN för Microsoft 365 inte stämmer överens med användarens AD DS UPN som definierats i AD DS. Detta kan inträffa när en användare har tilldelats en licens innan domänen verifierades. Lös det genom att använda PowerShell för att åtgärda UPN-dubbletter och uppdatera användarens [UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) så att UPN för Microsoft 365 matchar företagets användarnamn och domän. Om du uppdaterar UPN i AD DS och vill att det synkroniseras med Azure Active Directory-identiteten måste du ta bort användarens licens i Microsoft 365 innan du gör ändringarna i AD DS.

Se även [Så här förbereder du en icke-dirigerbar domän (till exempel .local) för katalogsynkronisering.](prepare-a-non-routable-domain-for-directory-synchronization.md)

## <a name="next-steps"></a>Nästa steg

Om du har utfört steg 1 till 5 ovan går du till [Konfigurera katalogsynkronisering](set-up-directory-synchronization.md).
