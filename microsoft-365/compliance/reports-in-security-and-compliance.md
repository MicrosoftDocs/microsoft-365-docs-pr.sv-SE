---
title: Rapporter i Säkerhets- & Efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: Använd Säkerhets- & för att få olika rapporter för din organisation SharePoint Online Exchange Online, plus Azure Active Directory rapporter.
ms.openlocfilehash: 3e72ecab68ece31c44d99f85806492e788f4cd7c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162214"
---
# <a name="reports-in-the-security--compliance-center"></a>Rapporter i Säkerhets- & Efterlevnadscenter

Du kan använda sidan **Visa rapporter** i Säkerhets- och & för att snabbt komma åt granskningsrapporter för dina SharePoint Online och Exchange Online organisationer. Du kan också komma Azure Active Directory (AD) inloggningsrapporter, användaraktivitetsrapporter och Azure AD-granskningsloggen från **sidan Visa** rapporter. Det beror på att din betalda prenumeration Microsoft 365 ingår en kostnadsfri prenumeration på Microsoft Azure. Första gången du försöker komma åt dessa Azure-rapporter måste du slutföra en registreringsprocess som du bara behöver utföra. 
  
> [!TIP]
> Om du vill visa fler rapporter om aktivitet i organisationen [går du till Aktivitetsrapporter Microsoft 365 administrationscentret](../admin/activity-reports/activity-reports.md). 
  
 **Before you begin**
  
Du behöver följande behörigheter för att visa rapporter i Säkerhets- & efterlevnadscenter.
  
- Du måste ha tilldelats rollen Säkerhetsläsare i administrationscentret Exchange (EAC) för att kunna visa rapporter i & säkerhets- och efterlevnadscenter. Som standard är den här rollen tilldelad rollgrupperna Organisationshantering och Säkerhetsläsare i EAC.
    
- Du måste ha tilldelats rollen View-Only DLP-efterlevnadshantering i Säkerhets- och efterlevnadscenter för & för att kunna visa DLP& och efterlevnadscenter. Som standard tilldelas den här rollen rollgrupperna Efterlevnadsadministratör, Organisationshantering, Säkerhetsadministratör och Säkerhetsläsare i säkerhets- & Säkerhets- och efterlevnadscenter.

- Dessutom måste du tilldelas rollen Mottagare View-Only I EAC för att kunna visa DLP-rapporter i EAC. Som standard är den här rollen tilldelad rollgrupperna Efterlevnadshantering, Organisationshantering View-Only Organisationshantering i EAC.
  
 **Så här öppnar du sidan Visa rapporter i säkerhets- & Säkerhets- och efterlevnadscenter:**
  
1. Gå till [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Logga in med uppgifterna för ett användarkonto i din organisation.
    
På **sidan Visa** rapporter kan du visa följande typer av rapporter: 
  
- [Granskningsrapporter](#auditing-reports)
- [Övervakande granskningsrapport](#supervisory-review-report)
- [Rapporter för dataförlustskydd](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Granskningsrapporter

I följande tabell beskrivs rapporterna i avsnittet **Granskning** på sidan Visa **rapporter** i Säkerhets- och & efterlevnadscenter. 
  
|**Rapport**|**Beskrivning**|
|:-----|:-----|
|**granskningsloggrapport** <br/> |Du kan söka i granskningsloggen efter användar- och administratörsaktivitet i organisationen. Rapporten innehåller poster för användar- och administratörsaktivitet i Exchange Online, SharePoint Online, OneDrive för företag och Azure Active Directory, som är katalogtjänsten för Office 365. Mer information finns i [Söka i granskningsloggen i Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Azure AD-rapporter** <br/> |Om du vill leta efter ovanliga eller misstänkta inloggningsaktiviteter i organisationen kan du använda inloggnings- och aktivitetsrapporter i Microsoft Azure. Du kan också visa händelser i Azure AD-granskningsloggen. Om du vill visa rapporter i Azure klickar du på **Visa Azure AD-rapporter.** Mer information finns i: <br/><br/>[Använd din kostnadsfria Azure Active Directory prenumeration i Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Visa dina åtkomst- och användningsrapporter](/azure/active-directory/reports-monitoring/overview-reports).  <br/> |
|**Exchange över granskningsrapporter** <br/> | Du kan använda granskningsfunktionen i Microsoft 365 för att spåra ändringar Exchange Online av organisationens administratörer. Ändringar som gjorts i Exchange Online organisation av en Microsoft-datacenteradministratör eller av en delegerad administratör loggas också. För Exchange Online är granskningsloggning för administratörer aktiverad som standard, så du behöver inte göra något för att aktivera den. Exchange Online även granskningsloggning för postlådor så att du kan spåra åtkomsten till postlådor av någon annan än postlådans ägare. Du måste aktivera granskningsloggning för postlådor för varje postlåda som du vill spåra åtkomst som inte är ägare.  <br/>  För både granskningsloggning för administratörer och postlådor kan du köra granskningsrapporter för att visa granskningsloggposterna. Du kan också exportera granskningsloggar för postlådor och administratörer, som skickas till dig inom 24 timmar i en XML-fil som är bifogad i ett e-postmeddelande. <br/><br/>Mer information om hur du exporterar granskningsloggar finns i:  <br/><br/> [Exportera granskningsloggar för postlådor](/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) <br/> [Visa och exportera granskningsloggen för administrationscentret](/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) <br/> [Söka i rollgruppens ändringar eller granskningsloggar för administratören](/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) <br/>   [Exchange granskningsrapporter](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).  <br/> |
   
## <a name="supervisory-review-report"></a>Övervakande granskningsrapport

Med rapporten om övervakande granskning kan du se status för alla övervakande granskningsprinciper i organisationen. Mer information finns i [Konfigurera principer för övervakande granskning för din organisation.](./communication-compliance-configure.md)
  
## <a name="data-loss-prevention-reports"></a>Rapporter för dataförlustskydd

DLP-rapporter (Data Loss Prevention) innehåller information om de DLP-principer och regler som har tillämpats på innehåll som innehåller känsliga data i organisationen. Du kan också konfigurera rapporten så att information om DLP-åtgärder som baseras på din DLP-princip och dina regler visas. Mer information finns i [Visa rapporten för skydd mot dataförlust.](view-the-dlp-reports.md)