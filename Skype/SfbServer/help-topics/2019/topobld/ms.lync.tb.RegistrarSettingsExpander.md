---
title: 登錄器設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: 復原功能可為註冊機構池提供高可用性和災害復原。 在主要註冊機發生故障時提供備份註冊機構, 備份註冊機構可能會接管失敗的註冊機, 讓使用者可以登入及通訊。 根據主要註冊機構失敗的系統, 使用者可能會遇到精簡功能。
ms.openlocfilehash: 122124140c93afb3ce58b1d9423839f3e21dbcad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188023"
---
# <a name="registrar-settings-expander"></a>登錄器設定展開工具
 
復原功能可為註冊機構池提供高可用性和災害復原。 在主要註冊機發生故障時提供備份註冊機構, 備份註冊機構可能會接管失敗的註冊機, 讓使用者可以登入及通訊。 根據主要註冊機構失敗的系統, 使用者可能會遇到精簡功能。
  
在 Survivable 分支裝置或 Survivable 分支伺服器的 [**編輯屬性**] 對話方塊的 [**復原**] 區段中, 您可以變更下列設定:
  
- **關聯的使用者服務與備份註冊機構池**在下拉式清單中, 選取要充當 Survivable 分支裝置或 Survivable 分支伺服器之備份註冊機構的企業版前端池或標準版前端伺服器。
    
- **啟用容錯移轉與回切**選取此設定, 即可自動偵測失敗的註冊機構, 並自動判斷主要註冊機構已還原並準備好繼續註冊程式。
    
- **失敗偵測間隔 (秒)** 輸入在判斷主要註冊機構失敗前應經過的秒數。 預設值為120秒。 如果您選取 [**啟用容錯移轉及回切**], 此欄位就是必要的。
    
- **回退偵測間隔 (秒)** 輸入要經過多少秒, 才能確定主要註冊機構已備份。 預設值為240秒。 如果您選取 [**啟用容錯移轉及回退**], 此欄位就是必要的。
    
> [!IMPORTANT]
> 當您定義失敗偵測間隔和回退偵測間隔時, 請小心不要輸入一個間隔, 如果註冊機構無法在短期內回應, 就會導致容錯移轉和回退發生。 主要註冊機構可能不會根據載入池或伺服器的短時段來回應。 
  

