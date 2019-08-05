---
title: 商務用 Skype Server 2015 應力與效能工具的效能案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 使用壓力與效能工具設定商務用 Skype Server 2015 以執行效能與載入測試時所需執行的工作。
ms.openlocfilehash: 2aedb43a6b7214aaf582e1dfd4754e626a602508
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193132"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>商務用 Skype Server 2015 應力與效能工具的效能案例
 
使用壓力與效能工具設定商務用 Skype Server 2015 以執行效能與載入測試時所需執行的工作。
  
若要執行商務用 Skype Server 2015 的壓力與效能工具 (LyncPerfTool), 必須先針對與您相關的案例設定商務用 Skype Server 2015 拓撲。 如果未設定商務用 Skype Server 2015, 或設定不正確, 您的負載模擬很可能會失敗。 使用商務用 Skype Server 2015 的壓力與效能工具, 我們提供的是商務用 Skype Server Management Shell 腳本和基本資源檔案的範例。 [](https://www.microsoft.com/download/details.aspx?id=50367) 這些都可以用來做為設定您的商務用 Skype Server 部署的起點。 本文將說明提供的 Windows PowerShell 範例。
  
> [!NOTE]
> 本主題無法協助您描述如何設定商務用 Skype Server 2015, 我們通常會提供其他規劃與部署主題。 如需在商務用 Skype Server 2015 中使用 Windows PowerShell 的詳細資料, 請參閱這裡的 [插入簡介] 中的商務用 Skype Server Management 命令介面檔。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>關於執行商務用 Skype Server management 命令介面腳本

我們正在提供您可以用來準備負載模擬的範例 PowerShell 腳本。 因為這些腳本是用來進行負載模擬, 所以您會發現它們很簡單且可供使用。 這可能不適合您的生產環境。 我們再次強調, 這些腳本是範例, 您需要複習這些程式, 而且在許多情況下, 您必須先對您的環境進行變更, 才能實際使用它們。 我們會預計您必須使用您的拓撲來修改回應服務群組 (RSG) 腳本 (以指定指派給 agent 群組的代理程式)。 但如果您不需要的話, 您就不需要執行此程式。
  
> [!CAUTION]
> 請小心閱讀並瞭解這些範例。 在執行時, 腳本會覆寫拓撲中任何現有的設定。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>壓力與效能工具用戶端版本名稱

如果您先前已變更預設值的設定, 您可能需要設定用戶端版本檢查原則。 如果您不確定這一點, 請核取[用戶端版本檢查檔](https://msdn.microsoft.com/en-us/vsto/jj923060)。
  
當與商務用 Skype Server 2015 通訊時, [壓力] 和 [效能] 工具預設會使用下列使用者代理版本:
  
- LSPT/15.0.0.0 (商務用 Skype Server 2015 應力與效能工具)
    
- OCPHONE/.0.522
    
在 LyncPerfTool 中針對行動 (UCWA) 用戶端:
  
- UCWA Perf 工具/Web 會議
    
- UCWA Perf 工具/行動裝置
    

