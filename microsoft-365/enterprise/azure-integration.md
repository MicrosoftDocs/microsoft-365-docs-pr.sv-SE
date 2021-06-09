---
title: Azure-integrering med Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integrera Microsoft 365 med Azure AD om du vill ha lösenordssynkronisering eller enkel inloggning i din lokala miljö.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905338"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure-integrering med Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365 använder Azure Active Directory (Azure AD) för att hantera användaridentiteter i bakgrunden. I din Microsoft 365-prenumeration ingår en kostnadsfri Azure AD-prenumeration så att du kan integrera din lokala AD DS (Active Directory Domain Services) för att synkronisera användarkonton och lösenord eller konfigurera enkel inloggning. Du kan också köpa avancerade funktioner för att bättre hantera dina konton.
  
Azure AD erbjuder även andra funktioner, till exempel hantering av integrerade appar, som du kan använda för att utöka och anpassa Microsoft 365 prenumerationer.
  
Du kan använda Azure AD-distributionsrådgivaren för en guidad konfiguration och konfiguration i administrationscentret för Microsoft 365 (du måste vara inloggad för att Microsoft 365):

 - [Azure AD Anslut rådgivare](https://aka.ms/aadconnectpwsync)
 - [DISTRIBUTIONSrådgivaren för AD FS](https://aka.ms/adfsguidance)
 - [Konfigurationsguide för Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD-utgåvor och Microsoft 365 identitetshantering

Om du har en betald prenumeration på Microsoft 365 har du också en kostnadsfri Azure AD-prenumeration. Du kan använda Azure AD för att skapa och hantera användar- och gruppkonton. Du måste slutföra en registrering som krävs för att aktivera den här prenumerationen. Därefter kan du komma åt Azure AD Microsoft 365 administrationscentret. 

Instruktioner för hur du registrerar din kostnadsfria Azure AD-prenumeration finns i [använda din kostnadsfria Azure AD-prenumeration.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) Gå inte direkt till azure.microsoft.com för att registrera dig för då kan du få en utvärderingsversion eller betald prenumeration på Microsoft Azure som skiljer sig från din kostnadsfria Azure AD-prenumeration med Microsoft 365. 
  
Med den kostnadsfria prenumerationen kan du synkronisera med lokala kataloger, konfigurera enkel inloggning och synkronisera med många programvaror som tjänstprogram, till exempel Salesforce, DropBox och många fler.
  
Om du vill ha förbättrade funktioner i AD DS, dubbelriktad synkronisering och andra hanteringsfunktioner kan du uppgradera din kostnadsfria prenumeration till en betald Premium-prenumeration. Mer information finns i [Azure Active Directory utgåvor](https://azure.microsoft.com/pricing/details/active-directory/).
  
Mer information om hur du Microsoft 365 och Azure AD finns i skapa [Microsoft 365 identitetsmodeller.](about-microsoft-365-identity.md)
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Utöka funktionerna i Microsoft 365 klientorganisation

|**Funktion**|**Beskrivning**|
|:-----|:-----|
|Integrerade appar  <br/> |Du kan ge enskilda appar åtkomst till dina Microsoft 365 data, till exempel e-post, kalendrar, kontakter, användare, grupper, filer och mappar. Du kan också tillåta apparna på global administratörsnivå och göra dem tillgängliga för hela företaget genom att registrera apparna i Azure AD. Mer information finns i [Integrerade appar och Azure AD för Microsoft 365 administratörer.](integrated-apps-and-azure-ads.md)  <br/> Se [även Enkel inloggning.](/azure/active-directory/manage-apps/what-is-single-sign-on)  <br/> |
|PowerApps  <br/> | Power-appar är fokuserade appar för mobila enheter som kan ansluta till dina befintliga datakällor, SharePoint till exempel listor och andra dataappar. Mer [information finns i Skapa en PowerApp SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) och sidan [PowerApps.](https://powerapps.microsoft.com/)  <br/> |
   
## <a name="see-also"></a>Se även

[Microsoft 365 Enterprise översikt](microsoft-365-overview.md)