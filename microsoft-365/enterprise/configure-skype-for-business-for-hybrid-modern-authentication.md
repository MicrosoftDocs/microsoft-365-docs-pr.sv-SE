---
title: Konfigurera en Skype för företag lokalt för att använda modern hybridautentisering
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
description: Lär dig hur du Skype för företag en lokal konfiguration för att använda HMA (Hybrid Modern Authentication), som ger dig säkrare användarautentisering och auktorisering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9695815d0a085931b10f7f64b9fca2e997af9077
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286063"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Konfigurera en Skype för företag lokalt för att använda modern hybridautentisering

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Modern autentisering är en metod för identitetshantering som ger säkrare användarautentisering och auktorisering, som är tillgänglig för Skype för företag-server lokalt och Exchange-server lokalt samt för Skype för företag-hybrider med delad domän.

 **Viktigt** Vill du veta mer om modern autentisering (MA) och varför du kanske vill använda den i ditt företag eller din organisation? Titta [i det här dokumentet](hybrid-modern-auth-overview.md) för en översikt. Om du behöver veta vilka Skype för företag stöds med MA, finns det information här!

 **Innan vi börjar** använder jag följande termer:

- Modern autentisering (MA)

- Modern hybridautentisering (HMA)

- Exchange lokalt (EXCH)

- Exchange Online (EXO)

- Skype för företag lokalt (SFB)

- Skype för företag Online (SFBO)

Om en bild i den här artikeln har ett objekt som är nedtonat  eller nedtonat, vilket innebär att det element som visas med grått inte ingår i MA-specifik konfiguration.

## <a name="read-the-summary"></a>Läs sammanfattningen

Den här sammanfattningen bryter ned processen i steg som annars skulle kunna gå förlorade under körningen, och är bra för en övergripande checklista för att hålla reda på var du befinner dig i processen.

1. Kontrollera först att du uppfyller alla krav.

1. Eftersom det finns många förutsättningar för både Skype för företag och Exchange finns mer information i **översiktsartikeln** [för den förincheckade checklistan.](hybrid-modern-auth-overview.md) Gör detta  *innan*  du påbörjar något av stegen i den här artikeln.

1. Samla in HMA-specifik information som du behöver i en fil eller OneNote.

1. Aktivera modern autentisering för EXO (om det inte redan är aktiverat).

1. Aktivera modern autentisering för SFBO (om det inte redan är aktiverat).

1. Aktivera modern hybridautentisering för Exchange autentisering lokalt.

1. Aktivera modern hybridautentisering för Skype för företag-autentisering lokalt.

Dessa steg aktiverar MA för SFB, SFBO, EXCH och EXO – det vill säga alla produkter som kan ingå i HMA-konfigurationen av SFB och SFBO (inklusive beroenden på EXCH/EXO). Med andra ord, om användarna finns i/har postlådor skapade i någon del av Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO eller EXCH + SFB), kommer din färdiga produkt att se ut så här:

