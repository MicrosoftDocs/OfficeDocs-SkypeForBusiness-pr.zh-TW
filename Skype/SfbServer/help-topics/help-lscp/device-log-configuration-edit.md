---
title: 裝置記錄檔設定編輯
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 您可以在 [編輯記錄檔設定] 頁面中新增裝置記錄檔設定，以決定記錄檔快取大小上限、記錄檔大小上限，或在清除記錄檔之前保留記錄檔的時間長度。 您可以根據組織的需求來變更這些設定。
ms.openlocfilehash: a8d1ac8d85fa08461c8f43688e874371e6cb4f60
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386801"
---
# <a name="device-log-configuration-edit"></a>裝置記錄組態：編輯
 
您可以在 [ **編輯記錄檔設定** ] 頁面中新增裝置記錄檔設定，以決定記錄檔快取大小上限、記錄檔大小上限，或在清除記錄檔之前保留記錄檔的時間長度。 您可以根據組織的需求來變更這些設定。
  
> [!CAUTION]
> 永久清除檔案會將檔案從檔案系統中移除。 清除檔案之後，便無法復原。 
  
## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在 [ **編輯記錄檔設定** ] 頁面上執行下列工作：
  
- 全域或針對特定網站新增裝置記錄檔設定。
    
- 修改現有裝置記錄檔設定的選項。
    
## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。
  
- **範圍** 識別裝置記錄檔設定 (全域或網站) 的範圍。
    
- **名字** 您可以新增或修改裝置記錄檔設定的名稱。
    
- **(位元組的檔案大小上限)** 您可以指定在清除記錄檔之前，記錄檔可以變為的大小上限。 預設值為1024000位元組 (1 MB) 。
    
- **(位元組的最大快取大小)** 您可以指定可在記錄檔快取中保留的最大資訊量 (，) 在該快取必須先加以保留，才能清除快取，而且資料會寫入記錄檔。 預設值為512000位元組 (0.5 MB) 。
    
- 刷新快取 **(1-60 的分鐘)** 您可以指定儲存在記錄檔快取中的資訊寫入實際記錄檔的頻率。 在記錄資料後，會清除快取。 預設值為5分鐘。
    
- **將記錄檔保留在 (1-365 的天數)** 您可以指定在清除記錄檔之前保留的天數。 預設值為10天。
    
## <a name="see-also"></a>另請參閱

[裝置記錄組態](device-log-configuration.md)
