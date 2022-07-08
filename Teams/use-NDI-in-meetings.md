---
title: 廣播會議內容
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 NDI 和 SDI 在 Microsoft Teams 中廣播會議內容。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d048063f7b8efa6b853aa7273e0bcefaeb41b1f
ms.sourcegitcommit: 9175c6d542dd825ce965d0cb7c67264f22315202
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2022
ms.locfileid: "66687819"
---
# <a name="broadcast-meeting-content"></a>廣播會議內容 



Teams 提供廣播 Teams 會議內容的兩個選項：[網路裝置介面] (NewTek NDI®) 和串列數位介面 (SDI) ：

- NewTek NDI® 技術是連接媒體裝置 (的現代化解決方案，例如工作室相機和混搭機) 。 NDI® 技術可透過本機內部網路（包括本機電腦）啟用連線，而不是使用實體連線。

  NDI® 技術已成為製作串流即時內容的標準產業解決方案，在專業廣播世界中也獲得了重要的意識和採用。

- 自 1989 年起，SDI 已用於廣播生產，而且在大多數的舊版 Studio 硬體裝置上都受到支援。 AJA 視訊系統和黑色影像設計的硬體裝置，為使用 SDI 的舊版廣播裝置提供連線能力。

> [!NOTE]
> 支援 SDI 的視訊硬體退出功能目前處於預覽版本中。

所有地區皆支援 NDI® 和 SDI 技術。

使用 NDI 和 SDI 的存取權取決於嘗試啟用此功能的使用者的會議原則。 若要獲得最安全的解決方案，請勿開啟本機串流參數做為全域設定。


## <a name="enable-broadcast-features"></a>啟用廣播功能

若要為使用者啟用 NDI® 和 SDI 廣播功能：

1. 租使用者系統管理員必須啟用使用者會議原則的本機串流。 

2. 使用者必須針對其特定用戶端開啟本機串流。


若要啟用使用者，您可以使用 Teams 管理員中心或 Teams PowerShell，如下所示。

在 Teams 系統管理中心，移至 **會議原則>音訊&視訊** ，然後選取 **[本機廣播]**。

若要使用 PowerShell，請使用Set-CsTeamsMeetingPolicy Cmdlet，如下所示：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

填入此變更之後，使用者必須從 [設定許可權] 開啟其特定用戶端 **的**  >  本機串流。**** 如需詳細資訊，請參閱 [從 Teams 廣播音訊和視訊](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)。





