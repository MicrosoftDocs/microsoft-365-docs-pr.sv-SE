---
title: Hitta din domänregistrator
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Lär dig hur du hittar din domänregistrator och DNS-värdtjänst med InterNIC-sökning.
ms.openlocfilehash: 77e4776946d51cb4f8dfe1a746e85d74a9e0a700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228033"
---
# <a name="find-your-domain-registrar"></a>Hitta din domänregistrator

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.

## <a name="domain-registrar"></a>Domänregistrator

### <a name="find-your-domain-name-registrar"></a>Hitta din domännamnsregistrator

> [!NOTE]
> Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.

1. På [söksidan för InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois-sökning** anger du din domän, till exempel  *contoso.com.*

2. Välj alternativet **Domän** och välj sedan **Skicka**.

3. På sidan **Whois sökresultat** letar du upp rutan **Registrator**. Här hittar du den organisation som tillhandahåller registratorstjänsten för din domän.

## <a name="dns-hosting-provider"></a>DNS-värdtjänst

### <a name="find-your-dns-hosting-provider"></a>Hitta din DNS-värdtjänst

> [!NOTE]
> Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.

1. På [söksidan för InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois-sökning** anger du din domän, till exempel contoso.com.

2. Välj alternativet **Domain** (Domän) och välj sedan **Submit** (Skicka).

3. På sidan **Whois Search Results** (Whois-sökresultat) söker du efter den första **Name Server** (Namnserver)-posten.

4. Kopiera den namnserverinformation (NS) som visas efter kolonet (:) och klistra in den i rutan **Sök** längst upp på sidan. Välj **Namnserver** och välj sedan **Skicka**.

5. På sidan **Whois Search Results** (Whois-sökresultat) letar du upp rutan **Registrar** (Registrator). Här hittar du namnet på den DNS-tjänstleverantör som äger din domäns namnserver.

---

