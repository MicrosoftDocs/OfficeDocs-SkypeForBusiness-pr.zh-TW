---
title: 管理語音和通話Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 瞭解語音Teams通話政策。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460583"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>管理語音和通話Microsoft Teams

語音和通話政策是用來控制語音和通話Microsoft Teams。

## <a name="emergency-calling-policies"></a>緊急通話政策

您可以使用 [緊急通話政策](manage-emergency-calling-policies.md) 來設定當貴組織的使用者撥打緊急電話時會發生什麼情況。 這些策略在系統管理中心Teams使用Windows PowerShell。

![緊急通話策略的螢幕擷取畫面。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>緊急通話路由策略

如果貴組織已部署 **電話系統** 路由，您可以使用緊急電話路由策略來 [](manage-emergency-call-routing-policies.md)判斷緊急電話的路由位置、是否已啟用增強的緊急服務，以及用於緊急服務的號碼。 這些策略是使用 PowerShell 或系統管理Microsoft Teams管理中心管理。

![緊急通話路由策略的螢幕擷取畫面。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>本機號碼政策

[本機號碼政策](caller-id-policies.md) 是用來變更或封鎖本機號碼。

![本機號碼策略的螢幕擷取畫面。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>語音路由策略

語音 [路由策略](manage-voice-routing-policies.md) 是公用交換電話網絡 (PSTN) 容器。 如果您的組織已部署直接路由，您可以使用 **電話系統策略**。 語音路由策略可以使用 PowerShell 或系統管理中心Teams管理。

![語音路由策略的螢幕擷取畫面。](media/voice-routing-policy.png)

## <a name="calling-policies"></a>通話原則

[通話政策](teams-calling-policy.md) 可控制哪些通話和呼叫轉寄功能可供使用者使用，包括使用者是否可以撥打私人電話、將通話傳送給通話群組，以及將通話路由至語音信箱。

![通話策略的螢幕擷取畫面。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>呼叫停駐和取回策略

[呼叫保留和取回](call-park-and-retrieve.md) 可讓使用者將其他使用者置於保留狀態，並可讓同一個使用者或其他人繼續通話。

![呼叫停駐和取回策略的螢幕擷取畫面。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>建立和管理撥號對應表

[撥號方案](create-and-manage-dial-plans.md) 會翻譯撥號電話號碼，以用於通話授權和路由。 您可以透過 PowerShell 或系統管理中心建立Microsoft Teams方案。

![撥號方案螢幕擷取畫面。](media/dial-plans.png)

## <a name="related-topics"></a>相關主題

* [在 Microsoft Teams](manage-emergency-calling-policies.md)
* [管理緊急電話路由原則](manage-emergency-call-routing-policies.md)
* [管理 Microsoft Teams 中的來電顯示原則](caller-id-policies.md)。
* [管理語音路由策略](manage-voice-routing-policies.md)
* [通話中Microsoft Teams](teams-calling-policy.md)
* [呼叫停駐和Microsoft Teams](call-park-and-retrieve.md)
* [建立和管理撥號對應表](create-and-manage-dial-plans.md)
* [使用Teams管理](manage-teams-with-policies.md)
