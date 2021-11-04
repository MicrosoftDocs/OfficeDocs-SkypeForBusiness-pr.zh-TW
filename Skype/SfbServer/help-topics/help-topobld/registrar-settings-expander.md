---
title: 登錄器設定展開工具
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 恢復功能提供註冊區集區的高可用性和嚴重損壞修復。 藉由在主要登錄器發生失敗時提供備份登錄器，備份登錄器可以接手失敗的登錄器，並允許使用者登入和通訊。 使用者可能會發現功能減少，視主要登錄器上失敗的系統而定。
ms.openlocfilehash: fd138232b2d1561fbd4628ebacd30e83a571dc62
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768051"
---
# <a name="registrar-settings-expander"></a>登錄器設定展開工具
 
恢復功能提供註冊區集區的高可用性和嚴重損壞修復。 藉由在主要登錄器發生失敗時提供備份登錄器，備份登錄器可以接手失敗的登錄器，並允許使用者登入和通訊。 使用者可能會發現功能減少，視主要登錄器上失敗的系統而定。
  
在您 Survivable Branch Appliance 或 Survivable Branch Server 的 **[編輯內容]** 對話方塊 **[恢復能力]** 區段中，可以變更下列設定：
  
- **關聯的使用者服務和備份註冊區集** 區在下拉式清單中，選取要充當 Survivable 分支裝置或 Survivable branch 伺服器之備份報名者的 Enterprise Edition 前端集區或 Standard Edition 前端伺服器。
    
- **啟用容錯移轉和回切** 選取此設定，以允許自動偵測失敗的註冊機構，並自動判斷主要註冊機已備份，且可以繼續進行註冊程式的處理常式。
    
- **失敗偵測間隔 (秒)** 輸入在判斷主要註冊機構失敗之前所應經過的秒數。 預設值為 120 秒。 如果您選取 [ **啟用容錯移轉和容錯回復**]，則此欄位是必要的。
    
- **後備偵測間隔 (秒)** 輸入在判斷主要註冊機已備份之前，應經過的秒數。 預設值為240秒。 如果您選取 [ **啟用容錯移轉和回退**]，則需要此欄位。
    
> [!IMPORTANT]
> 當您定義失敗偵測間隔和後援偵測間隔時，請小心不要讓輸入的間隔導致在登錄器短時間無法回應時，發生容錯移轉和容錯回復。根據集區或伺服器的負載，主要登錄器可能會在短時間內無法回應。 
  

