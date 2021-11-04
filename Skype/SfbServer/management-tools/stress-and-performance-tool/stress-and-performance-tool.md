---
title: 商務用 Skype Server 2015 應力和效能工具
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 在非生產或測試環境中進行容量規劃和效能調整時，會使用商務用 Skype Server 2015 的壓力和效能工具。
ms.openlocfilehash: 565f868ae81915b6bcb595f13c2d184d82db62b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766261"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>商務用 Skype Server 2015 應力和效能工具
 
在非生產或測試環境中進行容量規劃和效能調整時，會使用商務用 Skype Server 2015 的壓力和效能工具。
  
商務用 Skype Server 2015 的壓力和效能工具組含的工具可以簡化商務用 Skype Server 2015 的容量規劃。 商務用 Skype Server 2015 的壓力和效能工具可協助您：
  
- 簡化商務用 Skype Server 的硬體規劃
    
- 提供更多有關效能調整的知識和最佳作法
    
- 衡量商務用 Skype Server 部署的效能
    
在您使用[商務用 Skype Server 2015 規劃工具](../../management-tools/planning-tool/planning-tool.md)來設計拓撲，並使用[商務用 Skype Server 2015 容量規劃計算機](../../management-tools/capacity-planning-calculator.md)來精煉拓撲時，通常會使用此工具。 

> [!NOTE]
> 將不會更新商務用 Skype Server 2019 的此工具。
  
## <a name="tests"></a>測試

壓力和效能工具可以模擬下列類型的使用者負載：
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|立即訊息 (IM) 和目前狀態   |音訊會議   |
|應用程式共用   |Voice over IP (VoIP) ，包括公用交換電話網路 (PTSN) 模擬   |
|Web Access 用戶端會議   |會議自動語音應答   |
|回應群組   |通訊群組清單延伸   |
|通訊錄下載和通訊錄查詢   |增強型 911 (E911) 通話和位置設定檔 (撥號對應表)    |
|重視   |資料共同作業   |
|行動性   ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>商務用 Skype Server 2015 壓力和效能工具隨附的應用程式和檔案

這些應用程式屬於商務用 Skype Server 壓力和效能工具的一部分：
  
|工具|描述|
|:-----|:-----|
|UserProvisioningTool.exe   |此工具用來建立使用者和連絡人。   |
|UserProfileGenerator.exe   |用來設定所模擬之使用者負載的特性。   |
|LyncPerfTool.exe   |模擬使用者負載的工具。   |
|預設的 tmx   |需要使用商務用 Skype Server 2015 記錄工具。   |
|布建腳本範例   |根據特定案例，用來設定執行負載測試的拓撲。 您可能需要加以修改，使其與您的特定環境相關。   |
   
## <a name="topics-in-this-section"></a>本節中的主題

若需要深入瞭解，請參閱下列文章：
  
- [Busines 應力和效能工具的 Skype 必要條件和設定](prerequisites-and-setup.md)
    
- [商務用 Skype Server 2015 壓力和效能工具的效能案例](scenarios.md)
    
  - [在壓力和效能案例中布建拓撲以執行負載](provisioning-the-topology-to-run-load.md)
    
  - [設定商務用 Skype Server 2015 壓力和效能工具的原則](configuring-policies.md)
    
- [使用商務用 Skype Server 2015 應力和效能工具](using-the-tool.md)
    
- [商務用 Skype Server 2015 壓力和效能工具的常見問題](faq.md)
    

