---
title: Möjligheter till grundläggande mobilitet och säkerhet
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
description: Grundläggande mobilitet och säkerhet kan hjälpa dig att skydda och hantera mobila enheter.
ms.openlocfilehash: aed4f4c2d252e487d24496ac00f3de24bc57ab55
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545902"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Möjligheter till grundläggande mobilitet och säkerhet

Med grundläggande mobilitet och säkerhet kan du skydda och hantera mobila enheter som iPhone, iPad, Android och Windows-telefoner som används av licensierade Microsoft 365-användare i din organisation. Du kan skapa principer för mobila enheter med inställningar som hjälper dig att kontrol lera åtkomsten till organisationens Microsoft 365-e-post och dokument för mobila enheter och program som stöds. Om en enhet går förlorad eller stjäls kan du fjärrrensa enheten för att ta bort känslig organisationsinformation.

## <a name="supported-devices"></a>Enheter som stöds

Du kan använda grundläggande mobilitet och säkerhet för att skydda och hantera följande enheter.

- iOS 11,0 eller senare
    
- Android 5,0 eller senare version<sup>3</sup>
    
- Windows 8,1<sup>1</sup>
    
- Windows 8,1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 Mobile<sup>2</sup>   

<sup>1</sup> Åtkomst kontroll för Windows 8,1 RT-enheter är begränsad till Exchange ActiveSync.

<sup>2</sup> Åtkomst kontroll för Windows 8,1 RT-enheter är begränsad till Exchange ActiveSync.
För åtkomst kontroll för Windows 10 krävs en prenumeration som inkluderar Azure AD Premium och enheten måste vara ansluten till Azure Active Directory.

<sup>3</sup> Åtkomst kontroll för Windows 8,1 RT-enheter är begränsad till Exchange ActiveSync.
Efter juni 2020 kan Android-versioner senare än 9 inte hantera lösen ords inställningar förutom för Samsung KNOX-enheter.

>[!NOTE]
>Enheter som redan har registrerats med tidigare OS-versioner fortsätter att fungera trots att funktionerna kan ändras utan förvarning.

