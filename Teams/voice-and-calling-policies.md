---
title: 在 Teams 中管理語音和通話政策
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347998"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理語音和通話政策

在 Microsoft Teams 中，語音和通話政策可用來控制語音和通話。

## <a name="emergency-calling-policies"></a>緊急通話政策

您可以使用 [緊急通話政策](manage-emergency-calling-policies.md) 來設定當貴組織的使用者撥打緊急電話時會發生什麼情況。 這些策略在 Teams 系統管理中心或 Windows PowerShell 中管理。

![緊急通話政策螢幕擷取畫面。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>緊急電話路由規則

如果貴組織已部署電話 **系統直接路由**，您可以使用緊急電話路由 [](manage-emergency-call-routing-policies.md)策略來判斷緊急電話的路由位置、是否已啟用增強的緊急服務，以及緊急服務會使用哪些號碼。 這些策略是使用 PowerShell 或 Microsoft Teams 系統管理中心管理。

![緊急電話路由策略的螢幕擷取畫面。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>本機號碼政策

[本機號碼政策](caller-id-policies.md) 是用來變更或封鎖本機號碼。

![本機號碼政策螢幕擷取畫面。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>語音路由策略

語音 [路由策略](manage-voice-routing-policies.md) 是公用交換電話網路的容器 (PSTN) 記錄。 如果您的組織已部署電話系統直接路由 **，您可以使用這些策略**。 語音路由策略可以使用 PowerShell 或 Teams 系統管理中心管理。

![語音路由策略的螢幕擷取畫面。](media/voice-routing-policy.png)

## <a name="calling-policies"></a>通話原則

[通話政策](teams-calling-policy.md) 可控制使用者可以使用哪些通話和呼叫轉寄功能，包括使用者是否可以撥打私人電話、將通話傳送給通話群組，以及將通話路由至語音信箱。

![通話政策螢幕擷取畫面。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>通話停駐和取回政策

[通話保留和取回](call-park-and-retrieve.md) 功能可讓使用者保留其他使用者，並可讓同一個使用者或其他人繼續通話。

![通話停駐和取回策略的螢幕擷取畫面。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>建立和管理撥號對應表

[撥號方案](create-and-manage-dial-plans.md) 會翻譯撥號電話號碼，以用於通話授權和路由。 您可以透過 PowerShell 或 Microsoft Teams 系統管理中心建立和管理撥號表。

![撥號盤案的螢幕擷取畫面。](media/dial-plans.png)

## <a name="related-topics"></a>相關主題

* [在 Microsoft Teams 中管理緊急通話政策](manage-emergency-calling-policies.md)
* [管理緊急電話路由原則](manage-emergency-call-routing-policies.md)
* [在 Microsoft Teams 中管理本機號碼政策](caller-id-policies.md)
* [管理語音路由策略](manage-voice-routing-policies.md)
* [Microsoft Teams 中的通話政策](teams-calling-policy.md)
* [Microsoft Teams 中的通話停駐和取回](call-park-and-retrieve.md)
* [建立和管理撥號對應表](create-and-manage-dial-plans.md)
* [使用策略管理 Teams](manage-teams-with-policies.md)
