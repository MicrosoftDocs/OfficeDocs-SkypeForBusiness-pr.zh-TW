---
title: 重設通話許可控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果舊版前端池是託管 [呼叫許可控制] (CAC), 您必須先將 CAC 託管到商務用 Skype Server 2019 池, 才能移除舊版的前端池。
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193908"
---
# <a name="reset-call-admission-control"></a>重設通話許可控制

如果舊版前端池是託管 [呼叫許可控制] (CAC), 您必須先將 CAC 託管到商務用 Skype Server 2019 池, 才能移除舊版的前端池。
  
### <a name="to-reset-cac"></a>若要重設 CAC

1. 開啟拓撲建立器。
    
2. 以滑鼠右鍵按一下網站節點, 然後按一下 [**編輯屬性**]。
    
3. 在 [**呼叫許可控制設定**] 底下, 請確認已選取 [**啟用撥號許可控制**]。 
    
4. 在 [前端池] 底下,**若要執行 [呼叫許可控制] (CAC)**, 請選取要裝載 CAC 的商務用 Skype Server 2019 池, 然後按一下 **[確定]**。
    
5. 發佈拓撲。
    

