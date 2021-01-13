---
title: 商務用 Skype Server 2015 應力和效能工具的效能案例
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 使用壓力和效能工具，將商務用 Skype Server 2015 設定為執行效能和負載測試時所需執行的工作。
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814703"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>商務用 Skype Server 2015 應力和效能工具的效能案例
 
使用壓力和效能工具，將商務用 Skype Server 2015 設定為執行效能和負載測試時所需執行的工作。
  
若要執行商務用 Skype Server 2015 應力和效能工具 (LyncPerfTool) ，必須先針對與您相關的案例，設定商務用 Skype Server 2015 拓撲。 如果未設定商務用 Skype Server 2015，或設定不正確，您的負載模擬很可能會失敗。 透過商務用 Skype Server 2015 應力和效能工具，我們會在 [下載工具](https://www.microsoft.com/download/details.aspx?id=50367)時，供應商務用 Skype Server 管理命令介面腳本和基本資源檔案的範例。 這些可以做為設定商務用 Skype Server 部署的開始點。 本文說明所提供的 Windows PowerShell 範例。
  
> [!NOTE]
> 本主題不會協助您說明如何設定商務用 Skype Server 2015。一般而言，我們有其他的規劃及部署主題。 如需在商務用 Skype Server 2015 中使用 Windows PowerShell 的詳細資訊，請參閱此處的插入簡介中的商務用 Skype Server 管理命令介面檔。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>關於執行商務用 Skype Server 管理命令介面腳本

我們會提供可用於準備負載模擬的範例 PowerShell 腳本。 因為這些腳本是用來進行負載模擬，所以您會發現這些腳本很簡單且具有容許的效果。 這可能不適合您的實際執行環境。 同樣地，我們很強調這些腳本是範例，您必須加以檢查，而且在許多情況下，在您的環境中進行相關變更之後，才能夠實際使用它們。 在最低限度下，我們預計您必須修改回應服務群組 (RSG) 腳本，以 (指定指派給代理人群組的代理程式) 。 不過，如果您不需要執行，則不需要執行。
  
> [!CAUTION]
> 請小心檢查和瞭解這些範例。 執行時，腳本會覆寫拓撲中的任何現有設定。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>應力和效能工具用戶端版本名稱

如果您先前已變更預設值的設定，您可能需要設定用戶端版本檢查原則。 如果您不確定這一點，請查看 [用戶端版本檢查檔](https://msdn.microsoft.com/vsto/jj923060)。
  
當與商務用 Skype Server 2015 通訊時，壓力和效能工具預設會使用下列使用者代理程式版本：
  
- LSPT/15.0.0.0 (商務用 Skype Server 2015 應力和效能工具) 
    
- OCPHONE/.0.522
    
針對 LyncPerfTool 中的行動性 (UCWA) 用戶端：
  
- UCWA Perf 工具/Web 會議
    
- UCWA Perf 工具/行動裝置
    

