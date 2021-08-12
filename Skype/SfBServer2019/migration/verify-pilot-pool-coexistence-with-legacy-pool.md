---
title: 驗證試驗集區與舊版集區共存
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 驗證試驗集區與舊版集區共存的處理常式。
ms.openlocfilehash: f9a3fa8a9716d880b8fa2381fd5cafe88509504c2c142ebd5da5c5ab43667cf1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341119"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>驗證試驗集區與舊版集區共存

 **In this article**
  
[確認已啟動商務用 Skype Server 2019 服務](#sectionSection0)
  
[開啟商務用 Skype Server 2019 控制台](#sectionSection1)
  
[不要嘗試在舊版拓撲產生器中開啟拓撲](#sectionSection2)
  
部署試驗集區之後，您必須使用系統管理工具來查看集區資訊，以確認兩個集區共存。 針對商務用 Skype Server 2019 集區和舊版集區，您必須使用商務用 Skype Server 2019 控制台和拓撲產生器工具。 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>確認已啟動商務用 Skype Server 2019 服務
<a name="sectionSection0"> </a>

1. 從商務用 Skype Server 2019 前端伺服器，流覽至 [管理工具 \ 服務] 小程式。
    
2. 確認下列服務正在前端伺服器上執行：

    - 集中式記錄服務代理程式
    - 應用程式共用
    - 音訊測試服務
    - 會議 Audio/Video
    - 通話駐留
    - 會議宣告
    - 會議語音應答
    - 前端
    - IM 會議
    - 調解
    - 複製副本複製器代理程式
    - 回應群組
    - Web 會議
    - XMPP 轉譯閘道

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>開啟商務用 Skype Server 2019 控制台
<a name="sectionSection1"> </a>

在商務用 Skype Server 2019 部署中的前端伺服器上，開啟商務用 Skype Server 2019 控制台，然後選取舊版集區。 重複此程式以開啟商務用 Skype Server 2019 集區。
  
> [!IMPORTANT]
> 在商務用 Skype Server 2019 上，您必須先將 silverlight 升級至 silverlight 第5版，再使用商務用 Skype Server 控制台。 
  
此拓撲現在包括舊版和商務用 Skype Server 2019 伺服器角色。 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>不要嘗試在舊版拓撲產生器中開啟拓撲
<a name="sectionSection2"> </a>

只能使用商務用 Skype Server 2019 拓撲產生器來查看拓撲。 商務用 Skype Server 2019 拓撲產生器必須用來建立商務用 Skype Server 2019 和舊版安裝的集區。

  

