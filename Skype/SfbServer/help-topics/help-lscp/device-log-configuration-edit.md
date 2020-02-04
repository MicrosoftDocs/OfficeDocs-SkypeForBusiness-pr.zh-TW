---
title: 裝置記錄配置編輯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 您可以將裝置記錄設定新增至 [編輯記錄] 設定頁面，以判斷最大記錄快取大小、最大記錄檔大小，或記錄檔案在清除之前所保留的時間長度。 您可以根據組織的需求變更這些設定。
ms.openlocfilehash: 069548626972f8daf73f1863ec08f302bf20e082
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700308"
---
# <a name="device-log-configuration-edit"></a>裝置記錄組態：編輯
 
您可以將裝置記錄設定新增至 [**編輯記錄] 設定**頁面，以判斷最大記錄快取大小、最大記錄檔大小，或記錄檔案在清除之前所保留的時間長度。 您可以根據組織的需求變更這些設定。
  
> [!CAUTION]
> 清除檔案會從檔案系統將檔案永久移除。因此清除檔案後，您便無法復原檔案。 
  
## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在 [**編輯記錄] 設定**頁面上執行下列任務：
  
- 全域或針對特定網站新增裝置記錄配置。
    
- 修改現有裝置記錄檔設定的選項。
    
## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。
  
- **範圍**識別裝置記錄配置的範圍（全域或網站）。
    
- **名稱**您可以新增或修改裝置記錄配置的名稱。
    
- 檔案**大小上限（位元組）** 您可以指定記錄檔在清除前可以達到的大小上限。 預設值為1024000個位元組（1 MB）。
    
- **最大快取大小（位元組）** 您可以指定要在記錄檔案快取中保留的最大資訊數量（以位元組為單位），以便在必須清除快取，並將資料寫入記錄檔。 預設值為512000個位元組（0.5 MB）。
    
- **刷新快取的分鐘數（1-60）** 您可以指定儲存在記錄檔案快取中的資訊在實際的記錄檔中寫入的頻率。 記錄資料之後，就會清除快取。 預設值為5分鐘。
    
- **保留記錄檔的天數（1-365）** 您可以指定記錄檔案在清除前保留的天數。 預設值為10天。
    
## <a name="see-also"></a>另請參閱

[裝置記錄組態](device-log-configuration.md)
