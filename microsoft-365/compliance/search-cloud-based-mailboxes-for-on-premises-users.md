---
title: Söka efter Teams chattdata för lokala användare
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Använda eDiscovery-verktyg i Microsoft 365 till att söka efter och exportera Teams chattdata för lokala användare i en Exchange-hybridinstallation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311807"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Söka efter Teams chattdata för lokala användare

Om din organisation har en Exchange-hybridinstallation (eller om organisationen synkroniserar en lokal Exchange-organisation med Office 365) och har aktiverat Microsoft Teams, kan lokala användare använda Teams chattprogram för snabbmeddelanden. För molnbaserade användare sparas Teams chattdata (kallas även *1x1- eller 1xN-chattar*) i den primära molnbaserade postlådan. När en lokal användare använder Teams chattprogram kan deras chattmeddelanden inte lagras i den primära postlådan som finns lokalt. För att komma runt den här begränsningen har Microsoft släppt en ny funktion där ett molnbaserad lagringsområde skapas så att du kan använda eDiscovery-verktyg för att söka efter och exportera Teams chattdata för lokala användare.
  
Här är kraven och begränsningarna för att aktivera molnbaserad lagring för lokala användare:
  
- Användarkontona i den lokala katalogtjänsten (till exempel Active Directory) måste synkroniseras med katalogtjänsten Azure Active Directory i Microsoft 365. Det innebär att ett e-postkonto för användaren skapas i Microsoft 365 och kopplas till en användare vars primära postlåda finns i den lokala organisationen.

- Den användare vars primära postlåda finns i den lokala organisationen måste tilldelas en Microsoft Teams-licens och en licens för minst Exchange Online, alternativ 1.

- Om din organisation inte har en Exchange-hybridinstallation, måste du synkronisera ditt lokala Exchange-schema till Azure Active Directory. Om du inte gör det kan du riskera att skapa duplicerade molnbaserade postlådor i Exchange Online för användare som har en postlåda i din lokala Exchange-organisation.

- Det är bara Teams chattdata som är associerad med en lokal användare som lagras i det molnbaserade lagringsutrymmet. Den lokala användaren kan inte komma åt lagringsutrymmet på något sätt.

