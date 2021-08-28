---
title: 設定信任的應用程式伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 在混合環境中，如果您建立新的受信任應用程式伺服器，則必須將下一個躍點集區設為商務用 Skype Server 2019 集區。 在混合環境中，舊版集區和商務用 Skype Server 2019 集區會出現在下拉式清單中。 但不支援選取舊版集區。
ms.openlocfilehash: 9965af757a570cfd787bb482a932d2817fd07ab0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584467"
---
# <a name="configure-trusted-application-servers"></a>設定信任的應用程式伺服器

在混合環境中，如果您建立新的受信任應用程式伺服器，則必須將下一個躍點集區設為商務用 Skype Server 2019 集區。 在混合環境中，舊版集區和商務用 Skype Server 2019 集區會出現在下拉式清單中。 但不支援選取舊版集區。
  
> [!IMPORTANT]
> 如果您要遷移的是受信任的應用程式伺服器，也應該更新所使用的 UCMA 版本。 如果您為商務用 Skype Server 2019 建立新的受信任應用程式集區，則應該將 UCMA 更新為包含商務用 Skype Server 2019 的版本，或是可用的最新版本。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>在建立信任的應用程式伺服器時，選取商務用 Skype Server 2019 做為下一個躍點

1. 開啟拓撲產生器。
    
2. 在左窗格中，以滑鼠右鍵按一下 [ **信任的應用程式伺服器** ]，然後按一下 [ **新增信任的應用程式集** 區
    
3. 輸入信任的應用程式集區的 [ **集區 FQDN** ]，並選取它將會是單一伺服器或多部伺服器。 
    
4. 按 **[下一步]**。
    
5. 在 [**選取下一個躍點]** 頁面上，從清單中選取商務用 Skype Server 2019 前端集區。 
    
6. 按一下 **[完成]**。
    
7. 選取上方節點 **商務用 Skype Server**，然後從 [**動作**] 功能表中選取 [**發佈**]。
    
    確認已成功建立 **信任的應用程式集** 區，且該集區與正確的前端集區相關聯。 
    

