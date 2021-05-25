---
title: Hantera Meddelandekryptering i Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: När du är klar med att konfigurera Meddelandekryptering i Office 365 (OME) kan du lära dig hur du anpassar distributionen på flera olika sätt.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650990"
---
# <a name="manage-office-365-message-encryption"></a>Hantera Meddelandekryptering i Office 365

När du är klar med konfigureringen Meddelandekryptering i Office 365 (OME) kan du anpassa konfigurationen av distributionen på flera olika sätt. Du kan till exempel konfigurera om du vill aktivera  lösenord för endast en gång, visa knappen Kryptera i Outlook på webben och mycket mer. Uppgifterna i den här artikeln beskriver hur.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Hantera om mottagarna av Google-, Yahoo- och Microsoft-konton kan använda dessa konton för att logga in på Meddelandekryptering i Office 365 portalen

När du konfigurerat Meddelandekryptering i Office 365 funktioner kan användare i organisationen skicka meddelanden till mottagare som finns utanför organisationen. Om mottagaren använder ett *socialt ID,* till exempel ett Google-konto, Yahoo-konto eller Microsoft-konto, kan mottagaren logga in på OME-portalen med ett socialt ID. Om du vill kan du välja att inte tillåta att mottagare använder sociala IDs för att logga in på OME-portalen.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Så här hanterar du om mottagare kan använda sociala IDs för att logga in på OME-portalen
  
