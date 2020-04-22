---
title: Hantera e-postanvändare i EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Att definiera e-postanvändare är en viktig del av hanteringen av Tjänsten Exchange Online Protection (EOP).
ms.openlocfilehash: 56827e29872c6a6ffd14821af8e2d9ea005ff20c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635586"
---
# <a name="manage-mail-users-in-eop"></a>Hantera e-postanvändare i EOP

Att definiera e-postanvändare är en viktig del av hanteringen av Tjänsten Exchange Online Protection (EOP). Det finns flera sätt att hantera användare i EOP:

- **Använd katalogsynkronisering för att hantera e-postanvändare:** Om företaget har befintliga användarkonton i en lokal Active Directory-miljö kan du synkronisera dessa konton till Azure Active Directory (AD), där en kopia av kontona lagras i molnet. När du synkroniserar dina befintliga användarkonton till Azure Active Directory kan du visa dessa användare i fönstret Mottagare i **Administrationscentret** för Exchange (EAC). Användning av katalogsynkronisering rekommenderas.

- **Använd EAC för att hantera e-postanvändare:** Lägg till och hantera e-postanvändare direkt i EAC. Detta är det enklaste sättet att lägga till e-postanvändare och är användbart för att lägga till en användare i taget.

- **Använd PowerShell för att hantera e-postanvändare:** Lägg till och hantera e-postanvändare i Exchange Online Protection PowerShell. Den här metoden är användbar när du vill lägga till flera poster och skapa skript.

> [!NOTE]
> Du kan lägga till användare i Microsoft 365-administrationscentret, men dessa användare kan inte användas som e-postmottagare.

## <a name="before-you-begin"></a>Innan du börjar

- Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Information om vilka behörigheter du behöver finns i posten "Användare, Kontakter och Rollgrupper" i [Funktionsbehörigheter i EOP](feature-permissions-in-eop.md).

- Tänk på att när du skapar e-postanvändare med hjälp av Exchange Online Protection PowerShell-cmdlets kan du stöta på begränsning.

- PowerShell-kommandona i det här avsnittet använder en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan resultaten av kommandona visas.

- Mer information om hur du använder Windows PowerShell för att ansluta till Exchange Online Protection finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Använda katalogsynkronisering för att hantera e-postanvändare

Det här avsnittet innehåller information om hur du hanterar e-postanvändare med hjälp av katalogsynkronisering.

**Anmärkningar**:

- Om du använder katalogsynkronisering för att hantera mottagarna kan du fortfarande lägga till och hantera användare i Microsoft 365-administrationscentret, men de synkroniseras inte med den lokala Active Directory. Detta beror på att katalogsynkronisering bara synkroniserar mottagare **från** den lokala Active Directory **till** molnet.