Om personer i din organisation använder mobila enheter som inte stöds av grundläggande mobilitet och säkerhet kan det vara bra att blockera program åtkomst för Exchange ActiveSync till Microsoft 365-e-post för dessa enheter så att organisationens data blir säkrare. Anvisningar för hur du blockerar Exchange ActiveSync finns i [Hantera åtkomst inställningar för enheter i grundläggande mobilitet och säkerhet](manage-device-access-settings.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Åtkomst kontroll för Microsoft 365 e-post och dokument

De program som stöds för de olika typerna av mobila enheter i följande tabell uppmanar användare att registrera sig för grundläggande mobilitet och säkerhet, där det finns en ny hanterings princip för mobila enheter som gäller för en användares enhet och användaren inte har registrerat enheten tidigare. Om en användares enhet inte följer någon princip, beroende på hur du ställer in principen, kan en användare hindras från att få åtkomst till Microsoft 365-resurser i de här apparna, eller så kan de ha Access men Microsoft 365 rapporterar en policy överträdelse.

|**Produkt**|**iOS 10,0 eller senare**|**Android 5,0 eller senare**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync inkluderar inbyggd e-post och tredjepartsprogram, till exempel TouchDown, som använder Exchange ActiveSync version 14,1 eller senare. |Program |E-post |
|**Office**   och **OneDrive för företag** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**På telefoner och surfplattor**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Endast på telefoner:** <br/> Office Mobile |

>[!NOTE]
- >Stöd för iOS 10,0 och senare versioner inkluderar iPhone-och iPad-enheter.
- >Hantering av Black Berry OS-enheter stöds inte av mobila enheter som hanteras av Microsoft 365. Använda Black Berry Business Cloud Services (BBCS) från Black Berry för att hantera Black Berry OS-enheter. Black Berry-enheter med Android OS stöds som vanliga Android-enheter
- >Användare uppmanas inte att registrera sig och kommer inte att blockeras eller rapporteras för policy brott om de använder mobilen för att komma åt Microsoft 365 SharePoint-webbplatser, dokument i Office Online eller via e-post i Outlook Web App.
    
Följande diagram visar vad som händer när en användare med en ny enhet loggar in i ett program som har stöd för åtkomst kontroll med grundläggande mobilitet och säkerhet. Användaren blockeras från att få åtkomst till Microsoft 365-resurser i appen tills de registrerar sina enheter.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Grundläggande åtkomst kontroll för rörlighet och säkerhet":::

Obs! principer och åtkomst regler som har skapats i MDM för Microsoft 365 Business Standard åsidosätter Exchange ActiveSync-principer för mobila enheter och åtkomst regler för enheter som skapats i administrations centret för Exchange. När en enhet har registrerats i MDM för Microsoft 365 Business Standard, ignoreras alla mobila enheter för Exchange ActiveSync-postlådor eller enhets åtkomst för enheten. Mer information om Exchange ActiveSync finns i [Exchange ActiveSync i Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="policy-settings-for-mobile-devices"></a>Princip inställningar för mobila enheter

Om du skapar en princip för att blockera åtkomst med vissa inställningar aktiverade hindras användarna från att få åtkomst till Microsoft 365-resurser när ett program som stöds visas i [åtkomst kontroll för Microsoft 365 e-post och dokument](capabilities.md). 

De inställningar som kan hindra användare från att komma åt Microsoft 365-resurser är i följande avsnitt:

- Säkerhet
    
- Kryptering
    
- Jail trasig
    
- Hanterad e-postprofil  

Följande diagram visar till exempel vad som händer när en användare med en registrerad enhet inte är kompatibel med en säkerhets inställning i en hanterings princip för mobila enheter som gäller för enheten. Användaren loggar in i ett program som har stöd för åtkomst kontroll med grundläggande mobilitet och säkerhet. De hindras från att använda Microsoft 365-resurser i appen förrän deras enheter uppfyller säkerhets inställningen.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Grundläggande meddelanden om mobilitet och säkerhet":::

I följande avsnitt visas de princip inställningar du kan använda för att skydda och hantera mobila enheter som ansluter till din Microsoft 365-organisation.

## <a name="security-settings"></a>Säkerhets inställningar

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|**Samsung KNOX**|
|:-----|:-----|:-----|:-----|
|Kräv lösen ord|Ja|Ja|Ja|
|Förhindra enkelt lösen ord|Ja|Nej|Nej|
|Kräva ett alfanumeriskt lösen ord|Ja|Nej|Nej|
|Minsta längd på lösen ord |Ja|Ja|Ja|
|Antal misslyckade inloggnings försök innan enheten rensas |Ja|Ja|Ja|
|Minuters inaktivitet innan enheten är låst |Ja|Ja|Ja|
|Lösen ordet upphör (dagar) |Ja|Ja|Ja|
|Kom ihåg lösen ords historik och förhindra åter användning |Ja|Ja|Ja|

## <a name="encryption-settings"></a>Krypterings inställningar 

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|**Samsung KNOX**|
|:-----|:-----|:-----|:-----|
|Kräv data kryptering på enheter<sup>1</sup> |Nej|Ja|Ja|

<sup>1</sup> Med Samsung KNOX kan du även kräva kryptering på lagrings kort. 

## <a name="jail-broken-setting"></a>Jail trasig inställning 

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|**Samsung KNOX**|
|:-----|:-----|:-----|:-----|
|Enheten kan inte Jail vara trasig eller rotad |Ja|Ja|Ja|

## <a name="managed-email-profile-option"></a>Alternativet hanterad e-postprofil 

Följande alternativ kan hindra användare från att komma åt sin Microsoft 365-e-post om de använder en manuellt skapad e-postprofil. Användare på iOS-enheter måste ta bort sin manuellt skapade e-postprofil innan de får åtkomst till deras e-post. När han eller hon tagit bort profilen skapas en ny profil automatiskt på enheten. Instruktioner om hur slutanvändare får till gång till kompatibilitet finns i [ett befintligt e-postkonto](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|**Samsung KNOX**|
|:-----|:-----|:-----|:-----|
|E-postprofil hanteras |Ja|Nej|Nej|

## <a name="cloud-settings"></a>Moln inställningar 

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|**Samsung KNOX**|
|:-----|:-----|:-----|:-----|
|Kräv krypterad säkerhets kopiering |Ja|Nej|Nej|
|Blockera säkerhets kopiering av moln |Ja|Nej|Nej|
|Blockera synkronisering av dokument |Ja|Nej|Nej|
|Blockera Fotosynkronisering  |Ja|Nej|Nej|
|Tillåt Google-säkerhetskopiering  |Saknas|Nej|Ja|
|Tillåt automatisk synkronisering av Google-konto  |Saknas|Nej|Ja|

## <a name="system-settings"></a>Systeminställningar 

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|**Samsung KNOX**|
|:-----|:-----|:-----|:-----|
|Blockera skärmdump |Ja|Nej|Ja|
|Blockera att skicka diagnostikdata från enheten |Ja|Nej|Ja|

## <a name="application-settings"></a>Program inställningar 

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|**Samsung KNOX**|
|:-----|:-----|:-----|:-----|
|Blockera video konferenser på enhet |Ja|Nej|Nej|
|Blockera åtkomst till program lagring |Ja|Nej|Ja|
|Kräv lösen ord vid åtkomst till program arkivet |Nej|Ja|Ja|

## <a name="device-capabilities-settings"></a>Inställningar för enhets funktioner 

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|**Samsung KNOX**|
|:-----|:-----|:-----|:-----|
|Blockera anslutning med flyttbart lagrings utrymme |Ja|Ja|Nej|
|Blockera Bluetooth-anslutning |Ja|Ja|Nej|

## <a name="additional-settings"></a>Ytterligare inställningar

Du kan ange följande princip inställningar genom att använda säkerhets & kompatibilitetskontroll för PowerShell-cmdletar. Mer information finns i [säkerhets & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).

|**Ställa in namn**|**iOS 7,1 och senare**|**Android 5 och senare**|
|:-----|:-----|:-----|
|CameraEnabled|Ja|Ja|
|RegionRatings|Ja|Nej|
|MoviesRatings|Ja|Nej|
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

Du kan hantera Windows 10-enheter genom att registrera dem som mobila enheter. När en tillämplig princip har distribuerats måste användare med Windows 10-enheter registrera sig i grundläggande mobilitet och säkerhet första gången de använder den inbyggda e-postappen för att få åtkomst till Microsoft 365-e-post (kräver Azure AD Premium-prenumeration).

Följande inställningar stöds för Windows 10-enheter som är registrerade som mobila enheter. Dessa inställningar hindrar inte användarna från att få åtkomst till Microsoft 365-resurser.

### <a name="security-settings"></a>Säkerhets inställningar

- Kräva ett alfanumeriskt lösen ord

- Minsta längd på lösen ord
    
- Antal misslyckade inloggnings försök innan enheten rensas
    
- Minuters inaktivitet innan enheten är låst
    
- Lösen ordet upphör (dagar)
    
- Kom ihåg lösen ords historik och förhindra åter användning   

>[!NOTE]
>Följande inställningar reglerar lösen ord endast lokala Windows-konton. Windows-konton som tillhandahålls via Anslut till en domän eller Azure Active Directory påverkas inte av de här inställningarna.

### <a name="system-settings"></a>Systeminställningar

Blockera att skicka diagnostikdata från enhet.

### <a name="additional-settings"></a>Ytterligare inställningar

Du kan ange följande princip inställningar genom att använda PowerShell-cmdletar:

- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus   

- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    

## <a name="remotely-wipe-a-mobile-device"></a>Rensa en mobil enhet på en fjärrdator

Om en enhet försvinner eller blir stulen kan du ta bort känslig organisations data och förhindra åtkomst till dina Microsoft 365-organisations resurser genom att göra en rensning från säkerhets & Compliance Center > hantering av **data förlust**  >  **Device management**. Du kan göra en selektiv rensning för att enbart ta bort organisations data eller en fullständig rensning för att ta bort all information från en enhet och återställa den till fabriks inställningarna.

Mer information finns i [Rensa en mobil enhet i grundläggande mobilitet och säkerhet](wipe-mobile-device.md).

## <a name="related-topics"></a>Relaterade ämnen

[Översikt över grundläggande mobilitet och säkerhet för Microsoft 365](overview.md)

[Skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies.md)