---
title: 設定具有三層保護層級的 Teams 會議
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365solution-overview
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 瞭解如何使用三層保護來設定 Teams 會議，以提升安全性、在安全性上與輕鬆進行共同作業之間取得平衡。
ms.openlocfilehash: 607c4d484df714fd4fba736ffd618aafdbab67d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800136"
---
# <a name="configure-teams-meetings-with-three-tiers-of-protection"></a>設定具有三層保護層級的 Teams 會議

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

本系列文章提供使用 Teams 和 Microsoft 365 中可用的合規性功能來建立符合您合規性需求的會議環境的選項。 我們會查看含有敏感度標籤和範本的可用選項，以及如何與其他 Teams 系統管理員設定搭配使用這些選項。

> [!Note]
> 敏感度標籤和自訂會議範本中的會議設定需要Teams 進階版。

本文定義了四種不同的設定，從沒有特定合規性需求之會議的比較基準設定開始。 隨著會議選項受到更多限制，每一個額外的設定都代表在保護上有意義的一步。 本文中的組態提供範例，說明如何設定不同敏感度等級之會議的保護。 請使用這些範例瞭解可能的功能，並視需要修改貴組織的特定設定。

我們會討論以下三種設定：

- 比較基準保護

- 敏感性保護

- 高度敏感性保護

此外，我們會討論針對出席者互動最少的簡報所設計的高度機密設定變化。

## <a name="three-tiers-at-a-glance"></a>一目了然的三層

下表摘要列出每個層級的設定。 使用這些設定做為起點建議，並調整組態以符合貴組織的需求。 根據您的合規性需求，您可能不需要每個層級。

|&nbsp;|基線|敏感|高度敏感|高度敏感的簡報|
|:-----|:-----|:-----|:-----|:-----|
|允許出席者使用相機|**開啟**|**開啟**|**開啟**|**關閉**|
|允許出席者使用麥克風|**開啟**|**開啟**|**開啟**|**關閉**|
|將浮水印套用至每個人的視訊摘要|**關閉**|**關閉**|**開啟**|**開啟**|
|將浮水印套用至共用內容|**關閉**|**關閉**|**開啟**|**開啟**|
|端對端加密|**關閉**|**關閉**|**開啟**|**開啟**|
|管理出席者看到的內容|**關閉**|**開啟**|**開啟**|**開啟**|
|會議聊天|**開啟**|**開啟**|**僅限會議中**|**關閉**|
|撥入人員可以略過大廳|**關閉**|**關閉**|**關閉**|**關閉**|
|防止將聊天內容複寫到剪貼簿|**關閉**|**關閉**|**開啟**|**開啟**|
|自動錄製|**關閉**|**關閉**|**關閉**|**關閉**|
|誰可以略過大廳|**在我的組織中人員、受信任網域的人員和來賓**|**邀請人員**|**僅自己和共同召集人**|**僅自己和共同召集人**|
|誰可以簡報|**組織中的人員和來賓**|**組織中的人員和來賓**|**僅限召集人和共同召集人**|**僅限召集人和共同召集人**|
|誰可以錄製|**召集人和簡報者**|**召集人和共同召集人**|因為浮水印而停用|因為浮水印而停用|

有關如何設定每個層級的詳細資料，請參閱：

- [使用比較基準保護設定 Teams 會議](configure-meetings-baseline-protection.md)
- [設定 Teams 會議並保護機密資料](configure-meetings-sensitive-protection.md)
- [設定 Teams 會議並保護高度機密資料](configure-meetings-highly-sensitive-protection.md)

## <a name="managing-compliance-with-sensitivity-labels-and-meeting-templates"></a>使用敏感度標籤和會議範本管理合規性

會議範本和敏感度標籤都能夠強制執行特定會議設定。 大部分的設定可以強制執行為開啟或關閉，也可以維持未設定，讓會議召集人可以進行設定。

