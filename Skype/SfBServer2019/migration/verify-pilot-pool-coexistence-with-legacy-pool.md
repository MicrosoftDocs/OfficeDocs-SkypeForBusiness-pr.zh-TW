---
title: 驗證試驗集區與舊版集區共存
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用舊版池來驗證試驗池共存的程式。
ms.openlocfilehash: 386ea4a7857fcdef7d45e5d8029ff4bf31293819
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812671"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>驗證試驗集區與舊版集區共存

 **本文內容**
  
[確認已開始使用商務用 Skype Server 2019 服務](#sectionSection0)
  
[開啟商務用 Skype Server 2019 的 [控制台]](#sectionSection1)
  
[不要嘗試在舊版拓撲建立器中開啟拓撲](#sectionSection2)
  
部署試生產池之後，您必須使用 [管理工具] 來查看池資訊，以驗證這兩個池的共存性。 針對商務用 Skype Server 2019 池與舊版池，您必須使用商務用 Skype Server 2019 的控制台與拓撲建立工具。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>確認已開始使用商務用 Skype Server 2019 服務
<a name="sectionSection0"> </a>

1. 從商務用 Skype Server 2019 前端伺服器，流覽至系統管理 Tools\Services 小程式。
    
2. 確認下列服務正在前端伺服器上執行：

    - 集中式記錄服務代理程式
    - 應用程式共用
    - 音訊測試服務
    - 音訊/視訊會議
    - 通話駐留
    - 會議公告
    - 會議助理
    - 前端
    - IM 會議
    - 仲介
    - 複本複製器代理程式
    - 回應群組
    - Web 會議
    - XMPP 翻譯閘道

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>開啟商務用 Skype Server 2019 的 [控制台]
<a name="sectionSection1"> </a>

在商務用 Skype Server 2019 部署中，在前端伺服器上開啟 [商務用 Skype Server 2019] 控制台，然後選取 [舊版] 池。 重複此程式以開啟商務用 Skype Server 2019 池。
  
> [!IMPORTANT]
> 在商務用 Skype Server 2019 上，您必須先將 Silverlight 升級至 Silverlight 版本5，然後才能使用商務用 Skype Server 的 [控制台]。 
  
此拓朴現在包含舊版及商務用 Skype Server 2019 伺服器角色。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>不要嘗試在舊版拓撲建立器中開啟拓撲
<a name="sectionSection2"> </a>

只能使用商務用 Skype Server 2019 拓撲產生器來查看拓撲。 商務用 Skype Server 2019 拓撲產生器必須用來建立商務用 Skype Server 2019 和舊版安裝的 pool。

  

