---
title: Lägga till DNS-poster för att ansluta till din domän
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Lär dig verifiera din domän och skapa DNS-poster på vilken DNS-värd som helst för Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 01bcffe37d9c38d91eff25d9df58f848f4ee1a82
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138262"
---
# <a name="add-dns-records-to-connect-your-domain"></a>Lägga till DNS-poster för att ansluta till din domän

Om du har köpt en domän från en tredjeparts värd kan du ansluta den till Microsoft 365 genom att uppdatera DNS-posterna på registratorns konto.

Under slutet av de här stegen kommer din domän att vara registrerad hos den värd som du har köpt domänen från, men Microsoft 365 kan använda det för e-postadresser (till exempel user@yourdomain.com) och andra tjänster.

Om du inte lägger till en domän kommer personer i organisationen att använda domänen onmicrosoft.com för sina e-postadresser tills du gör det. Det är viktigt att lägga till domänen innan du lägger till användare, så att du inte behöver konfigurera dem två gånger.

[Läs frågor och svar om domäner](../setup/domains-faq.md) om du inte hittar det du letar efter nedan.

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>Steg 1: Lägga till en TXT eller MX-post för att verifiera att det är din domän

### <a name="recommended-verify-with-a-txt-record"></a>Rekommenderas: Verifiera med en TXT-post

Först måste du bevisa att du äger den domän som du vill lägga till i Microsoft 365.

1. Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com/) och välj **Visa alla** > **Inställningar** > **Domäner**.
2. Logga in på din DNS-värdtjänst i en ny flik i webbläsaren eller i en ny webbläsare och leta sedan reda på hur du hanterar dina DNS-inställningar (t. ex. inställningar för zonfiler, hantera domäner, domänhanteraren, DNS-hanteraren).
3. Gå till din leverantörs DNS-hanterare och lägga till den TXT-post som anges i administrationscentret för din domän.

Om du lägger till den här posten påverkas inte din befintliga e-post och andra tjänster, och du kan ta bort den när domänen är ansluten till Microsoft 365.

Exempel:
- TXT-namn: `@`
- TXT-värde: MS = MS # # # # # # # # (unikt ID från administrationscentret)
- TTL: `3600‎` (eller din leverantörs standard)

4. Spara posten, gå tillbaka till administrationscentret och välj **Verifiera**. Det tar normalt cirka 15 minuter innan ändringarna registreras, men ibland kan det ta längre tid. Ge det lite tid och några försök att fånga förändringen.

När Microsoft hittar rätt TXT-post är din domän verifierad.

### <a name="verify-with-an-mx-record"></a>Verifiera med en MX-post

Om din domänregistrator inte har stöd för att lägga till TXT-poster kan du verifiera genom att lägga till en MX-post.

1. Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com/) och välj **Visa alla** > **Inställningar** > **Domäner**.
2. Logga in på din DNS-värdtjänst i en ny flik i webbläsaren eller i en ny webbläsare och leta sedan reda på hur du hanterar dina DNS-inställningar (t. ex. inställningar för zonfiler, hantera domäner, domänhanteraren, DNS-hanteraren).
3. Gå till din leverantörs DNS-hanterare och lägga till den MX-post som anges i administrationscentret för din domän.

MX-postens **Prioritet** måste vara den högsta av alla befintliga MX-poster för domänen. Annars kan det störa sändning och mottagning av e-post. Du bör ta bort de här posterna när domänverifieringen är slutförd.

Kontrollera att fälten är inställda på följande värden:

- Posttyp: `MX`
- Prioritet: Ange det högsta värdet, vanligtvis `0`.
- Värdnamn: `@`
- Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.
- TTL: `3600‎` (eller din leverantörs standard)

När Microsoft hittar rätt MX-post är din domän verifierad.

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>Steg 2: Lägga till DNS-poster för att ansluta till Microsoft-tjänster

Logga in på din DNS-värdtjänst i en ny flik i webbläsaren eller i en ny webbläsare och leta reda på hur du hanterar dina DNS-inställningar (t. ex. inställningar för zonfiler, hantera domäner, domänhanteraren, DNS-hanteraren).

Du kan lägga till flera olika typer av DNS-poster beroende på vilka tjänster du vill aktivera. 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>Lägga till en MX-post för e-post (Outlook, Exchange Online)
**Innan du börjar**: om användarna redan har ett e-postmeddelande med din domän (t. ex. user@yourdomain.com), skapar du kontona i administrationscentret innan du konfigurerar dina MX-poster. På så sätt fortsätter de att få e-post. När du uppdaterar domänens MX-post kommer nu alla nya e-postmeddelanden till alla som använder din domän till Microsoft 365. E-postmeddelanden som du redan har finns kvar hos din nuvarande e-postvärd, om du inte bestämmer dig för att [migrera e-postmeddelanden och kontakter till Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)

