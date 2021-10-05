---
title: 串Teams會議
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 瞭解如何設定和管理會議Teams串流。
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127541"
---
# <a name="stream-teams-meetings"></a>串Teams會議

本文將協助您設定會議Teams串流。

## <a name="what-is-streaming-and-how-does-it-work"></a>什麼是串流，它如何工作？

串流可讓貴組織擴大您的影響範圍，並給予會議出席者更多會議選項。 當您啟用串流時，召集人可提供 Real-Time 傳訊通訊通訊協定 (RTMP) URL 和 Teams 內建的自訂串流應用程式金鑰，將會議和網路研討會串流至外部端點。

> [!NOTE]
> 您無法串流即時活動。

## <a name="set-up-streaming-with-powershell"></a>使用 PowerShell 設定串流

您可以設定貴組織使用 PowerShell 串流。 目前，系統管理中心Teams此政策。 每個使用者策略是用來指定 **誰** 可以啟用即時串流。 預設為關閉。

您可以在 **Set-CsTeamsMeetingPolicy** Cmdlet Windows PowerShell中的下列屬性來設定串流。 有關 Cmdlet 的資訊，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

- LiveStreamingMode

將 **LiveStreamingMode** 設定為 **啟用** ，為一或多個使用者開啟串流功能。

> [!IMPORTANT]
> 您必須開啟會議註冊，您的召集人才能串流網絡研討會。 詳細資訊，請參閱 [設定網路研討會](set-up-webinars.md)。

### <a name="assign-the-policy"></a>指派策略

若要瞭解如何使用 PowerShell 指派策略，請參閱在 Teams[中指派Teams。](policy-assignment-overview.md)

## <a name="related-topics"></a>相關主題

- [在 Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [快速入門 - 會議、網路研討會與即時活動](quick-start-meetings-live-events.md)