![HMA-topologin Skype mixed 6-Skype har MA på på alla fyra möjliga platser.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

Som du ser finns det fyra olika platser att aktivera MA! För bästa användarupplevelse rekommenderar vi att du aktiverar MA på alla fyra av dessa platser. Om du inte kan aktivera MA på alla de här platserna justerar du stegen så att du aktiverar MA endast på de platser som krävs för din miljö.

Se avsnittet [Support för mer Skype för företag med MA för](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) topologier som stöds.

 **Viktigt** Kontrollera att du har uppfyllt alla krav innan du börjar. Du hittar den informationen i Översikt över [och förutsättningar för modern hybridautentisering.](hybrid-modern-auth-overview.md)

## <a name="collect-all-hma-specific-info-youll-need"></a>Samla in all HMA-specifik information som du behöver

När du har dubbelkollat att [](hybrid-modern-auth-overview.md) du uppfyller kraven för att använda modern autentisering (se anmärkningen ovan) bör du skapa en fil som innehåller den information du behöver för att konfigurera HMA i stegen som ligger före. Exempel som används i den här artikeln:

- **SIP-/SMTP-domän**

  - Exempel. contoso.com (är extern Office 365)

- **Klientorganisations-ID**

  - Det GUID som representerar Office 365 klientorganisation (vid inloggningen contoso.onmicrosoft.com).

- **SFB 2015 CU5 WEBBTJÄNST-URL:er**

Du behöver interna och externa webbtjänst-URL:er för alla SfB 2015-pooler distribuerade. Om du vill hämta dessa kör du följande Skype för företag Management Shell:

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Exempel. Internt: https://lyncwebint01.contoso.com

- Exempel. Externt: https://lyncwebext01.contoso.com

Om du använder en e Standard Edition server är den interna URL:en tom. I det här fallet ska du använda poolens fqdn för den interna URL:en.

## <a name="turn-on-modern-authentication-for-exo"></a>Aktivera modern autentisering för EXO

Följ anvisningarna här: [Exchange Online: Aktivera klientorganisationen för modern autentisering.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)

## <a name="turn-on-modern-authentication-for-sfbo"></a>Aktivera modern autentisering för SFBO

Följ anvisningarna här: [Skype för företag Online: Aktivera klientorganisationen för modern autentisering](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Aktivera modern hybridautentisering för Exchange på en lokal miljö

Följ anvisningarna här: [Konfigurera Exchange Server att använda modern hybridautentisering](configure-exchange-server-for-hybrid-modern-authentication.md).

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Aktivera modern hybridautentisering för Skype för företag på en lokal miljö

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Lägga till lokala webbtjänst-URL:er som SPN i Azure Active Directory

Nu måste du köra kommandon för att lägga till URL-adresser (som samlats in tidigare) som tjänsthuvudnamn i SFBO.

 **Obs!** Service principal names (SPNs) identifierar webbtjänster och associerar dem med ett säkerhetshuvudnamn (t.ex. ett kontonamn eller en grupp) så att tjänsten kan agera för en behörig användares räkning. Klienter som autentiserar på en server använder information som finns i SPNs.

1. Börja med att ansluta Azure Active Directory (Azure AD) med [de här instruktionerna.](/powershell/azure/active-directory/overview)

2. Kör det här kommandot lokalt för att få en lista över SFB-webbtjänstwebbwebbadresser.

   Observera att AppPrincipalId börjar med `00000004` . Det här motsvarar Skype för företag Online.

   Notera (och skärmbilder för senare jämförelser) utdata för det här kommandot, som innehåller en SE- och WS-URL, men oftast består av SPN som börjar med `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Om de interna **eller** externa SAB-URL:erna från den lokala platsen saknas (till exempel, och vi måste lägga till de specifika https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) posterna i den här listan.

    Se till att ersätta  *exempeladresserna nedan* med dina faktiska URL:er i Lägg till kommandon!

```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. Kontrollera att dina nya poster har lagts till genom att köra **kommandot Get-MsolServicePrincipal** från steg 2 igen och titta igenom utdata. Jämför listan eller skärmbilden före med den nya listan med SPN. Du kan även skärmbilda den nya listan för dina poster. Om det lyckades visas de två nya webbadresserna i listan. Om vi går igenom exemplet innehåller listan med SPN nu specifika URL:er https://lyncwebint01.contoso.com och https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Create the UndersTS Auth Server-objektet

Kör följande kommando i Skype för företag Management Shell.

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Aktivera modern hybridautentisering

Det här är det steg som faktiskt aktiverar ma. Alla tidigare steg kan köras i förväg utan att ändra klientautentiseringsflödet. När du är redo att ändra autentiseringsflödet kör du det här kommandot Skype för företag Management Shell.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Verifiera

När du har aktiverat HMA används det nya autentiseringsflödet för klientens nästa inloggning. Observera att endast aktivera HMA utlöser inte en nyauthentication för någon klient. Klienterna återauthenticate baserat på livslängden för autentiseringstoken och/eller certifikat de har.

Om du vill testa att HMA fungerar efter att du har aktiverat det loggar du ut från en test-SFB Windows-klient och klickar på "ta bort mina autentiseringsuppgifter". Logga in igen. Klienten ska nu använda Flödet för modern autentisering. Din inloggning innehåller nu en **Office 365-uppmaning** om ett arbets- eller skolkonto, som visas direkt innan klienten kontaktar servern och loggar in dig.

Du bör också kontrollera "Configuration Information" (konfigurationsinformation) Skype för företag klienter efter en OAuth-behörighet (OAuth Authority). Det gör du på klientdatorn genom att hålla ned CTRL-tangenten samtidigt som du högerklickar på Skype för företag-ikonen i Windows meddelandefältet. Klicka **på Konfigurationsinformation** i menyn som visas. I fönstret Skype för företag Konfigurationsinformation som visas på skrivbordet letar du efter följande:

![Konfigurationsinformationen för en klient Skype för företag modern autentisering visar URL-adressen till Lync och EWS OAUTH Authority för https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)

Du bör också hålla ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (även i meddelandefältet i Windows) och klickar på "Anslutningsstatus". Leta efter klientens SMTP-adress mot autentiseringstypen "Bearer", som representerar den bearer-token som används \* i OAuth.

## <a name="related-articles"></a>Relaterade artiklar

[Länka tillbaka till översikten över Modern autentisering.](hybrid-modern-auth-overview.md)

Behöver du veta hur du använder modern autentisering (ADAL) för dina Skype för företag klienter? Vi har steg [här](./hybrid-modern-auth-overview.md).