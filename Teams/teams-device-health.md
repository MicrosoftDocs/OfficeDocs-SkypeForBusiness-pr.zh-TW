---
title: 管理裝置Teams健康狀態
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: snchatur
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文將引導您管理裝置Teams裝置、已安裝Microsoft Teams裝置的健康狀態。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d5e98e65c35b8319a7e4f8675b68d530fa382c31
ms.sourcegitcommit: ab9d27d7ddd1494539ae9424de200c9d0e76a9ec
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2021
ms.locfileid: "59984768"
---
# <a name="manage-the-health-of-teams-devices"></a>管理裝置Teams健康狀態

系統管理員可以使用健康情況狀態來監控Microsoft Teams安裝之裝置的健康情況，這表示問題的嚴重性。 若要檢查裝置健康情況，您可以前往系統管理中心的 Teams 裝置區段下的裝置Teams清單。 此清單的健康情況欄會指出裝置目前的健康情況狀態。 選取該狀態會開啟健康 **狀態面板**，提供有關健康情況問題的更多詳細資料。

許多類型的問題都會導致裝置健康情況狀態，Teams系統會評估這些問題的嚴重性。

管理組織Teams裝置之系統管理員可能會決定問題的嚴重性與系統提供的預設Teams相同。 系統管理員可以自訂其裝置健康情況的嚴重性和影響，以符合其組織優先順序。

Teams 會議室裝置有附加的周邊裝置，可提供完整的會議體驗，例如喇叭、麥克風、顯示器、相機。 有關詳細資料，請參閱裝置頁面的周邊及健康情況標籤。 這些周邊設備的連線性會影響父裝置的健康。

## <a name="feature-details"></a>功能詳細資料

在裝置頁面上檢視周邊詳細資料時，您現在會看到管理健康  **情況影響** 選項。 此外，系統管理員也可以查看每個周邊裝置對裝置健康的影響。

根據預設，所有周邊 **裝置都設定** 為對裝置健康情況有重大影響。 如果外接裝置中斷連接，父裝置的健康情況會變成重要，此問題會顯示在健康情況面板的重大問題下。

> [!NOTE]
> HDMI **ingest 和****計算** 等周邊類別無法進行自訂，因為它們對父裝置的運作至關重要。

## <a name="how-does-this-work"></a>運作方式

1. 系統管理員可以選取他們想要變更其健康影響的周邊。 然後，他們可以選取 管理 **健康影響**。 或者，他們也可以在每個外周卡的外周資料表下找到管理健康影響選項。
1. 健康 **狀態影響** 面板會開啟，系統管理員可以選取所選周邊設備所需的影響等級並儲存。

| 設定選項 | 描述 |
|------------------|-------------|
| **非緊急** | 設定為周邊類別 (例如顯示器或喇叭) 且外接裝置已中斷連接時，Teams 會議室 裝置的健康狀態會變成非緊急 (，而非) 。   新問題將在健康狀態 **面板的非** 緊急區段分類。|
| **無影響** | 當設定為周邊類別且外接裝置已中斷連接時，Teams 會議室裝置的健康狀態會維持正常狀態 (重要) 。  此健康情況問題不會顯示在健康狀態面板中。|
| **關鍵** | 當設定為周邊類別且已中斷連接時，裝置Teams 會議室的狀態會變成 **重要**。 新的這類問題會分類在健康情況 **面板** 的重要區段。|
| **重設為預設值** | 當設定為周邊類別時，該類別的健康情況影響會重設為 **重要**。 儲存這個選項之後，將會採用變更，而健康情況影響將會反映這些變更。|

## <a name="applicable-device-categories"></a>適用的裝置類別

目前，這項功能可用於管理與裝置相關的Microsoft Teams 會議室 (Windows) 影響。

## <a name="impact-on-other-workflows"></a>其他工作流程的影響

如果外周健康情況影響的嚴重性降低，系統管理員可能不會注意到問題發生時。 您應該留意需要密切監控的高優先順序裝置。

例如，如果通知的健康情況變成重要，則通知已配置為觸發 ConfRoom1。  系統管理員已經將該會議室的顯示器和喇叭健康情況影響從預設為 **重要降低為****非緊急**。 現在，如果顯示器已中斷連接，則 ConfRoom1 的健康狀態會變成 **非緊急狀態**。 在這種情況下，系統不會觸發通知。
