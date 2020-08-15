---
title: Konfigurera Skype för företag för lokal användning av hybrid modern
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lär dig hur du konfigurerar Skype för företag lokalt för användning av hybrid modern autentisering (HMA) och ger dig säkrare autentisering och verifiering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695032"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Konfigurera Skype för företag för lokal användning av hybrid modern

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Modern autentisering, är en metod för identitets hantering som erbjuder säkrare användar verifiering och-auktorisering, och är tillgänglig för Skype för företag-Server lokalt och Exchange Server lokalt samt för delade domän-domäner med hybrider.
  
 **Viktigt** Vill du veta mer om modern inloggningsautentisering (MA) och varför du föredrar att använda den i ditt företag eller din organisation? Kontrol lera [detta dokument](hybrid-modern-auth-overview.md) för en översikt. Om du behöver veta vad topologierna för Skype för företag fungerar tillsammans med MA är det dokumenterat här!
  
 **Innan vi börjar**följer jag de här villkoren:
  
- Modern (MA)

- Hybrid modern (HMA)

- Exchange On-premises (VALUTAKURS)

- Exchange Online (EXO)

- Skype för företag – lokalt (SFB)

- Skype för företag – Online (SFBO)

Om en bild i den här artikeln har ett objekt som är nedtonat eller nedtonat innebär det att elementet som visas i grått **inte** ingår i valfri konfiguration.
  
## <a name="read-the-summary"></a>Läsa sammanfattningen

Den här sammanfattningen delar upp processen i steg som annars skulle förloras under körningen, och det är bra för en övergripande check lista för att hålla reda på var du befinner dig.
  
1. Kontrol lera först att du uppfyller alla förutsättningar.

1. Eftersom många **förutsättningar** är vanliga för både Skype för företag och Exchange kan du [läsa översikts artikeln för din check lista för krav](hybrid-modern-auth-overview.md). Gör det  *innan*  du följer anvisningarna i den här artikeln.

1. Samla in den HMA-specifika information du behöver i en fil eller i OneNote.

1. Aktivera modern EXO (om den inte redan är aktive rad).

1. Aktivera modern SFBO (om den inte redan är aktive rad).

1. Aktivera hybrid modern inloggning för Exchange lokal.

1. Aktivera hybrid modern inloggning för Skype för företag lokalt.

De här stegen aktiverar MA för SFB, SFBO, VALUTAKURS och EXO-det vill säga alla produkter som kan delta i en HMA-konfiguration för SFB och SFBO (inklusive beroenden på polyEXO). Med andra ord kommer den färdiga produkten att se ut så här om användarna är hemifrån/har post lådor som har skapats i en del av hybriden (EXO + SFBO, EXO + SFB, Poly+ SFBO eller Poly+ SFB):
  