Du får information om MX-posten från administrationscentrets konfigurationsguide.

Lägg till en ny MX-post på värdens webbplats.
Kontrollera att fälten är inställda på följande värden:

- Posttyp: `MX`
- Prioritet: Ange det högsta värdet, vanligtvis `0`.
- Värdnamn: `@`
- Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.
- TTL: `3600‎` (eller din leverantörs standard)

Spara posten och ta bort eventuella andra MX-poster.

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>Lägga till CNAME-poster för att ansluta till andra tjänster (Teams, Exchange Online, AAD, MDM)
Du får information om CNAME-posterna från administrationscentrets konfigurationsguide.

Lägg till CNAME-poster för varje tjänst du vill ansluta på värdens webbplats.
Kontrollera att fälten är inställda på följande värden för varje:

- Posttyp: `CNAME (Alias)`
- Värd: Klistra in värdena som du kopierar från administrationscentret här.
- Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.
- TTL: `3600‎` (eller din leverantörs standard)


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>Lägga till eller redigera en SPF TXT-post för att förhindra skräppost i e-post (Outlook, Exchange Online)
**Innan du börjar:** Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft 365. Lägg istället till de obligatoriska Microsoft 365-värdena i den aktuella posten på din värds webbplats så att du har en *enda* SPF-post som innehåller båda uppsättningarna med värden.

Redigera den befintliga SPF-posten eller skapa en SPF-post på värdens webbplats.
Kontrollera att fälten är inställda på följande värden:

- Posttyp: `TXT (Text)`
- Värd: `@`
- TXT Value: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (eller din leverantörs standard)

Spara posten.

Använd något av följande [SPF-verifieringsverktyg](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) för att verifiera SPF-posten

SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot. För att skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Microsoft 365. 

Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din domän i Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) och [Använda DMARC för att validera e-post i Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>Lägga till SRV-poster för kommunikationstjänster (Teams, Skype för företag)

Lägg till SRV-poster för varje tjänst du vill ansluta på värdens webbplats.
Kontrollera att fälten är inställda på följande värden för varje:

- Posttyp: `SRV (Service)`
- Namn: `@`
- Mål: Kopiera värdet från administrationscentret och klistra in det här.
- Protokoll: Kopiera värdet från administrationscentret och klistra in det här.
- Tjänst: Kopiera värdet från administrationscentret och klistra in det här.
- Prioritet: `100`
- Vikt: `1`
- Port: Kopiera värdet från administrationscentret och klistra in det här.
- TTL: `3600‎` (eller din leverantörs standard)

Spara posten.

#### <a name="srv-record-field-restrictions-and-workarounds"></a>Restriktioner och lösningar för SRV-postfält
Vissa värdar har restriktioner för fältvärden i SRV-poster. Här är några vanliga lösningar på de här begränsningarna.

##### <a name="name"></a>Namn
Om din värd inte tillåter att fältet anges till **@**, lämnar du det tomt. Använd den här metoden *bara* när din värd har separata fält för värdena Tjänst och Protokoll. Se annars anteckningarna om Tjänst och Protokoll nedan.

##### <a name="service-and-protocol"></a>Tjänst och protokoll
Om värden inte tillhandahåller dessa fält för SRV-poster måste du ange värdena för **Tjänst-** och **Protokollvärden** i postens **Namn**. (Obs! Beroende på värden kan fältet **Namn** heta något annat, t.ex. **Värd**, **Värdnamn** eller **Underdomän**.) För att lägga till värdet skapar du en enskild sträng och separerar värdena med en punkt. 

Exempel: `_sip._tls`

##### <a name="priority-weight-and-port-br"></a>Prioritet, vikt och port <br>
Om värden inte tillhandahåller dessa fält för SRV-poster måste du ange värdena för postens **Målfält**. (Obs! beroende på din värd kan **Målfältet** kallas för något annat, t. ex.: **Innehåll**, **IP-adress**eller **Målvärd**.) 

Om du vill lägga till de här värdena skapar du en sträng som avgränsar värdena med blanksteg och *ibland slutar med en punkt* (kontrollera med din leverantör om du är osäker). Värdena måste tas med i följande ordning: Prioritet, Vikt, Port, Mål. 

- Exempel 1: `100 1 443 sipdir.online.lync.com.`
- Exempe 2l: `100 1 443 sipdir.online.lync.com`
