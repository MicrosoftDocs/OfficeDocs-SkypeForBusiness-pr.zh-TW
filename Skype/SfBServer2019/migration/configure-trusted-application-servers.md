---
title: 設定受信任的應用程式伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在混合式環境中, 如果您建立新的受信任的應用程式伺服器, 您必須將下一個躍點池設定為商務用 Skype Server 2019 池。 在混合式環境中, 舊版文件庫和商務用 Skype Server 2019 池都會出現在下拉式清單中。 不支援選取舊版池。
ms.openlocfilehash: b0dfb9ba1e4744ba3e0ea0c376f67a224e70376a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191557"
---
# <a name="configure-trusted-application-servers"></a>設定受信任的應用程式伺服器

在混合式環境中, 如果您建立新的受信任的應用程式伺服器, 您必須將下一個躍點池設定為商務用 Skype Server 2019 池。 在混合式環境中, 舊版文件庫和商務用 Skype Server 2019 池都會出現在下拉式清單中。 不支援選取舊版池。
  
> [!IMPORTANT]
> 如果您要遷移受信任的應用程式伺服器, 您也應該更新您正在使用的 UCMA 版本。 如果您為商務用 Skype Server 2019 建立新的受信任的應用程式池, 您應該更新 UCMA 至商務用 Skype Server 2019 隨附的版本或最新版本。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>在建立信任的應用程式伺服器時, 選取 [商務用 Skype Server 2019] 作為下一個躍點

1. 開啟拓撲建立器。
    
2. 在左窗格中, 以滑鼠右鍵按一下 [**信任的應用程式伺服器**], 然後按一下 [**新增信任的應用程式池**]
    
3. 輸入受信任的應用程式池的 [**池 FQDN** ], 然後選取它將是單一伺服器或多重伺服器。 
    
4. 按一下 **[下一步]**。
    
5. 在 [**選取下一個躍點]** 頁面上的清單中, 選取 [商務用 Skype Server 2019 前端] 池。 
    
6. 按一下 **[完成]**。
    
7. 選取最上層**的商務用 Skype 伺服器**, 然後從 [**動作**] 功能表中選取 [**發佈**]。
    
    確認信任的**應用程式池**已順利建立, 且與正確的 [前端] 池相關聯。 
    

