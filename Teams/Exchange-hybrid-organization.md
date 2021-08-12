---
title: 設定混合式Exchange組織
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 瞭解如何設定一個Exchange混合式組織，Microsoft Teams群組成員資格同步處理。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4a0480ff8a795addb9ae322478fddb69e9aeceeed14ebca83f27cac34b01bfbb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284473"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>設定Exchange混合式組織，以用於Microsoft Teams
======================================================================

一般而言，您不應設定任何Exchange Online功能，以用於Microsoft Teams。 不過，針對Exchange混合式案例，需要採取一些步驟，以確保群組成員資格在 Exchange Server (內部部署和) 之間Exchange Online。 這涉及在 Azure AD 連線啟用群組寫回功能，以及各種初始化腳本：使用內部部署或混合式Microsoft 365組Exchange[組](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。