> [!Important]
> 某些功能 [是由系統管理原則控制](meeting-templates-sensitivity-labels-policies.md#policies-labels-templates-and-meetings-settings) ，必須先啟用，才能由會議範本和敏感度標籤控制。

某些設定僅適用于敏感度標籤，有些則僅適用于範本。 兩者都有提供數種功能：

- 聊天
- 端對端加密
- 大廳設定
- 會議錄製
- 浮水印

敏感度標籤和範本可用來協助您符合合規性需求。 如需詳細資訊，請參閱 [同時使用 Teams 會議範本、敏感度標籤和系統管理原則](meeting-templates-sensitivity-labels-policies.md)。

## <a name="meeting-chat"></a>會議聊天

會議聊天是會議期間共同作業的重要部分。 不過，您可能會想要在特定類型的會議中限制會議聊天，以避免在該處共用機密資訊。

身為系統管理員，您可以使用下列方式控制會議聊天：

- **Teams 系統管理員會議原則** (每個使用者或群組) 可用來允許聊天、允許匿名參與者以外的所有人聊天，或關閉聊天功能。
- 每個會議 (敏感 **度標籤設定**) 可以強制開啟或關閉聊天，或只允許在會議期間進行聊天。 您可以將此設定設定保留為由範本或會議召集人控制。
- **每個會議 (會議範本設定**) 可以強制開啟或關閉聊天，或只允許在會議期間進行聊天。 您可以將此設定設定保留為由會議召集人控制。

針對三層的保護，我們允許比較基準和敏感性會議聊天，並在高度機密的會議中將它限制為僅限會議內。

如需詳細資訊，請參閱 [管理敏感式 Teams 會議的聊天](manage-chat-sensitive-meetings.md)。

## <a name="meeting-recordings"></a>會議錄製

身為系統管理員，您可以使用下列方式控制會議錄製：

- 每個使用者或群組 (雲端 **錄製** 系統管理員會議原則) 
- 每位使用者或群組 () 系統管理員會議原則 (記錄刪除，會議會 **自動過期**) 
- **誰可以錄製** 敏感度標籤和會議範本中的設定， (每個會議) 
- 敏感度標籤和會議範本中的 [ **自動** 錄製] 設定 (每個會議) 

如果您的組織或其中某些人員或群組不應該能夠錄製會議，您可以使用 **雲端錄製** 系統管理員會議原則來關閉此功能。

如果有特定類型的會議必須永遠記錄下來，您可以使用會議範本或敏感度標籤強制執行 **[** 自動錄製] 設定。

在此討論的三層中，由於我們在共用內容和視訊上使用端對端加密及浮水印，因此在高度機密的會議中會停用錄製。 如果您需要能夠錄製高度機密的會議，請確定您沒有使用敏感度標籤強制執行浮水印或端對端加密。 會議召集人仍然可以使用端對端加密，並在未錄製指定的會議時套用浮水印。

如需管理會議錄製選項的詳細資訊，請參閱 [管理敏感性會議的 Microsoft Teams 會議錄製選項](manage-meeting-recording-options.md)。

如需遵循原則型會議記錄的相關資訊，請參閱 [Teams 原則型錄製簡介，以針對通話&會議](teams-recording-policy.md)。

## <a name="meeting-with-guests-and-external-participants"></a>與來賓和外部參與者開會

可以加入會議的外部參與者有三種：

- 來自信任網域的參與者
- 來賓
- 匿名參與者

來自受信任網域的參與者會透過 [外部存取](manage-external-access.md) 功能加入會議。 您可以控制貴組織想要信任哪些網域，如果有的話。  (此設定也會影響與這些網域中的人員進行一對一和群組聊天。) 

如果您的組織已啟用 [Teams 來賓存取](guest-access.md) ，則來賓將能夠加入會議。 來賓存取設定也可以用來控制來賓的螢幕共用模式，包括停用螢幕畫面分享。  (來賓存取權也用於邀請來賓加入團隊。) 

如果 **匿名使用者可以加入會議** Teams 系統管理員設定已開啟，匿名參與者將能夠加入會議。

雖然您可以完全關閉匿名加入，而不會影響會議以外的功能，但來賓存取和受信任的網域都會用於會議以外的情況。 如果您想要限制這些參與者的會議存取權，但基於其他原因需要讓功能保持開啟，您必須使用大廳。

## <a name="lobby-options"></a>大廳選項

會議大廳可讓會議召集人先檢查出席者，再允許他們進入會議。 視會議類型和您的合規性需求而定，建議您允許所有出席者略過大廳並直接加入會議，或在大廳等候特定類型的出席者，直到會議召集人允許他們進入為止。 如果您想要防止特定類型的人員參加會議，例如來賓，您可以讓他們在大廳等候，然後會議召集人就可以拒絕他們加入。

針對比較基準層級，我們允許匿名出席者以外的所有人略過大廳。 針對敏感性會議，我們只允許具有會議邀請的人員略過大廳。 對於高度機密的會議，我們需要召集人准許每位出席者參加。

身為系統管理員，您可以透過下列方式控制大廳：

- 自動 **允許** 使用者或群組 (人員系統管理員會議原則) 
- **撥入使用者可以略過大廳** 系統管理員會議原則， (每個使用者或群組) 
- 在敏感度標籤和會議範本中 **，誰可以略過大廳** 設定， (每個會議) 
- 撥 **入人員可以略過大廳** 系統管理員會議原則 (每個使用者或群組) ，或在敏感度標籤和會議範本中， (每個會議) 

除非會議召集人已鎖定敏感度標籤或範本，否則這些設定也可供會議召集人使用。


當系統管理員原則設定預設值時，您需要範本或標籤來強制執行


如果您的產業受到高度規範，而且必須手動允許每位出席者參加貴組織中的所有會議，您可以使用 Teams 系統管理中心的系統管理員會議原則來設定大廳。 如果貴組織不同類型的會議具有不同的大廳需求，則建議您使用會議範本或敏感度標籤來設定這些設定。

如需詳細資訊，請參閱針對 [敏感性會議設定 Microsoft Teams 會議大廳](configure-lobby-sensitive-meetings.md)

## <a name="related-topics"></a>相關主題

[適用于企業架構的 Microsoft 雲端圖例](/microsoft-365/solutions/cloud-architecture-models)

[使用敏感度標籤來保護行事曆專案、Teams 會議和聊天](/microsoft-365/compliance/sensitivity-labels-meetings)