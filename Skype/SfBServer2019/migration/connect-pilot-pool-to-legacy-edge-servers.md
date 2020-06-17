---
title: 將試驗集區連線到舊版 Edge Server
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
description: 在部署商務用 Skype Server 2019 之後，您必須為您的網站設定同盟路由。 為了使用舊版安裝所使用的同盟路由，商務用 Skype Server 2019 必須設定成使用此路由。
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753923"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>將試驗集區連線到舊版 Edge Server

在部署商務用 Skype Server 2019 之後，您必須為您的網站設定同盟路由。 為了使用舊版安裝所使用的同盟路由，商務用 Skype Server 2019 必須設定成使用此路由。 
  
若要讓商務用 Skype Server 2019 網站使用舊版部署的 Director 和 Edge Server，請使用拓撲產生器建立與舊版 Edge 集區的關聯。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓撲產生器來與舊版 Edge 集區建立關聯

1. 開啟拓撲產生器。 
    
2. 選取您的網站，它會直接位於**商務用 Skype Server**節點底下。 
    
3. 在 [動作]**** 功能表上，按一下 [編輯屬性]****。
    
4. 在左窗格中，選取 [**同盟路由**]。
    
5. 在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取舊版 Director 或舊版 Edge Server （如果未列出 Director）。
  
6. 按一下 [確定]**** 關閉 [編輯內容]**** 頁面。 
    
7. 在 [拓撲產生器] 的 [商務用 Skype 伺服器 2019] 節點下，流覽至 [ **Standard edition server** ] 或 [ **Enterprise Edition 前端**集區]，以滑鼠右鍵按一下集區，然後按一下 [**編輯屬性**]。
    
8. 在 [關聯]**** 底下，選取 [關聯 Edge 集區 (適用於媒體元件)]**** 旁邊的核取方塊。 
    
9. 從清單中，選取舊版 Edge Server。 
  
10. 按一下 [確定]**** 關閉 [編輯內容]**** 頁面。 
    
11. 在 [**拓撲**產生器] 中，選取最頂端的節點（**商務用 Skype 伺服器**）。
    
12. 從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後按 **[下一步]**。
    
13. 當 [發行精靈]**** 完成之後，按一下 [完成]****。
    

