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
ms.openlocfilehash: d1b5cb89f28a334b24aecf982dd3913dfce079ac
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014868"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>設定Exchange混合式組織，以用於Microsoft Teams

一般而言，您不應設定任何Exchange Online功能，以與 Microsoft Teams。 不過，針對Exchange混合式案例，需要採取一些步驟，確保內部部署和Exchange Server (之間的群組成員資格) Exchange Online。 這涉及啟用 Azure AD 連線群組寫回功能，以及各種初始化腳本：使用內部部署或混合式Microsoft 365組Exchange[組](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。