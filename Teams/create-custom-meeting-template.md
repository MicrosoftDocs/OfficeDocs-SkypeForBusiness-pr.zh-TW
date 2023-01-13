---
title: 在 Microsoft Teams 中建立自訂會議範本
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
- highpri
appliesto:
- Microsoft Teams
description: 瞭解 Microsoft Teams 系統管理員如何建立自訂會議範本，以設定或強制執行會議召集人設定，以增強會議安全性和合規性。
ms.openlocfilehash: ec9e836474032d5bb9fde0aed6c81a231788d1bf
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800273"
---
# <a name="create-a-custom-meeting-template-in-microsoft-teams"></a>在 Microsoft Teams 中建立自訂會議範本

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Microsoft Teams 自訂會議範本 (Teams 進階版功能) 可讓您為會議召集人可用的許多會議設定指定值。 範本可以設定會議召集人可以變更或鎖定設定的設定，讓會議召集人無法變更設定。 如需自訂會議範本的詳細資訊，請參 [閱 Microsoft Teams 中的自訂會議範本概觀](custom-meeting-templates-overview.md)。

您最多可以建立 50 個自訂範本。 如需如何管理使用者可使用的範本的相關資訊，請參閱管理 [Microsoft Teams 中的會議範本](manage-meeting-templates.md) 。

針對範本中的每個選項，您可以定義下列專案：

- **預設值** ： 這是使用範本時套用至會議的值。
- **可見** - 這會決定會議召集人是否可以在會議選項中看到此設定。 
- **鎖定狀態** - 這會決定會議召集人是否可以變更範本所設定的設定。 如果設定已鎖定，會議召集人就無法變更設定。

建立自訂會議範本

1. 在 Teams 系統管理中心中，展開 **[會議** ]，然後選取 **[會議範本]**。
1. 選取 **[新增]**
1. 輸入範本的名稱和描述。
1. 選擇您要用於此範本的設定。  (請參閱下方各節以瞭解每個設定的描述。) 
1. 若要防止會議召集人變更設定，請選取設定，然後選取 **[鎖定]**。
1. 若要防止會議召集人看到設定，請選取設定，然後選取 **[隱藏]**。
1. 選取 [儲存 **]**。

建立範本之後，使用者最多可能需要 24 小時才能使用。

#### <a name="security"></a>安全性

|設定|描述|
|:------|:----------|
|敏感度標籤|指定會議要使用的會議敏感度標籤。 請注意，敏感度標籤可能會覆寫範本中的特定設定。|
|誰可以略過大廳？|指定誰可以略過大廳並直接加入會議。|
|撥入人員可以略過大廳|指定使用電話撥入的人員是否可以略過大廳並直接加入會議。|
|當來電者加入並離開時通知|指定當人員透過電話撥入或離開會議時，是否要播放音效。|
|啟用會議端對端加密|指定您是否要讓會議使用端對端加密。 如果已開啟錄製和轉譯，則無法運作。|
|將浮水印套用至共用內容|指定在會議畫面上共用的內容上是否要重迭浮水印。|
|將浮水印套用至每個人的視訊摘要|指定會議中出席者視訊摘要上是否要重迭浮水印。|

#### <a name="audio-and-video"></a>音訊和視訊

|設定|描述|
|:------|:----------|
|允許出席者使用麥克風|開 **啟** 時，出席者可以取消靜音。|
|允許出席者使用相機|開 **啟** 時，出席者可以開啟其相機。|

#### <a name="recording-and-transcription"></a>錄製和轉譯

|設定|描述|
|:------|:----------|
|自動錄製會議|[ **會議** ] 會自動錄製下來。|
|誰可以錄製會議？|指定會議是否只能由召集人錄製，還是由召集人和簡報者錄製。|

#### <a name="meeting-engagement"></a>會議參與

|設定|描述|
|:------|:----------|
|出席者可以聊天|指定會議聊天是否可供使用。 也可以用來避免在會議前後聊天。|
|出席者可以使用圖釋|指定出席者是否可以在會議中使用圖釋。 這必須是 **[開** 啟]，舉手功能才能正常運作。|
|啟用 Q&A|指定出席者是否可以使用 Q&A 功能在會議期間提出問題。|
|管理出席者看到的內容|開 **啟** 時，會議召集人可以預覽及核准在螢幕上共用的內容，其他會議參與者才能看到。|

## <a name="related-topics"></a>相關主題

[Microsoft Teams 中的自訂會議範本概觀](custom-meeting-templates-overview.md)

[一起使用 Teams 會議範本、敏感度標籤和系統管理原則](meeting-templates-sensitivity-labels-policies.md)

[設定具有三層保護層級的 Teams 會議](configure-meetings-three-tiers-protection.md)
