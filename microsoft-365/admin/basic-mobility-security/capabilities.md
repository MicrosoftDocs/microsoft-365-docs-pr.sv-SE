---
title: Funktioner i grundläggande Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Basic Mobility and Security kan hjälpa dig att skydda och hantera mobila enheter.
ms.openlocfilehash: a5f20b2999a1a54070433560904e9535a4d1524a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228285"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Funktioner i grundläggande Mobility and Security

Basic Mobility and Security kan hjälpa dig att skydda och hantera mobila enheter som iPhone, iPad, Android och Windows Telefoner som används av licensierade Microsoft 365 användare i organisationen. Du kan skapa principer för hantering av mobila enheter med inställningar som kan hjälpa dig att kontrollera åtkomsten till din organisations e-Microsoft 365 och dokument för mobila enheter och appar som stöds. Om en enhet försvinner eller blir stulen kan du fjärradea enheten för att ta bort känslig information om organisationen.

## <a name="supported-devices"></a>Enheter som stöds

Du kan använda Basic Mobility and Security för att skydda och hantera följande enheter.

- iOS 11.0 eller senare versioner

- Android 5.0 eller senare versioner<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> Åtkomstkontrollen för Windows 8.1 RT-enheter är begränsad till Exchange ActiveSync.

<sup>2</sup> Åtkomstkontroll för Windows 10 kräver en prenumeration som Azure AD Premium och enheten måste vara ansluten till Azure Active Directory.

<sup>3</sup> Efter juni 2020 kan Android-versioner senare än 9 inte hantera lösenordsinställningar utom på Samsung Knox-enheter.

> [!NOTE]
> Enheter som redan har registrerats med tidigare os-versioner fortsätter att fungera, men funktionerna kan ändras utan föregående meddelande.

Om personer i din organisation använder mobila enheter som inte stöds av Grundläggande rörlighet och säkerhet kanske du vill blockera Exchange ActiveSync-appåtkomst till Microsoft 365-e-post för dessa enheter, för att göra organisationens data säkrare. Information om hur du blockerar Exchange ActiveSync finns i [Hantera inställningar för enhetsåtkomst i Grundläggande rörlighet och säkerhet.](manage-device-access-settings.md)

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Åtkomstkontroll för e Microsoft 365 och dokument

Apparna som stöds för de olika typerna av mobila enheter i följande tabell uppmanar användarna att registrera sig i Basic Mobility and Security, där det finns en ny princip för hantering av mobila enheter som gäller för en användares enhet och användaren inte tidigare har registrerat enheten. Om en användares enhet inte uppfyller en princip, beroende på hur du har angett principen, kan en användare blockeras från att komma åt Microsoft 365-resurser i dessa program, eller så kan de ha åtkomst, men Microsoft 365 rapporterar en principbrott.

|**Produkt**|**iOS 10.0 eller senare**|**Android 5.0 eller senare**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync innehåller inbyggda e-post- och tredjepartsprogram, till exempel TouchDown, som använder Exchange ActiveSync version 14.1 eller senare. |E-post |E-post |
|**Office**   och  **OneDrive för företag** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**På telefoner och surfplattor:**<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Endast på telefoner:** <br/> Office Mobil |

> [!NOTE]
>
> - Stöd för iOS 10.0 och senare versioner omfattar även iPhone och iPad enheter.
> - Hantering av BlackBerry OS-enheter stöds inte av Basic Security och Mobility. Använd BlackBerry Business Cloud Services (BBCS) från BlackBerry för att hantera BlackBerry OS-enheter. Blackberry-enheter med Android OS stöds som vanliga Android-enheter
> - Användarna uppmanas inte att registrera sig och de kommer inte att blockeras eller rapporteras för principbrott om de använder mobilwebbläsaren för att komma åt Microsoft 365 SharePoint-webbplatser, dokument i Office Online eller e-post i Outlook Web App.

Följande diagram visar vad som händer när en användare med en ny enhet loggar in i en app som stöder åtkomstkontroll med Basic Mobility och Security. Användaren blockeras från att komma åt Microsoft 365 i programmet tills de registrerar sin enhet.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Åtkomstkontroll för enkel rörlighet och säkerhet":::