- Katalogsynkronisering rekommenderas för användning med följande funktioner:

  - **Outlook-listor med betrodda avsändare och blockerade avsändare**: När de synkroniseras med tjänsten har dessa listor företräde framför skräppostfiltrering i tjänsten. På så sätt kan användare hantera sina egna säkra avsändare och blockerade avsändarelistor per användare eller per domän.

  - **Katalogbaserad kantblockering (DBEB)**: Mer information om DBEB finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Slutanvändarens spam karantän:** För att komma åt slutanvändaren spam karantän, slutanvändare måste ha ett giltigt användar-ID och lösenord. EOP-kunder som skyddar lokala postlådor måste vara giltiga e-postanvändare.

  - **Regler för e-postflöde**: När du använder katalogsynkronisering överförs dina befintliga Active Directory-användare och -grupper automatiskt till molnet, och du kan sedan skapa regler för e-postflöde (kallas även transportregler) som riktar sig till specifika användare och/eller grupper utan att behöva lägga till dem manuellt via EAC eller Exchange Online Protection PowerShell. Observera att [dynamiska distributionsgrupper](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras via katalogsynkronisering.

Hämta nödvändiga behörigheter och förbereda för katalogsynkronisering enligt beskrivningen i [Vad är hybrididentitet med Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>Så här synkroniserar du användarkataloger med Azure Active Directory Connect (AAD Connect)

Om du vill synkronisera användare till Azure Active Directory (AAD) måste du först **aktivera katalogsynkronisering**enligt beskrivningen i [Azure AD Connect-synkronisering: Förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Nästa är installation och konfiguration av en lokal dator för att köra AAD Connect (om du inte redan har en - något värt att kontrollera i förväg). [När du konfigurerar AAD Connect, uttryckssättet,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) berättar du hur du konfigurerar och synkroniserar dina konton från lokala till Azure AD med AAD Connect.

Men innan du gör det arbetet, se till att [du uppfyller förutsättningarna](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)och [välj din installationstyp](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation). Den tidigare länken är till en kort artikel för expressinstallationer. Du kan också hitta artiklar om [anpassade installationer](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)eller [direktautentisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) om de behövs.

> [!IMPORTANT]
> När du är klar med konfigurationsguiden för Azure Active Directory Sync Tool skapas **MSOL_AD_SYNC-kontot** i Active Directory-skogen. Det här kontot används för att läsa och synkronisera din lokala Active Directory-information. För att katalogsynkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogsynkroniseringsservern är öppen.

När du har konfigurerat synkroniseringen måste du kontrollera att EOP synkroniseras korrekt. I EAC går du till **Mottagare** \> **Kontakter** och visa att listan över användare har synkroniserats korrekt från din lokala miljö.

## <a name="use-the-eac-to-manage-mail-users"></a>Använda EAC för att hantera e-postanvändare

Det här avsnittet innehåller information om hur du lägger till och hanterar e-postanvändare direkt i EAC.

### <a name="use-the-eac-to-add-a-mail-user"></a>Använda EAC för att lägga till en e-postanvändare

1. Skapa en e-postanvändare genom att gå till **Mottagare** \> **Kontakter** i EAC och klicka sedan på **Nytt +**.

2. På sidan **Ny e-postanvändare** anger du användarens information, inklusive följande:

   ****

   |**Egenskapen E-postanvändare**|**Beskrivning**|
   |:-----|:-----|
   |**Förnamn**, **Initialer**och **Efternamn**|Skriv användarens fullständiga namn i lämpliga rutor.|
   |**Visningsnamn**|Skriv ett namn med upp till 64 tecken. Som standard visar den här rutan namnen i rutorna **Förnamn,** **Initialer**och **Efternamn** om sådana finns. Visningsnamnet krävs.|
   |**Alias**|Skriv ett unikt alias med upp till 64 tecken för användaren. Alias krävs.|
   |**Extern e-postadress**|Skriv användarens externa e-postadress.|
   |**Användar-ID**|Ange det namn som e-postanvändaren ska använda för att logga in på tjänsten. Användarens inloggningsnamn består av ett användarnamn till vänster om at-symbolen (@) och ett suffix till höger. Vanligtvis är suffixet det domännamn som användarkontot finns i.|
   |**Nytt lösenord**|Skriv lösenordet som e-postanvändaren ska använda för att logga in på tjänsten. Kontrollera att lösenordet du anger uppfyller kraven för lösenordslängd, komplexitet och historik för den domän där du skapar användarkontot.|
   |**Bekräfta lösenord   **|Skriv in lösenordet igen för att bekräfta det.|

3. Klicka på **Spara** om du vill skapa den nya e-postanvändaren. Den nya användaren ska visas i listan över användare.

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a>Använda EAC för att redigera eller ta bort en e-postanvändare

- Gå till **Mottagare** \> **kontakter**i EAC. Klicka på den användare som du vill visa eller ändra **Edit** ![i listan](../../media/ITPro-EAC-EditIcon.gif) över användare och välj sedan ikonen Redigera redigera redigera för att uppdatera användarinställningarna efter behov. Du kan ändra användarens namn, alias eller kontaktinformation och du kan registrera detaljerad information om användarens roll i organisationen. Du kan också välja en användare](../../media/ITPro-EAC-RemoveIcon.gif) och sedan välja Ikonen Ta bort ta **bort** ![för att ta bort den.

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>Använda Exchange Online Protection PowerShell för att hantera e-postanvändare

Det här avsnittet innehåller information om hur du lägger till och hanterar e-postanvändare med hjälp av fjärr-Windows PowerShell.

### <a name="use-eop-powershell-to-add-a-mail-user"></a>Använda EOP PowerShell för att lägga till en e-postanvändare

I det här exemplet används cmdleten [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) för att skapa ett e-postaktiverat användarkonto för Jeffrey Zeng i EOP med följande information:

- Förnamnet är Jeffrey och efternamnet är Zeng.

- Namnet är Jeffrey och visningsnamnet är Jeffrey Zeng.

- Alias är Jeffreyz.

- Den externa e-postadressen är jzeng@tailspintoys.com.

- Inloggningsnamnet för Microsoft 365 är jeffreyz@contoso.onmicrosoft.com.

- Lösenordet är Pa $ $word1.

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

Om du vill kontrollera att detta fungerade kör du följande kommando för att visa information om den nya e-postanvändaren Jeffrey Zeng:

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

Detaljerad syntax- och parameterinformation finns i [Hämta användare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a>Använda EOP PowerShell för att redigera egenskaperna för en e-postanvändare

Använd cmdlets hämta mottagare och [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) för att visa eller ändra egenskaper för [e-postanvändare.](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)

I det här exemplet anges den externa e-postadressen för Pilar Pinilla.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

I det här exemplet anges egenskapen Företag för alla e-postanvändare till Contoso.

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Om du vill kontrollera att detta fungerade använder du cmdleten [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) för att verifiera ändringarna. (Observera att du kan visa flera egenskaper för flera e-postkontakter.)

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

I föregående exempel där egenskapen Företag angavs till Contoso för alla e-postanvändare kör du följande kommando för att verifiera ändringarna:

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> Denna cmdlet använder en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan cmdletens resultat är synliga.

### <a name="use-eop-powershell-to-remove-a-mail-user"></a>Använda EOP PowerShell för att ta bort en e-postanvändare

I det här exemplet används cmdleten [Ta bort EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) för att ta bort användaren Jeffrey Zeng:

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
Om du vill kontrollera att detta fungerade kör du cmdleten Hämta mottagare för att kontrollera att [e-postanvändaren](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) inte längre finns.

```PowerShell
Get-Recipient Jeffrey | Format-List
```