> [!NOTE]
> Teams kanalkonversationer lagras alltid i den molnbaserade postlådan som är kopplad till gruppen, vilket innebär att du kan söka efter kanalkonversationer. Mer information om hur du söker efter Teams kanalkonversationer finns i [Söka i Microsoft Teams och Microsoft 365-grupper](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Så här fungerar det

Om en Microsoft Teams-aktiverad användare har en lokal postlåda och användarens användarkonto/identitet har synkroniserats till molnet, skapar Microsoft molnbaserad lagring som den lokala användarens 1xN Teams chattdata kan associeras med. Teams chattdata för lokala användare indexeras för sökning. Det innebär att du kan använda innehållssökning (och sökningar som är kopplade till Core eDiscovery- och Advanced eDiscovery-fall) för att söka, förhandsgranska och exportera Teams chattdata för lokala användare. Du kan också använda cmdletar för **\*ComplianceSearch** i Säkerhets- och efterlevnadscenter för PowerShell till att söka efter Teams chattdata för lokala användare.
  
Följande bild visar arbetsflödet för hur Teams chattdata för lokala användare är tillgänglig för sökning, förhandsgranskning och export.
  
![Molnbaserad lagring för lokala användare i Microsoft Teams](../media/EHAMShard1.png)
  
Utöver den här funktionen kan du även använda eDiscovery-verktyg till att söka, förhandsgranska och exportera Teams-innehåll på den molnbaserade SharePoint-webbplatsen och i Exchange-postlådan som är kopplad till varje Microsoft Team och 1xN Teams chattdata i Exchange Online-postlådan för molnbaserade användare.

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a>Den här funktionen stöds i sökverktygen för innehållssökning och Core eDiscovery

Följande gränssnittselement i Innehållssökning samt i sökverktyget är kopplade till Core eDiscovery-fall i Microsoft 365 Efterlevnadscenter:
  
- Kryssrutan **Lägg till appinnehåll för lokala användare** visas på guidesidan **Platser** i verktyget Innehållssökning och är markerad som standard. Låt den här kryssrutan vara markerad för att inkludera det molnbaserade lagringsutrymmet för lokala användare vid innehållssökning.

    ![Kryssrutan för "Lägg till appinnehåll från Office för lokala användare" läggs till i användargränssnittet för Innehållssökning](../media/EHAMShardCheckBox.png)
  
- Du kan söka efter lokala användare när du väljer att söka efter specifika användare.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Söker efter chattinnehåll från Teams för lokala användare

Så här använder du innehållssökning i Microsoft 365 Efterlevnadscenter till att söka efter Teams chattdata för lokala användare.
  
1. I Microsoft 365 Efterlevnadscenter går du till **Innehållssökning**.

2. På fliken **Sökningar** klickar du på **Ny sökning** och anger den nya sökningen.

3. På sidan **Platser** ställer du in **På** för reglaget för Exchange-postlådor. Se till att kryssrutan **Lägg till appinnehåll för lokala användare** visas och är markerad som standard.

4. För att söka efter innehåll från Teams för specifika användare väljer du **Välj användare, grupp eller team** och väljer specifika användare som ska ingå i sökningen. För att söka efter innehåll från Teams för alla användare, inklusive lokala användare, klickar du på **Nästa**.

5. På sidan **Definiera sökvillkor** skapar du en nyckelordsfråga och lägger till villkor i sökfrågan om det behövs. För att endast söka efter data för teamchattar kan du lägga till följande fråga i rutan **Nyckelord**:

    ```text
    kind:im AND kind:microsoftteams
    ```

6. Spara och kör sökningen. Alla sökresultat för lokala användare kan förhandsgranskas på samma sätt som i andra sökresultat. Du kan också exportera sökresultatet (inklusive Teams chattdata) till en PST-fil. Mer information finns i:

    - [Skapa en sökning](content-search.md)

    - [Förhandsgranska sökresultat](preview-ediscovery-search-results.md)

    - [Exportera sökresultaten](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>Använda PowerShell till att söka efter chattdata för Teams för lokala användare

Du kan använda cmdletarna **New-ComplianceSearch** och **Set-ComplianceSearch** i Säkerhets- och efterlevnadscenter för PowerShell till att söka efter Teams chattdata för lokala användare. Som tidigare beskrivits behöver du inte skicka någon supportbegäran om att använda PowerShell till att söka efter Teams chattdata för lokala användare.
  
1. [Ansluta till Säkerhets- och efterlevnadscenter i PowerShell](/powershell/exchange/connect-to-scc-powershell).

2. Kör följande PowerShell-kommando för att skapa en innehållssökning som söker efter Teams chattdata för lokala användare.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    Parametern *IncludeUserAppContent* används för att ange den molnbaserade lagringen för den eller de användare som anges av parametern *ExchangeLocation*. Med *AllowNotFoundExchangeLocationsEnabled* kan du söka i det molnbaserade lagringsutrymmet efter lokala användare. När du använder `$true`-värdet för den här parametern verifierar inte sökningen att postlådan finns innan den körs. Det här krävs för att kunna söka i den molnbaserade lagringen efter lokala användare, eftersom den molnbaserade lagringen inte fungerar som en vanlig molnbaserad postlåda.

    Följande exempel söker efter chattar i Teams som innehåller nyckelordet "redstone" i den molnbaserade lagringen för Sara Davis, som är en lokal användare i Contoso-organisationen.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   När du har skapat en sökning använder du cmdleten **Start-ComplianceSearch** för att köra sökningen.
  
Mer information om hur du använder dessa cmdletar finns i:
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Kända problem

- För närvarande kan du söka efter, förhandsgranska och exportera Teams chattdata för lokala användare. Du kan också parkera Teams chattdata för en lokal användare som är kopplad till ett Core eller Advanced eDiscovery-ärende och tillämpa en kvarhållningsprincip för Teams chattar eller kanalmeddelanden för lokala användare. För närvarande kan du dock inte tillämpa en kvarhållningsprincip för andra innehållsplatser (till exempel Exchange-postlådor och SharePoint-webbplatser) för lokala användare.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

**Måste jag skicka en supportbegäran för att söka efter chattmeddelanden för lokala användare?**

Nej. Den här funktionen är aktiverad som standard för alla organisationer. Tidigare behövde du kontakta Microsoft Support, men det behöver du inte längre.
  
 **Kan eDiscovery-verktyg hitta äldre Teams chattdata för lokala användare innan funktionen aktiverades som standard för alla organisationer?**
  
Microsoft började lagra Teams chattdata för lokala användare den 31 januari 2018. Om identiteten för en lokal Teams-användare har synkroniserats mellan din lokala Active Directory och Azure Active Directory i Microsoft 365 efter det här datumet lagras deras Teams chattdata i molnet och är sökbar med eDiscovery-verktyg.

 **Behöver lokala användare en licens för att kunna lagra Teams chattdata i molnet?**
  
Ja. Om Teams chattdata ska lagras för en lokal användare i en molnbaserad lagring, måste användaren tilldelas en Microsoft Teams-licens och en licens för Exchange Online i Office 365 (eller Microsoft 365).

**Var finns den molnbaserade lagringen för lokala användare?**
  
Teams chattdata lagras på den önskade dataplatsen (PDL) för en lokal användare. PDL används både i Single-Geo- och Multi-Geo-miljöer. Mer information finns i [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

**Finns det någon risk att förlora Teams chattdata om användarens lokala postlåda migreras till molnet?**
  
Nej. När du migrerar en lokal användares primära postlåda till molnet migreras Teams chattdata för användaren till den nya molnbaserade primära postlådan.
  
 **Kan jag tillämpa kvarhållningsprinciper för eDiscovery på lokala användare?**
  
Ja. Du kan tillämpa eDiscovery-kvarhållningsprinciper för Teams chattar och kanalmeddelanden för lokala användare. Om du däremot vill bevara eller behålla Teams-innehåll för lokala användare måste den lokala användaren tilldelas en licens för Exchange Online, alternativ 2.
