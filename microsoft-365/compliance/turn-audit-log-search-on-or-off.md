---
title: Aktivera eller inaktivera granskningar
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Så här aktiverar eller inaktiverar du funktionen Granskningsloggsökning i Microsoft 365 efterlevnadscenter för att aktivera eller inaktivera administratörers möjlighet att söka i granskningsloggen.
ms.openlocfilehash: 457f453b001f71a095bc60932c8e0cebf46aa7b1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706670"
---
# <a name="turn-auditing-on-or-off"></a>Aktivera eller inaktivera granskningar

Granskningsloggning är som standard aktiverat för Microsoft 365 och Office 365 Enterprise-organisationer. Det omfattar även organisationer med prenumerationer på E3/G3 eller E5/G5. När granskning i efterlevnadscentret är aktiverad registreras användar- och administratörsaktiviteten från organisationen i granskningsloggen och behålls i 90 dagar och upp till ett år beroende på vilken licens som tilldelats användarna. Det kan dock finnas skäl för organisationen att inte registrera och behålla granskningsloggdata. I sådana fall kan en global administratör välja att inaktivera granskning i Microsoft 365.

> [!IMPORTANT]
> Om du inaktiverar granskning i Microsoft 365 kan du inte använda API:t för Office 365 hanteringsaktivitet eller Azure Sentinel för att komma åt granskningsdata för organisationen. Om du inaktiverar granskning genom att följa stegen i den här artikeln innebär det att inga resultat returneras när du söker i granskningsloggen med hjälp av Säkerhets- och efterlevnadscenter för & eller när du kör cmdleten **Search-UnifiedAuditLog** i Exchange Online PowerShell. Det innebär också att granskningsloggar inte är tillgängliga via API:t för Office 365 managementaktivitet eller Azure Sentinel.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Innan du aktiverar eller inaktiverar granskning

- Du måste ha tilldelats rollen Granskningsloggar i Exchange Online att aktivera eller inaktivera granskning i Microsoft 365 organisation. Som standard är den här rollen tilldelad rollgrupperna  Efterlevnadshantering och Organisationshantering på sidan Behörigheter Exchange administrationscentret. Globala administratörer i Microsoft 365 är medlemmar i rollgruppen Organisationshantering i Exchange Online. 

    > [!NOTE]
    > Användare måste ha tilldelats behörigheter i Exchange Online att aktivera eller inaktivera granskning. Om du tilldelar användarna rollen  Granskningsloggar på sidan Behörigheter i Säkerhets- & efterlevnadscenter kan de inte aktivera eller inaktivera granskning. Det beror på att den underliggande cmdleten är en Exchange Online PowerShell-cmdlet. 

- Stegvisa instruktioner för hur du söker i granskningsloggen finns i Söka i [granskningsloggen i Säkerhets- & Efterlevnadscenter.](search-the-audit-log-in-security-and-compliance.md) Mer information om API för hanteringsaktivitet Microsoft 365 finns i Komma [igång Microsoft 365 Management API:er.](/office/office-365-management-api/get-started-with-office-365-management-apis)

- Du kan kontrollera att granskning är aktiverad genom att köra följande kommando i Exchange Online PowerShell:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    Värdet för  `True` egenskapen  _UnifiedAuditLogIngestionEnabled_ anger att granskning är aktiverad. 

## <a name="turn-on-auditing"></a>Aktivera granskning

Om granskning inte är aktiverat för organisationen kan du aktivera den i efterlevnadscentret eller med hjälp av Exchange Online PowerShell. Det kan ta flera timmar efter att du har aktiverar granskning innan du kan returnera resultat när du söker i granskningsloggen.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Aktivera granskning med hjälp av efterlevnadscentret

1. Gå till <https://compliance.microsoft.com> och logga in.

2. I det vänstra navigeringsfönstret i Microsoft 365, klickar du på **Visa alla** och sedan på **Granska**.

   Om granskning inte är aktiverat för organisationen visas en banderoll där du uppmanas att börja spela in användar- och administratörsaktivitet.

   ![Banderoll på granskningssida](../media/AuditingBanner.png)

3. Klicka på **banderollen Starta inspelning av användar- och administratörsaktivitet.**

   Det kan ta upp till 60 minuter innan ändringen verkställs.

### <a name="use-powershell-to-turn-on-auditing"></a>Aktivera granskning med PowerShell

1. [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör följande PowerShell-kommando för att aktivera granskning i Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Ett meddelande visas om att det kan ta upp till 60 minuter innan ändringen verkställs.
  
## <a name="turn-off-auditing"></a>Inaktivera granskning

Du måste använda Exchange Online PowerShell för att inaktivera granskning.
  
1. [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör följande PowerShell-kommando för att inaktivera granskning.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Kontrollera att granskning är inaktiverat (inaktiverat) efter ett tag. Du kan göra det på två sätt:

    - I Exchange Online PowerShell kör du följande kommando:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      Värdet för  `False` egenskapen  _UnifiedAuditLogIngestionEnabled_ anger att granskning är inaktiverat.

    - Gå till **sidan Granskning** i Microsoft 365 kompatibilitetscenter.

      Om granskning inte är aktiverat för organisationen visas en banderoll där du uppmanas att börja spela in användar- och administratörsaktivitet.
