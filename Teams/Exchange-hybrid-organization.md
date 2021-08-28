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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3ef36b7bc50d21131dd10294566549bb8b642600
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632647"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>設定Exchange混合式組織，以用於Microsoft Teams
======================================================================

一般而言，您不應設定任何Exchange Online功能，以與 Microsoft Teams。 不過，針對Exchange混合式案例，有一些必要步驟可確保群組成員資格在內部部署和Exchange Server (之間) Exchange Online。 這涉及啟用 Azure AD 連線的群組寫回功能，以及各種初始化腳本：使用內部部署或混合式Microsoft 365組Exchange[組](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。