> [!NOTE]
> Principer och åtkomstregler som skapats i Basic Mobility and Security för Microsoft 365 Business Standard åsidosätter Exchange ActiveSync postlådeprinciper för mobila enheter och åtkomstregler som skapats i Exchange administrationscenter. När en enhet har registrerats i Basic Mobility and Security för Microsoft 365 Business Standard ignoreras eventuella Exchange ActiveSync-postlådeprinciper för mobila enheter eller enhetsåtkomstregel som tillämpas på enheten. Mer information om Exchange ActiveSync finns i [Exchange ActiveSync i Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="policy-settings-for-mobile-devices"></a>Principinställningar för mobila enheter

Om du skapar en princip för att blockera åtkomst med vissa inställningar påslagna blockeras användarna från att komma åt Microsoft 365-resurser när de använder ett program som stöds och som finns i Access-kontrollen för e-post och dokument i [Microsoft 365.](capabilities.md)

De inställningar som kan blockera användare från att komma åt Microsoft 365 finns i följande avsnitt:

- Säkerhet

- Kryptering

- Jail broken

- Hanterad e-postprofil

Följande diagram visar till exempel vad som händer när en användare med en registrerad enhet inte följer en säkerhetsinställning i en princip för hantering av mobila enheter som gäller för deras enhet. Användaren loggar in på en app som har stöd för åtkomstkontroll med Basic Mobility and Security. De blockeras från att komma Microsoft 365-resurser i programmet tills enheten uppfyller säkerhetsinställningen.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Meddelande om efterlevnad av grundläggande rörlighet och säkerhet":::

I följande avsnitt finns en lista över de principinställningar du kan använda för att skydda och hantera mobila enheter som ansluter Microsoft 365 organisationens resurser.

## <a name="security-settings"></a>Säkerhetsinställningar

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Kräv lösenord|Ja|Ja|Ja|
|Förhindra enkelt lösenord|Ja|Nej|Nej|
|Kräv ett alfanumeriskt lösenord|Ja|Nej|Nej|
|Minsta lösenordslängd |Ja|Ja|Ja|
|Antal inloggningsfel innan enheten rensas |Ja|Ja|Ja|
|Minuter av inaktivitet innan enheten låses |Ja|Ja|Ja|
|Lösenords giltighetstid (dagar) |Ja|Ja|Ja|
|Kom ihåg lösenordshistorik och förhindra återanvändning |Ja|Ja|Ja|

## <a name="encryption-settings"></a>Krypteringsinställningar

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Kräva datakryptering på enheter<sup>1</sup> |Nej|Ja|Ja|

<sup>1</sup> Med Samsung Knox kan du också kräva kryptering på minneskort.

## <a name="jail-broken-setting"></a>Inskannad inställning av jail broken

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Enheten kan inte bli jail broken or rooted |Ja|Ja|Ja|

## <a name="managed-email-profile-option"></a>Alternativ för hanterad e-postprofil

Följande alternativ kan blockera användare från att komma åt sin e Microsoft 365-post om de använder en manuellt skapad e-postprofil. Användare på iOS-enheter måste ta bort sin manuellt skapade e-postprofil innan de kan komma åt sin e-post. När profilen tas bort skapas automatiskt en ny profil på enheten. Anvisningar om hur slutanvändare följer finns i Ett [befintligt e-postkonto hittades.](/intune-user-help/existing-company-email-account-found)

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|E-postprofil hanteras |Ja|Nej|Nej|

## <a name="cloud-settings"></a>Molninställningar

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Kräv krypterad säkerhetskopiering |Ja|Nej|Nej|
|Blockera säkerhetskopiering av molnet |Ja|Nej|Nej|
|Blockera dokumentsynkronisering |Ja|Nej|Nej|
|Blockera fotosynkronisering  |Ja|Nej|Nej|
|Tillåt säkerhetskopiering av Google  |Uppgift saknas|Nej|Ja|
|Tillåt automatisk synkronisering av Google-konto  |Uppgift saknas|Nej|Ja|

## <a name="system-settings"></a>Systeminställningar

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blockera skärminspelning |Ja|Nej|Ja|
|Blockera att diagnostikdata skickas från enheten |Ja|Nej|Ja|

## <a name="application-settings"></a>Programinställningar

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blockera videokonferenser på en enhet |Ja|Nej|Nej|
|Blockera åtkomst till programbutik |Ja|Nej|Ja|
|Kräv lösenord när du öppnar programbutik |Nej|Ja|Ja|

## <a name="device-capabilities-settings"></a>Inställningar för enhetsfunktioner

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Blockera anslutning med flyttbara lagringsmedia |Ja|Ja|Nej|
|Blockera Bluetooth anslutning |Ja|Ja|Nej|

## <a name="additional-settings"></a>Ytterligare inställningar

Du kan ange följande ytterligare principinställningar med hjälp av PowerShell & Säkerhets- och efterlevnadscenter. Mer information finns i [Security & Compliance Center PowerShell.](/powershell/exchange/scc-powershell)

|**Ställa in namn**|**iOS 7.1 och senare**|**Android 5 och senare**|
|:-----|:-----|:-----|
|CameraEnabled|Ja|Ja|
|Regionratings|Ja|Nej|
|Filmratings|Ja|Nej|
|TVShowsRating |Ja|Nej|
|AppsRatings |Ja|Nej|
|AllowVoiceDialing |Ja|Nej|
|AllowVoiceAssistant |Ja|Nej|
|AllowAssistantWhileLocked  |Ja|Nej|
|AllowPassbookWhileLocked |Ja|Nej|
|MaxPasswordGracePeriod |Ja|Nej|
|PasswordQuality |Nej|Ja|
|SystemSecurityTLS  |Ja|Nej|
|WLANEnabled  |Nej|Nej|

## <a name="settings-supported-by-windows"></a>Inställningar som stöds av Windows

Du kan hantera Windows 10 genom att registrera dem som mobila enheter. När en tillämplig princip har distribuerats måste användare med Windows 10-enheter registrera sig i Basic Mobility and Security första gången de använder det inbyggda e-postprogrammet för att komma åt sin Microsoft 365-e-post (kräver Azure AD Premium-prenumeration).

Följande inställningar stöds för Windows 10 enheter som är registrerade som mobila enheter. Den här inställningen blockerar inte användare från att komma åt Microsoft 365 resurser.

### <a name="security-settings"></a>Säkerhetsinställningar

- Kräv ett alfanumeriskt lösenord

- Minsta lösenordslängd

- Antal inloggningsfel innan enheten rensas

- Minuter av inaktivitet innan enheten låses

- Lösenords giltighetstid (dagar)

- Kom ihåg lösenordshistorik och förhindra återanvändning

> [!NOTE]
> Följande inställningar som kontrollerar lösenord styr bara lokala Windows konton. Windows konton som tillhandahålls genom att ansluta till en domän eller Azure Active Directory påverkas inte av de här inställningarna.

### <a name="system-settings"></a>Systeminställningar

Blockera att diagnostikdata skickas från enheten.

### <a name="additional-settings"></a>Ytterligare inställningar

Du kan ange de här ytterligare principinställningarna med hjälp av PowerShell-cmdlets:

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>Radera en mobil enhet via fjärrenhet

Om en enhet försvinner eller blir stulen kan du ta bort känsliga organisationsdata och förhindra åtkomst till dina Microsoft 365-organisationsresurser genom att göra en rensning från Säkerhets- & och efterlevnadscenter > **Dataförlustskydd** Enhetshantering  >  . Du kan göra en selektiv rensning för att endast ta bort organisationsdata eller en fullständig rensning för att ta bort all information från en enhet och återställa den till fabriksinställningarna.

Mer information finns i Rensa [en mobil enhet i Basic Mobility and Security.](wipe-mobile-device.md)

## <a name="related-content"></a>Relaterat innehåll

[Översikt över Grundläggande rörlighet och säkerhet för Microsoft 365](overview.md) (artikel)\
[Skapa säkerhetsprinciper för enheter i Basic Mobility and Security](create-device-security-policies.md) (artikel)