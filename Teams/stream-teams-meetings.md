---
title: 串流 Teams 會議
author: MicrosoftHeidi
ms.author: heidip
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
description: 瞭解如何設定和管理 Teams 會議的串流處理。
ms.openlocfilehash: b8394abfe66ecde6813e383e0473bcdca2a0ad9f
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2022
ms.locfileid: "67707000"
---
# <a name="stream-teams-meetings"></a>串流 Teams 會議

本文將協助您設定 Teams 會議的串流處理。

## <a name="what-is-streaming-and-how-does-it-work"></a>什麼是串流處理及其運作方式？

串流可讓您的組織擴充您的連絡人，並提供會議出席者更多會議選項。 當您啟用串流時，召集人可以透過提供Real-Time訊息通訊協定 (RTMP) URL 和 Teams 內建的自訂串流應用程式按鍵，將會議和網路研討會串流到外部端點。

> [!NOTE]
> 您無法串流即時活動。

## <a name="set-up-streaming-with-powershell"></a>使用 PowerShell 設定串流

您可以設定貴組織使用 PowerShell 串流處理。 目前，Teams 系統管理中心不提供此原則。 每個使用者的原則是用來指定 **誰** 可以啟用即時串流。 預設為關閉。

您可以在 **Windows PowerShell Set-CsTeamsMeetingPolicy** Cmdlet 中使用下列屬性來設定串流。 如需 Cmdlet 的詳細資訊，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

- LiveStreamingMode

將 **LiveStreamingMode** 設定為 **[已啟用** ] 以開啟一或多個使用者的串流功能。

> [!IMPORTANT]
> 您必須先開啟會議註冊，召集人才能串流網絡研討會。 如需詳細資訊，請參閱 [設定網路研討會](set-up-webinars.md)。

### <a name="assign-the-policy"></a>指派原則

如需如何使用 PowerShell 指派原則的詳細資訊，請參閱 [在 Teams 中指派原則](policy-assignment-overview.md)。

## <a name="related-topics"></a>相關主題

- [在 Teams 中指派原則](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [快速入門 - 會議、網路研討會與即時活動](quick-start-meetings-live-events.md)