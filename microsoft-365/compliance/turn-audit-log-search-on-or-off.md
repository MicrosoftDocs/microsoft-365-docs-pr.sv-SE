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
description: Så här aktiverar eller inaktiverar du funktionen Granskningsloggsökning i Microsoft 365 Efterlevnadscenter för att aktivera eller inaktivera administratörs möjlighet att söka i granskningsloggen.
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341502"
---
# <a name="turn-auditing-on-or-off"></a>Aktivera eller inaktivera granskningar

Granskningsloggning är som standard aktiverat för Microsoft 365 och Office 365 Enterprise-organisationer. När granskning i Microsoft 365 Efterlevnadscenter är aktiverad registreras användar- och administratörsaktiviteten från organisationen i granskningsloggen och behålls i 90 dagar och upp till ett år beroende på vilken licens som tilldelats användarna. Det kan dock finnas skäl för organisationen att inte registrera och behålla granskningsloggdata. I sådana fall kan en global administratör välja att inaktivera granskning i Microsoft 365.

När du inställningar för Microsoft 365 eller Office 365 organisation kan du kontrollera organisationens granskningsstatus. Anvisningar finns i avsnittet [Kontrollera organisationens granskningsstatus i](#verify-the-auditing-status-for-your-organization) den här artikeln.

> [!IMPORTANT]
> Om du inaktiverar granskning i Microsoft 365 kan du inte använda API:t för Office 365 hanteringsaktivitet eller Azure Sentinel för att komma åt granskningsdata för organisationen. Om du inaktiverar granskning genom att följa stegen i den här artikeln innebär det att inga resultat returneras när du söker i granskningsloggen med hjälp av Microsoft 365 Efterlevnadscenter eller när du kör cmdleten **Search-UnifiedAuditLog** i Exchange Online PowerShell. Det innebär också att granskningsloggar inte är tillgängliga via API:t för Office 365 managementaktivitet eller Azure Sentinel.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Innan du aktiverar eller inaktiverar granskning

- Du måste ha tilldelats rollen Granskningsloggar i Exchange Online att aktivera eller inaktivera granskning i Microsoft 365 organisation. Som standard är den här rollen tilldelad rollgrupperna  Efterlevnadshantering och Organisationshantering på sidan Behörigheter Exchange administrationscentret. Globala administratörer i Microsoft 365 är medlemmar i rollgruppen Organisationshantering i Exchange Online.

    > [!NOTE]
    > Användare måste ha tilldelats behörigheter i Exchange Online att aktivera eller inaktivera granskning. Om du tilldelar användarna rollen  Granskningsloggar på sidan Behörigheter i Microsoft 365 Efterlevnadscenter kan de inte aktivera eller inaktivera granskning. Det beror på att den underliggande cmdleten är en Exchange Online PowerShell-cmdlet.

- Stegvisa instruktioner för hur du söker i granskningsloggen finns [i Söka i granskningsloggen.](search-the-audit-log-in-security-and-compliance.md) Mer information om API för hanteringsaktivitet Microsoft 365 finns i Komma [igång Microsoft 365 Management API:er.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="verify-the-auditing-status-for-your-organization"></a>Kontrollera organisationens granskningsstatus

Du kan kontrollera att granskning är aktiverad för organisationen genom att köra följande kommando i [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

Värdet för `True` egenskapen  _UnifiedAuditLogIngestionEnabled_ anger att granskning är aktiverad. Värdet för `False` anger att granskning inte är aktiverat.

## <a name="turn-on-auditing"></a>Aktivera granskning

Om granskning inte är aktiverat för organisationen kan du aktivera den i Microsoft 365 Efterlevnadscenter eller med hjälp Exchange Online PowerShell. Det kan ta flera timmar efter att du har aktiverar granskning innan du kan returnera resultat när du söker i granskningsloggen.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Aktivera granskning med hjälp av efterlevnadscentret

1. Gå till <https://compliance.microsoft.com> och logga in.

2. Klicka på Granska i det vänstra Microsoft 365 Efterlevnadscenter på **fliken Granska.**

   Om granskning inte är aktiverat för organisationen visas en banderoll där du uppmanas att börja spela in användar- och administratörsaktivitet.

   ![Banderoll på granskningssida](../media/AuditingBanner.png)

3. Klicka på **banderollen Starta inspelning av användar- och administratörsaktivitet.**

   Det kan ta upp till 60 minuter innan ändringen verkställs.

### <a name="use-powershell-to-turn-on-auditing"></a>Aktivera granskning med PowerShell

1. [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör följande PowerShell-kommando för att aktivera granskning.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Ett meddelande visas om att det kan ta upp till 60 minuter innan ändringen verkställs.
  
## <a name="turn-off-auditing"></a>Inaktivera granskning

Du måste använda Exchange Online PowerShell för att inaktivera granskning.
  
1. [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

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

    - Gå till **sidan** Granskning i Microsoft 365 Efterlevnadscenter.

      Om granskning inte är aktiverat för organisationen visas en banderoll där du uppmanas att börja spela in användar- och administratörsaktivitet.
