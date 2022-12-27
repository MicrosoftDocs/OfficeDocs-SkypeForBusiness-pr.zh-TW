---
title: Microsoft Teams 中的自訂會議範本概觀
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
appliesto:
- Microsoft Teams
description: 瞭解 Microsoft Teams 進階版中的自訂會議範本。
ms.openlocfilehash: 0ed766141e09b9c26d8e8c6f5e8fdd12195ddb78
ms.sourcegitcommit: 4fdbd93aacb52a4fca68e31eb04d0495d4e27a10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/27/2022
ms.locfileid: "69672913"
---
# <a name="overview-of-custom-meeting-templates-in-microsoft-teams"></a>Microsoft Teams 中的自訂會議範本概觀

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Microsoft Teams 進階版包含建立自訂會議範本的功能。 會議範本可用來控制會議召集人一般控制的會議設定。 您可以使用範本，在組織中建立一致的會議體驗，並協助強制執行合規性需求和商務規則。

會議範本可用來強制執行設定或設定預設值。 您可以鎖定每個範本設定，讓會議召集人無法變更，或是將範本解除鎖定，讓會議召集人視需要變更。

下列會議設定可以使用會議範本來控制：

|設定|描述|
|:------|:----------|
|聊天|指定會議聊天是否可供使用。 也可以用來避免在會議前後聊天。|
|端對端加密|指定會議是否加密。|
|大堂|指定誰可以略過大廳並直接加入會議。|
|管理出席者看到的內容|指定會議召集人是否可以預覽及核准在螢幕上共用的內容，其他會議參與者才能看到。|
|出席者的麥克風和相機|指定出席者是否可以取消靜音並使用其相機。|
|當來電者加入並離開時通知|指定當人員使用電話撥入或離開會議時，是否播放音效。|
|Q&A|指定出席者是否可以使用 Q&A 功能在會議期間提出問題。|
|反應|指定出席者是否可以在會議中使用圖釋或舉手。|
|錄製|指定誰可以錄製會議，以及是否自動錄製會議。|
|敏感度標籤|指定會議要使用的敏感度標籤。|
|浮水印|指定浮水印是否用於會議中螢幕共用的相機摘要和內容。|

範本有用的一些範例如下：

- 針對特定類型的會議強制執行自動會議錄製。
- 針對簡報樣式會議，限制聊天和出席者相機和音訊，以及使用 Q&A 功能。
- 對於可以略過大廳，但允許會議召集人視需要變更設定，使用更嚴格的預設值。

若要瞭解如何建立會議範本，請參閱[在 Microsoft Teams 中建立自訂會議範本](create-custom-meeting-template.md)。

## <a name="templates-with-sensitivity-labels"></a>含有敏感度標籤的範本

範本可以選擇指定敏感度標籤。 標籤也可以直接套用至會議，不含範本。 敏感度標籤可以控制一些與範本相同的設定：

- 端對端加密
- 會議聊天
- 自動錄製
- 誰可以略過大廳
- 誰可以簡報
- 誰可以錄製
- 浮水印

如果其中任一設定已在標籤中設定，則會覆寫範本中的這些設定。

## <a name="templates-included-with-teams"></a>Teams 隨附的範本

Teams 進階版包含數個您可以提供給使用者的預設會議範本：

- 大型會議
- 受保護的會議
- 大會堂
- [虛擬約會](virtual-appointment-meeting-template.md)
- 網路研討會

此外，這些範本也可在 Teams 教育版 中使用：

- 類
- 討論群組
- 演講
- 家長教師會議

如有需要，您可以更新這些範本上的設定。

## <a name="related-topics"></a>相關主題

[設定具有三層保護層級的 Teams 會議](configure-meetings-three-tiers-protection.md)

[一起使用 Teams 會議範本、敏感度標籤和系統管理原則](meeting-templates-sensitivity-labels-policies.md)
