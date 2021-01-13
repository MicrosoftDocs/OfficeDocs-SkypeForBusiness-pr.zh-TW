---
title: 商務用 Skype Server 2015 應力和效能工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 在非實際執行或測試環境中進行容量規劃和效能調整時，會使用商務用 Skype Server 2015 的壓力和效能工具。
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814923"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>商務用 Skype Server 2015 應力和效能工具
 
在非實際執行或測試環境中進行容量規劃和效能調整時，會使用商務用 Skype Server 2015 的壓力和效能工具。
  
商務用 Skype Server 2015 應力和效能工具組含的工具可以簡化您的商務用 Skype Server 2015 的容量規劃。 商務用 Skype Server 2015 應力和效能工具可協助您：
  
- 簡化商務用 Skype 伺服器的硬體規劃
    
- 提供更多有關效能調整的知識和最佳作法
    
- 度量商務用 Skype 伺服器部署的效能
    
您通常會在您使用 [商務用 Skype server 2015 規劃工具](../../management-tools/planning-tool/planning-tool.md) 來設計拓撲，並使用 [商務用 Skype Server 2015 容量規劃計算機](../../management-tools/capacity-planning-calculator.md)來精煉拓撲之後，使用此工具。 

> [!NOTE]
> 不會更新商務用 Skype Server 2019 的工具。
  
## <a name="tests"></a>測試

壓力和效能工具可以模擬下列類型的使用者負載：
  
|||
|:-----|:-----|
|立即訊息 (IM) 和目前狀態  <br/> |音訊會議  <br/> |
|應用程式共用  <br/> |Voice over IP (VoIP) ，包括公用交換電話網路 (PTSN) 模擬  <br/> |
|Web Access 用戶端會議  <br/> |會議自動語音應答  <br/> |
|回應群組  <br/> |通訊群組清單延伸  <br/> |
|通訊錄下載和通訊錄查詢  <br/> |增強型 911 (E911) 通話和位置設定檔 (撥號對應表)   <br/> |
|重視  <br/> |資料共同作業  <br/> |
|行動性  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>商務用 Skype Server 2015 應力和效能工具隨附的應用程式和檔案

這些應用程式是商務用 Skype Server 壓力和效能工具的一部分：
  
|**工具**|**描述**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |此工具用來建立使用者和連絡人。  <br/> |
|UserProfileGenerator.exe  <br/> |用來設定所模擬之使用者負載的特性。  <br/> |
|LyncPerfTool.exe  <br/> |模擬使用者負載的工具。  <br/> |
|預設的 tmx  <br/> |需要使用商務用 Skype Server 2015 記錄工具。  <br/> |
|布建腳本範例  <br/> |根據特定案例，用來設定執行負載測試的拓撲。 您可能需要加以修改，使其與您的特定環境相關。  <br/> |
   
## <a name="topics-in-this-section"></a>本節中的主題

若需要深入瞭解，請參閱下列文章：
  
- [Skype for Busines 應力和效能工具的必要條件和設定](prerequisites-and-setup.md)
    
- [商務用 Skype Server 2015 應力和效能工具的效能案例](scenarios.md)
    
  - [在壓力和效能案例中布建拓撲以執行負載](provisioning-the-topology-to-run-load.md)
    
  - [設定商務用 Skype Server 2015 應力和效能工具的原則](configuring-policies.md)
    
- [使用商務用 Skype Server 2015 應力和效能工具](using-the-tool.md)
    
- [商務用 Skype Server 2015 的常見問題解答和效能工具](faq.md)
    

