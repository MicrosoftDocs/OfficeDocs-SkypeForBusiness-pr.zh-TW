---
title: 在壓力和效能案例中布建拓撲以執行負載
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 商務用 Skype Server 2015 拓撲變更或布建，以允許使用者成功執行壓力和效能工具。
ms.openlocfilehash: 50bd77dd7b3531a150e1e62f6192d32666fa5ba7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854257"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>在壓力和效能案例中布建拓撲以執行負載
 
商務用 Skype Server 2015 拓撲變更或布建，以允許使用者成功執行壓力和效能工具。
  
根據您部署商務用 Skype Server 2015 的現有設定和設定，您可能需要在環境中進行一些變更。 以下是這些變更的清單：
  
1. 將 Windows PowerShell 執行原則設定為無限制。 如果您不確定目前所設定的設定，您可以開啟商務用 Skype Server 管理命令介面，並執行下列命令：
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   若未傳回無限制的值，則必須執行下列下一步：
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. 若要有效地設定商務用 Skype Server，您必須：
    
    - 熟悉商務用 Skype Server 2015 拓撲 (如電腦名稱稱、服務實例、網站名稱和原則) 。
    
    - 將一些建立的使用者指派給群組，例如回應群組搜尋群組 (例如，SIP URIs) 。
    
3. 若要從命令列執行腳本，您可以使用：
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 一般來說，當您從這個套件執行腳本後，所產生的追蹤會儲存在執行腳本的相同路徑中。 也有命名格式 \<scriptname\> $h $ m $s.txt。 因此，如果您在 12:15 PM 執行 ArchivingPolicy.ps1，您會收到名為 ArchivingPolicy121500.txt 的記錄檔。
    
5. 當我們為伺服器設定提供這些範例後，您可以在完成執行負載測試後，修改設定並還原或回滾。
    