![En 6-Topology-topologi med sex Skype för företag har MA på alla fyra möjliga platser.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
Som du ser finns det fyra olika ställen att slå på MA! För att det ska fungera så bra som möjligt rekommenderar vi att du aktiverar MA på alla fyra av dessa platser. Om du inte kan aktivera MA på alla de här platserna, justera stegen så att endast MA visas på de platser som behövs för din miljö.
  
Se [Support för Skype för företag med ma](https://technet.microsoft.com/library/mt803262.aspx) för topologier som stöds.
  
 **Viktigt** Kontrol lera att du har uppfyllt alla förutsättningar innan du börjar. Informationen finns i [hybrid modern verifiering och förutsättningar](hybrid-modern-auth-overview.md).
  
## <a name="collect-all-hma-specific-info-youll-need"></a>Samla in alla HMA-specifika uppgifter du behöver

När du har dubbelt kontrollerat att du uppfyller [kraven](hybrid-modern-auth-overview.md) för att använda modern verifiering (se anvisningarna ovan), bör du skapa en fil som innehåller den information du behöver för att konfigurera HMA i stegen ovan. Exempel som används i den här artikeln:
  
- **SIP-domän**

  - Hand. contoso.com (är sammanslaget med Office 365)

- **Klient-ID**

  - GUID som representerar din Office 365-klient (vid inloggningen på contoso.onmicrosoft.com).

- **Webb adresser för SFB 2015 CU5**

du behöver interna och externa webb tjänst-URL: er för alla SfB 2015-pooler distribuerade. För att få dessa kan du köra följande från Skype för företag Management Shell:
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Hand. Intern https://lyncwebint01.contoso.com

- Hand. 5,25 https://lyncwebext01.contoso.com

Om du använder en standard server för Edition är den interna URL-adressen tom. I det här fallet ska du använda pool-FQDN för den interna URL-adressen.
  
## <a name="turn-on-modern-authentication-for-exo"></a>Aktivera modern EXO

Följ anvisningarna här: [Exchange Online: så här aktiverar du en klient organisation för modern verifikation.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>Aktivera modern SFBO

Följ anvisningarna här: [Skype för företag – online: aktivera din klient organisation för modern verifikation](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Aktivera hybrid modern inloggning för Exchange lokalt

Följ anvisningarna här: [så här konfigurerar du Exchange Server lokalt för användning av hybrid modern](configure-exchange-server-for-hybrid-modern-authentication.md).
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Aktivera hybrid modern inloggningsautentisering för Skype för företag – lokalt

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Lägga till lokala webb tjänst-URL-adresser i Azure Active Directory

Nu måste du köra kommandon för att lägga till URL-adresserna (samlas in tidigare) som tjänst huvud objekt i SFBO.
  
 **Obs!** SPN (tjänstens huvud namn) identifiera webb tjänster och koppla dem till ett säkerhets objekt (till exempel ett konto namn eller en grupp) så att tjänsten kan agera för en behörig användares räkning. Klienter som autentiserar sig på en server använder information som finns i SPN.
  
1. Börja med att ansluta till Azure Active Directory (Azure AD) med [dessa instruktioner](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Kör det här kommandot lokalt för att få en lista med webb adresserna för SFB web service.

   Observera att AppPrincipalId börjar med `00000004` . Detta motsvarar Skype för företag – online.

   Notera (och skärm bild för senare jämförelse) utdata för det här kommandot, som innehåller ett SE-och en URL-adress, men som till exempel består av de SPN som börjar med `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Om de interna **eller** externa SFB URL-adresser från lokala användare saknas (till exempel https://lyncwebint01.contoso.com och https://lyncwebext01.contoso.com) vi måste lägga till dessa specifika poster i den här listan.

    Se till att du ersätter  *exemplen* nedan med dina faktiska URL-adresser i kommandona Add!
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. Verifiera att de nya posterna har lagts till genom att köra kommandot **Get-MsolServicePrincipal** från steg 2 igen och titta igenom resultatet. Jämför listan eller skärm bilden från den nya listan med SPN-objekt. Du kan också Skärmdumpa den nya listan för posterna. Om du lyckades ser du de två nya URL-adresserna i listan. I vårt exempel kommer listan med SPN att inkludera specifika URL: er https://lyncwebint01.contoso.com och https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Skapa EvoSTS

Kör följande kommando i Skype för företag Management Shell.
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Aktivera hybrid modern

Det här steget vänder sig faktiskt till MA. Alla föregående steg kan köras i förväg utan att klientens autentiseringspaket ändras. När du är redo att ändra autentiseringsläget kör du det här kommandot i Skype för företag Management Shell.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Kontroll

När du har aktiverat HMA använder klientens nästa inloggning det nya trafikflödet. Observera att när du bara aktiverar HMA utlöses ingen reauktorisering för någon klient. Klienterna autentiseras baserat på de auth-token och/eller certifikat de har.
  
Testa att HMA fungerar när du har aktiverat det genom att logga ut från en test SFB Windows-klient och klicka på "ta bort mina autentiseringsuppgifter". Logga in igen. Klienten bör nu använda moderna auth-flödet och din inloggning innehåller nu en **Office 365** -uppmaning för ett "jobb-eller skol konto" som visas direkt innan klienten kontaktar servern och loggar in dig.
  
Du bör också kontrol lera "konfigurations information" för Skype för företag-klienter för en "OAuth-auktoritet". Om du vill göra det på klient datorn håller du ned CTRL samtidigt som du högerklickar på ikonen Skype för företag i meddelande fältet i Windows. Klicka på **konfigurations information** i menyn som visas. I fönstret Skype för företag-konfigurations information som visas på Skriv bordet letar du upp följande:
  
![Konfigurations informationen för en Skype för företag-klient med modern autentisering visar en Lync-och EWS OAUTH Authority-URL till https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
Håll ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (också i Windows Notifications-fältet) och klicka på "anslutnings status". Leta efter klientens SMTP-adress mot authn-typen "Bearer \* ", som representerar Bearer-token som används i OAuth.
  
## <a name="related-articles"></a>Relaterade artiklar

[Länka tillbaka till den moderna verifikations översikten](hybrid-modern-auth-overview.md).
  
Behöver du veta hur du använder modern inloggningsautentisering (ADAL) för dina Skype för företag-klienter? Det finns anvisningar [här](https://technet.microsoft.com/library/mt710548.aspx).
