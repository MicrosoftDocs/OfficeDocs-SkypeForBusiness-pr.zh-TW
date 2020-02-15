---
title: The Skype for Business Server 2015 壓力及效能工具的效能案例
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
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 您必須設定商務用 Skype Server 2015 進行效能和負載測試，使用 [壓力及效能工具執行的工作。
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983848"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>The Skype for Business Server 2015 壓力及效能工具的效能案例
 
您必須設定商務用 Skype Server 2015 進行效能和負載測試，使用 [壓力及效能工具執行的工作。
  
若要執行 Skype for Business Server 2015 壓力及效能工具 (LyncPerfTool)，商務用 Skype Server 2015 拓撲必須先設定相關給您的案例。 如果商務用 Skype Server 2015 未設定，或未正確設定，您的負載模擬是很可能會失敗。 與 Skype for Business Server 2015 壓力及效能工具，我們提供範例 Skype for Business Server 管理命令介面指令碼和基本的資源檔案的[工具下載](https://www.microsoft.com/download/details.aspx?id=50367)的一部分。 這些可以用於做為起點設定您 Skype for Business Server 部署。 本文將告訴您提供的 Windows PowerShell 範例。
  
> [!NOTE]
> 本主題將協助您說明如何設定用 Skype Server 2015 通常，我們有的其他規劃及部署主題。 如需使用 Windows PowerShell in Skype Server 2015 的詳細資訊，請參閱 < Skype for Business Server Management Shell 文件在此處插入簡介。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>關於執行 Skype for Business Server 管理命令介面指令碼

我們提供範例 PowerShell 指令碼可用來準備您的負載模擬。 因為這些指令碼供負載模擬，您會發現他們既簡單又寬鬆]。 可能不適合實際執行環境。 再次我們壓力，這些指令碼範例，您必須重新檢閱並在許多情況下進行的變更與環境相關才能進行實際運用。 在最低限度下，我們應該會需要修改回應服務群組 」 (RSG) 指令碼，與您記住 （若要指定指派給代理人群組的代理程式） 的拓撲。 但您不需要執行，如果您不需要。
  
> [!CAUTION]
> 請謹慎檢閱和了解這些範例中。 指令碼將會覆寫任何現有的設定，在拓撲中執行時。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>壓力及效能工具的用戶端版本名稱

您可能需要設定用戶端版本檢查原則，如果您先前已變更的設定與預設值。 如果您不確定這一點，檢查[用戶端版本檢查文件](https://msdn.microsoft.com/vsto/jj923060)。
  
壓力及效能工具預設會使用下列的使用者代理程式版本通訊用 Skype Server 2015 時：
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 壓力及效能工具)
    
- OCPHONE/.0.522
    
在 [LyncPerfTool 行動力 (UCWA) 用戶端：
  
- UCWA Qfe 工具/Web 會議
    
- UCWA Qfe 工具/行動
    