1. [Anslut att Exchange Online använda Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör cmdleten Set-OMEConfiguration Med parametern SocialIdSignIn enligt följande:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Om du till exempel vill inaktivera sociala ID:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Så här aktiverar du sociala ID:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Hantera användningen av lösenordskoder för Meddelandekryptering i Office 365 portalen

Om mottagaren av ett meddelande som krypteras med OME inte använder Outlook, oavsett vilket konto som används av mottagaren, får mottagaren en tidsbegränsad webbvylänk som gör att mottagaren kan läsa meddelandet. Den här länken innehåller en kod för ett lösenord. Som administratör kan du bestämma om mottagarna ska kunna logga in på OME-portalen med hjälp av koder som du använder som lösenord.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Så här hanterar du om OME genererar koder för en gång
  
1. Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör Set-OMEConfiguration-cmdleten med parametern OTPEnabled:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   Så här inaktiverar du till exempel lösenord för en gång:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Så här aktiverar du lösenord för en gång:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Hantera visningen av knappen Kryptera i Outlook på webben

Som administratör kan du hantera om den här knappen ska visas för slutanvändare.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Så här hanterar du om knappen Kryptera visas Outlook på webben
  
1. Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör cmdleten Set-IRMConfiguration -SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Om du till exempel vill inaktivera **knappen** Kryptera:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   Så här aktiverar du **knappen** Kryptera:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Aktivera dekryptering av e-postmeddelanden på tjänstsidan för e-postanvändare i iOS-e-postprogrammet

E-postprogrammet i iOS kan inte dekryptera meddelanden som skyddas med Meddelandekryptering i Office 365. Som administratör Microsoft 365 kan du använda dekryptering på tjänstsidan för meddelanden som levereras till e-postprogrammet i iOS. När du väljer att dekryptera på tjänstsidan skickar tjänsten en dekrypterad kopia av meddelandet till iOS-enheten. En dekrypterad kopia av meddelandet lagras på klientenheten. Meddelandet behåller även information om användningsrättigheter även om e-postappen i iOS inte tillämpar användningsrättigheter på klientsidan för användaren. Användaren kan kopiera eller skriva ut meddelandet även om de inte ursprungligen har behörighet att göra det. Men om användaren försöker slutföra en åtgärd som kräver att Microsoft 365-e-postservern, till exempel vidarebefordrar meddelandet, tillåter servern inte åtgärden om användaren inte ursprungligen har rätt att göra det. Men slutanvändarna kan komma runt användningsbegränsningen Vidarebefordra inte genom att vidarebefordra meddelandet från ett annat konto i e-postprogrammet i iOS. Oavsett om du anger dekryptering av e-post på tjänstsidan kan inte bifogade filer i krypterad och rättighetsskyddad e-post visas i e-postprogrammet i iOS.
  
Om du väljer att inte tillåta att dekrypterade meddelanden skickas till användare i iOS-e-postprogrammet får användarna ett meddelande om att de inte har behörighet att visa meddelandet. Som standard är dekryptering av e-postmeddelanden inte aktiverat på tjänstsidan.
  
Mer information och en vy över klientupplevelsen finns i Visa [krypterade](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)meddelanden på din iPhone eller iPad .
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Hantera om användare av iOS-e-postprogram kan visa meddelanden som skyddas av Meddelandekryptering i Office 365
  
1. Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör Set-ActiveSyncOrganizations med parametern AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Om du till exempel vill konfigurera tjänsten för att dekryptera meddelanden innan de skickas till oaktiverade appar som e-postprogrammet i iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Om du vill konfigurera tjänsten så att dekrypterade meddelanden inte skickas till oaktiverade appar:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Enskilda postlådeprinciper (OWA/ActiveSync) åsidosätter de här inställningarna (dvs. om -IRMEnabled är inställt på Falskt inom respektive OWA-postlådeprincip eller ActiveSync-postlådeprincip, gäller inte de här konfigurationerna).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Aktivera dekryptering av e-postbilagor på tjänstsidan för e-postklienter i webbläsaren

När du använder Office 365 krypteras bifogade filer automatiskt. Som administratör kan du använda dekryptering på tjänstsidan för e-postbilagor som användare laddar ned från en webbläsare.
  
När du använder dekryptering på tjänstsidan skickar tjänsten en dekrypterad kopia av filen till enheten. Meddelandet krypteras fortfarande. Den bifogade filen för e-post behåller även information om användningsrättigheter även om webbläsaren inte gäller användarens användningsrättigheter på klientsidan. Användaren kan kopiera eller skriva ut den bifogade filen i ett e-postmeddelande även om de inte ursprungligen har behörighet att göra det. Men om användaren försöker slutföra en åtgärd som kräver att Microsoft 365-e-postservern, till exempel vidarebefordrar den bifogade filen, tillåter servern inte åtgärden om användaren inte ursprungligen har rätt att göra det.
  
Oavsett om du krypterar bifogade filer på tjänstsidan kan användarna inte visa bifogade filer i krypterad och rättighetsskyddad e-post i iOS-e-postprogrammet.
  
Om du väljer att inte tillåta dekrypterade e-postbilagor, vilket är standard, får användarna ett meddelande om att de inte har behörighet att visa den bifogade filen.
  
Mer information om hur Microsoft 365 implementerar kryptering för e-postmeddelanden och e-postbilagor med alternativet Encrypt-Only finns [i Alternativet Endast kryptering för e-postmeddelanden.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Hantera om e-postbilagor dekrypteras vid nedladdning från en webbläsare
  
1. Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör cmdleten Set-IRMConfiguration med parametern DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Om du till exempel vill konfigurera tjänsten för att dekryptera e-postbilagor när en användare hämtar dem från en webbläsare:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   Så här konfigurerar du tjänsten för att lämna krypterade e-postbilagor som de är vid nedladdning:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Kontrollera att alla externa mottagare använder OME-portalen för att läsa krypterad e-post

Du kan använda anpassade varumärkesmallar för att tvinga mottagare att ta emot ett omslagsmeddelande som dirigerar dem till att läsa krypterad e-post i OME-portalen i stället för att använda Outlook eller Outlook på webben. Det kan vara bra att göra det om du vill ha större kontroll över hur mottagarna använder sin e-post. Om externa mottagare till exempel visar e-post i webbportalen kan du ange ett utgångsdatum för e-postmeddelandet och återkalla e-postmeddelandet. De här funktionerna stöds endast via OME-portalen. Du kan använda alternativen Kryptera och Vidarebefordra inte när du skapar e-postflödesregler.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Använda en anpassad mall för att tvinga alla externa mottagare att använda OME-portalen och för krypterad e-post

1. Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör cmdleten New-TransportRule-cmdleten:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    där:

   - `mail flow rule name` är det namn du vill använda för den nya e-postflödesregeln.

   - `option name` är antingen `Encrypt` eller `Do Not Forward` .

   - `template name` är namnet du gav mallen för anpassade profilering, till exempel `OME Configuration` .

   Om du vill kryptera all extern e-post med mallen "OME-konfiguration" och använda Encrypt-Only alternativet:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Om du vill kryptera all extern e-post med mallen "OME-konfiguration" och använda alternativet Vidarebefordra inte:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Anpassa utseendet på e-postmeddelanden och OME-portalen

Detaljerad information om hur du kan anpassa OME för organisationen finns i [Lägga till företagets varumärke i krypterade meddelanden.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="disable-the-new-capabilities-for-ome"></a>Inaktivera de nya funktionerna för OME

Vi hoppas att det inte blir så, men om du behöver det är det mycket enkelt att inaktivera de nya funktionerna för OME. Först måste du ta bort alla e-postflödesregler som du har skapat och som använder de nya OME-funktionerna. Information om hur du tar bort e-postflödesregler finns [i Hantera e-postflödesregler.](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) Utför sedan dessa steg i Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>Inaktivera de nya funktionerna för OME
  
1. Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Om du  har aktiverat knappen Kryptera i Outlook på webben inaktiverar du den genom att köra cmdleten Set-IRMConfiguration med parametern SimplifiedClientAccessEnabled. Annars hoppar du över det här steget.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Inaktivera de nya funktionerna för OME genom att köra cmdleten Set-IRMConfiguration med parametern AzureRMSLicensingEnabled inställd på falskt:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
