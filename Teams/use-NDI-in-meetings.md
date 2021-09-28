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
description: 瞭解如何使用 NDI 和 SDI 在 Microsoft Teams。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941878"
---
# <a name="broadcast-meeting-content"></a>廣播會議內容 



Teams提供兩種廣播會議Teams選項：網路裝置介面 (NewTek NDI®) 和串列數位介面 (SDI) ：

- NewTek NDI®技術是連接媒體裝置 ，例如工作室 (和混頻器等媒體裝置) 。 NDI 技術不是使用實體®，而是能利用本機內部網路 ，包括在本機電腦上進行連接。

  NDI®技術已成為為數據流製作即時內容的標準產業解決方案，並獲得了專業廣播業界的顯著認知和採用。

- 自 1989 年以來，SDI 一直在廣播製作中使用，且在大多數舊版 Studio 硬體裝置上受到支援。 AJA Video Systems 和 Blackmagic 設計的硬體裝置提供與使用 SDI 的舊版廣播裝置之間的連接。

> [!NOTE]
> 支援 SDI 的視訊硬體 Out 功能目前位於預覽版中。

所有地區®支援 NDI、SDI 和 SDI 技術。

使用 NDI 和 SDI 的存取權是由嘗試啟用此功能的使用者的會議策略所決定。 針對最安全的解決方案，請勿將本地串流參數開啟為全域設定。


## <a name="enable-broadcast-features"></a>啟用廣播功能

若要為使用者® NDI、SDI 廣播功能：

1. 租使用者系統管理員必須讓使用者開啟其會議政策的本地串流。 

2. 使用者必須針對其特定用戶端開啟本地串流。


若要啟用使用者，您可以使用系統管理中心Teams PowerShell，Teams PowerShell。

在系統Teams中心，前往會議>**音訊&，** 然後選取允許 **NDI 串流**。

若要使用 PowerShell，請使用 Set-CsTeamsMeetingPolicy Cmdlet，如下所示：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

完成此變更之後，使用者必須從許可權開啟其特定用戶端的 **設定**  >  **串流**。 詳細資訊，請參閱從 Teams[廣播音訊Teams。](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)





