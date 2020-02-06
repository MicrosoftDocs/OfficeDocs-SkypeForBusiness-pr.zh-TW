---
title: 在壓力與效能案例中，配拓拓撲以執行負載
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 商務用 Skype Server 2015 拓撲變更或提供，以允許使用者成功執行壓力與效能工具。
ms.openlocfilehash: 2156616fac98d1e6fad08d2036f4bc2def3e98b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816162"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>在壓力與效能案例中，配拓拓撲以執行負載
 
商務用 Skype Server 2015 拓撲變更或提供，以允許使用者成功執行壓力與效能工具。
  
您可能需要在您的環境中進行一些變更，這取決於您現有的設定與商務用 Skype Server 2015 部署的配置。 以下是這些變更的清單：
  
1. 將 [Windows PowerShell 執行原則] 設定為 [無限制]。 如果您不確定目前所設定的專案，您可以開啟商務用 Skype Server Management 命令介面，然後執行此命令：
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   如果沒有傳回不受限制的值，您必須執行下一步：
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. 若要有效地設定商務用 Skype Server，您必須：
    
    - 熟悉商務用 Skype Server 2015 拓撲（例如電腦名稱稱、服務實例、網站名稱及原則）。
    
    - 指派一些建立給群組的使用者，例如回應群組查尋群組（例如 SIP Uri）。
    
3. 若要從命令列執行腳本，您可以使用：
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 通常，在您執行此套件中的腳本之後，產生的追蹤會儲存在執行腳本之位置相同路徑中的檔案中。 還有命名格式， \<$h scriptname\>$ m $ s .txt。 因此，如果您在 12:15 PM 執行 ArchivingPolicy，您將會收到名為 ArchivingPolicy121500 的記錄檔。
    
5. 雖然我們為伺服器設定提供了這些範例，但在執行完負載測試之後，您可以修改配置並還原或回滾。
    

